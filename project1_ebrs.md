# Developing the Energy Burden Risk Score
## Overview
<p>The following construct for Energy Burden Risk Score (EBRS) is derived from the Boston 2021 Property Assessment dataset. Energy burden is typically calculated as the proportion of a household’s annual utility bills out of their annual household income. It is used to describe the effect of when low-income households have high energy bills, the proportion of their income dedicated to heating/cooling their homes grows larger. This often means forgoing spending in other categories, often other necessities like food, creating what is sometimes referred to as the “heat or eat” choice. However, assessing energy burden at an aggregate level is challenging due to the inaccessibility of broad, detailed, residential utility consumption data. But because energy burden is a complex and compound issue generated by a combination of factors like income, housing quality and efficiency, weather intensity, as well as fluctuations in market prices of gas, it is plausible that its impacts can be estimated as a function of other, related factors with more easily accessible information. The EBRS combines and rates four key property characteristic fields in the 2021 Property Assessment Dataset to identify the areas in the City of Boston at risk of higher energy burden (air conditioning, year built/remodeled, overall property condition, and roof type).
The key logic behind associating property characteristics with risk of energy burden is that: poor quality housing can exacerbate the energy inefficiency of properties and increase energy costs disproportionately beyond those associated with higher energy efficient homes. Higher income owners can rent higher quality or newer homes, which have better insulation, more efficient appliances, and less energy leakage. In addition, low-income households often do not have the liquid assets to invest in energy efficiency upgrades or keep up with property maintenance, even if these upgrades could result in long term energy bill savings, that would ultimately benefit lower income households’ ability to spend more than it would a higher income household. The EBRS is based on property characteristics alone, but will be complemented in future analyses by socioeconomic data, like income and public assistance recipients, which are also key predictors of energy burden risk. The following sections describe the manifest variables used to construct the EBRS, explain the metric’s assembly, then share aggregate results of its distribution at the census block group level and the census tract level.</p>

## Measure Construction
The measure required defining four new manifest variables at the record level, as follows:
_Air Conditioning Score (AC_Score)_
The first manifest variable uses the dataset’s AC_TYPE field to incorporate and score the energy burden risk related to whether the property has central air conditioning. Central and ductless air conditioning HVAC systems in building have a decreasing impact on energy burden as building system HVAC systems are typically more energy efficient than self-installed individual air conditioning units. Running AC centrally would produce a lower energy bill than an individual AC unit would. As summers become hotter, having access to cooling is increasingly a necessity. The scores were assigned per Table 1. 

| Table 1           |                  |
|-------------------|-----------------|
| **AC Type**     | **Score**           |
| Central           | 0               |
| Condition Score   | 0               |
| Roof Score        | 1               |  
| NA                | NA              |

_Year Score (YR_SCORE)_

Older buildings are more likely to leak energy than newer construction. This is primarily due to changes in wall and attic insulation technology over time, heating input, exterior cladding, as well as accumulated wear and tear. Remodeling older buildings, replacing boilers, recladding exteriors, and replacing roofs, can reduce energy leakage. Therefore, the year score takes the dataset’s field for construction year, YR_BUILT, and the field for year remodeled, YR_REMODEL, and averages them – with 60% weight to year built, 40% to year remodeled. The YR_SCORE weights construction year more heavily due to the lack of detail in the dataset on the type of remodel that took place – remodeling could mean many different types of projects, some of which might have limited impacts on energy envelope. If no remodel year is present, the year score takes the year-built field alone. The scores were assigned per Table 2.

| Table 2           |                  |
|-------------------|-----------------|
| **Year Built/Remodeled**     | **Score**           |
| <1939           | 5               |
| 1940-1959   | 4               |
| 1960-1979        | 3               |  
| 1980-1999                | 2              |
| 2000-2021                | 1              |
| NA                | NA              |

_Overall Property Condition Score (COND_SCORE)_

A property’s condition will also have a large impact on energy leakage. Poorly maintained or inefficient homes will use more energy and generate higher energy bills than a home of the same size that is better maintained. Households experiencing energy burden are also more likely to live in poorly maintained homes for two critical reasons 1) they are less expensive to rent or purchase and 2) low-income households have less income flexibility and fewer liquid assets to invest in energy efficiency upgrades and general upkeep, even if it results in larger aggregate energy bill savings. The scores were assigned per Table 3.

| Table 3           |                  |
|-------------------|-----------------|
| **Overall Condition**     | **Score**           |
| Unsound           | 5               |
|Poor   | 5               |
| Average        | 4               |  
| Fair                | 3              |
| Good                | 2              |
| Very Good                | 1              |
| Excellent                | 1              |
| NA                | NA              |

_Roof Score (ROOF_SCORE)_

Roofing materials can significantly impact the demand of energy of a home due to their heat resistance - but like other energy efficient investments, the most efficient materials are often the most cost prohibitive. With the exception of new construction, most buildings in the Boston area were traditionally built to withstand cold winters, not hot summers. However, as shoulder seasons get shorter, winters become milder, and summers get hotter due to the impacts of climate change, these traditional technologies are no longer as desirable. Households lacking in income flexibility are more likely to live in a home with older roofing technology, or cheaper roof material. The dataset’s residential properties have the following roof types, and their score was assigned in the order in Table 4 (highest to lowest burden).
Asphalt shingles, also known as composition or composite shingles, are the most popular roofing material in the United States. Regardless of their color, it is estimated that only approximately 30% of light hitting asphalt shingles is reflected. This heat is transferred from the roof to the upper floors of a building. Though this can assist in warming a home in the wintertime, it is a cause for additional energy demand during the summer months. Because of the lack of sun gain during a Massachusetts winter, potential heat gains in wintertime have less of an impact on building temperature than the summertime solar burden. Therefore, in an assignment of an energy burden, asphalt shingles are a property characteristic considered an increase in energy burden.
Wood shingles are more expensive to maintain, and if not replaced, can increase energy leakage in the wintertime. They are not resilient to storms and are not as watertight as newer materials.
Slate and tile materials are generally more expensive to install than composite traditional shingles, but are more resilient to wind and rain, require less maintenance, and are usually lighter in color, increasing their solar reflectively, decreasing their risk for contributing to higher energy burden.
Rubber roof materials are a newer product. This material has a high reflective property, assisting in summer cooling, and creates a secure, watertight seal on a rooftop, which can reduce heat leakage in the winter months, or due to storm conditions. The properties with rubber roofs were assigned the score with least contribution to energy burden.


| Table 4           |                  |
|-------------------|-----------------|
| **Roof Type**     | **Score**           |
| Asphalt           | 4               |
| Composite                | 4              |
| Wood                | 3              |
| Slate                | 2              |
| Tile                | 2              |
| Rubber                | 1              |
| Other                | NA              |
| NA                | NA              |


_Measure Calculation_

$$EBRS = \frac{AC\ Score + Year\ Score + Condition\ Score + Roof\ Score}{Maximum\ Possible\ Score}$$

Because some properties may have one or more of the manifest fields blank, to establish a like-for-like comparison, property energy burden risk is expressed as a ratio between the total assigned risk score for non-blank manifest fields out of the total possible points achievable for that property; the maximum possible burden. For example, in the instance that a property was assigned a Year Score of 4, Property Condition Score of 3, and Roofing Score of 2, but the AC field is null, the equation for this property's property energy burden risk score is calculated as:

$$EBRS = \frac{0 + 4 + 3 + 2}{0 + 5 + 5 + 4} = \frac{9}{14} = 0.643$$

Due to their anticipated differences in impact to energy intensity at the property level, the manifest variables are not weighted equally in terms of increasing energy burden risk. If all fields are not null, their proportion of the burden would be:

|Manifest Variable|Max % of Burden|
|-------------------|-----------------|
| AC Score           | 6.66%          |
| Year Score   | 33.3%                |
| Condition Score        | 26.6%      |  
| Roof Score                | 33.3%   |
