## Executive Summary
Regular seasonal utility costs can pose a crushing burden to many Americans and New Englanders, especially during its cold winters. Due to energy burden's close relationship to the quality of housing and energy inefficiency accessible to low-income households, this paper uses the 2021 City of Boston's Property Assessment dataset, and the detailed property characteristics therein, to predict areas in the City that may be experiencing elevated energy burden. It examines calculations of energy burden risk through the lens of socio-economic demographic data from the 2015-2019 American Community Survey, as well as comparing the calculated risks to utility consumption from Mass Save's 2020 Massachusetts Residential Customer Profile Study. This paper finds that access to energy efficient housing is not equitably distributed across the City of Boston, and this gap may grow.
***

*This research was conducted in December 2022. For access to the complete paper, including full statistical analyses and methodology details, please [contact me](mailto:baker.cole@northeastern.edu).*
***
## Research Questions
This study explores these key questions:
- Can areas in Boston facing energy burden be predicted based on the characteristics of their housing?
- Are these predictions associated with actual increased energy consumption?
- Where in Boston are they most concentrated?

## Data Sources & Methods
### Data
The study utilized three main datasets:
1. CY2021 City of Boston Property Assessment dataset
   - Contains property details for all unique properties in the city
   - Working dataset of 133,071 individual residential properties
   - 79 variables describing property characteristics

2. Mass Save's 2020 Massachusetts Residential Customer Profile Study
   - Customer data on electricity consumption and gas consumption at block group level

3. American Community Survey (2015-2019)
   - Demographic and socioeconomic indicators at block group/census tract levels

### Methods
Established a latent variable for Energy Burden Risk Score (EBRS) based on four key building characteristics crucial to energy consumption:
- Air conditioning access
- Year built/remodeled
- Overall property condition
- Roof type

EBRS is calculated at the record level by:
```
EBRS = (AC Score + Year Score + Condition Score + Roof Score) / Maximum Possible Score
```

Learn more about how I calculated this variable by visiting a more detailed page on its construction and background on the logic: [View Variable Construction](project1_ebrs.md)

## Results & Analysis
### Distribution of EBRS
The block group with the highest average Energy Burden Risk Score is in Lower Allston (0.8969), followed by Brighton's Oak Square and Franklin Field South in Mattapan (0.89, 0.87, respectively).

The lowest burdens are in:
- East Boston, near LoPresti Park (0.25)
- Back Bay by the Boston Public Library (0.36)
- Seaport (0.42)

<p> <img src="https://github.com/user-attachments/assets/390de5ee-e2fd-4251-83ef-369d0bf68587" alt="Table 1: Summary Statistics of Average EBRS by Block Group" title="Table 1: Summary Statistics of Average EBRS by Block Group" align="left" hspace="50" vspace="50" width="15%" height="15%"> </p>

<p> Mapping all scores, Figure 1, shows that there are some block groups whose scores are so low that they skew the visual analysis, as seen in the brightest spots in Figure 1. Limiting the map to display scores exclusively above 0.5, in Figure 2, reveals additional variability in its distribution across the city. Some of the highest burdens are clearly clustered in Allston, Hyde Park, South Dorchester, and Mattapan. It appears that moving away from the City's center tends to increase the EBRS, though immediately at the edges of the City limits, such as in the Roslindale and Brighton areas tend to have slightly lower EBRSs than those slightly more central to the City.</p>
<p>
<img src="https://github.com/user-attachments/assets/10b03c85-3c6a-4cfa-9798-165c70773111" width="85%" height="85%"></p>

### Average EBRS -- By Neighborhood
<p> Though neighborhood-level EBRS aggregates were not used in statistical analysis, as block group level analysis has greater specificity and accuracy, Table 3 displays Average EBRS at the neighborhood level for legibility purposes. At the neighborhood level, the highest EBRSs are in Roslindale and Mattapan. These block groups have some of the highest concentrations of energy inefficient properties, mainly older R1-R4 homes. The neighborhoods with lowest EBRSs are in South Boston and in Central (Downtown) Boston.</p>
<img src = "https://github.com/user-attachments/assets/120faa49-ca39-49cc-9f6a-47d9ccde5b48" width=25% height=25%>


### Correlations and Significance

Strongest positive correlations with EBRS:
- Natural gas usage per household (therms)
- Proportion of buildings with less than five units
- Proportion of population who are Black
- Proportion of population who have completed high school
- Proportion of population who have completed some college

Strongest negative correlations:
- Median home value
- Proportion of residents who have completed a professional degree

<img src = "https://github.com/user-attachments/assets/1bb2ed2f-407b-4ff6-ae04-386ed07a6560" width=25% height=25%>
### Bivariate Regression

Given the strength of the EBRS's relationship with gas consumption (*thermsperhh*), it formed the basis of bivariate regression analysis, then multiple regression analysis. Running a regression on the two variables, with EBRS as the dependent variable and therms per household as independent shows that 21% of the variability in average EBRS can be explained by household energy consumption. Figure 3 shows the linear regression plot between average burden and therms consumed per household at the block group level.
Figure 3

<img src = "https://github.com/user-attachments/assets/4d0daaf9-ac20-43b8-8db4-cbc3537673b5" width=50% height=50%>


### Multiple Regression

Table 6: Multiple Regression Results

<img src = "https://github.com/user-attachments/assets/c6ea4905-1694-4b46-b5e7-b7f5bc44c67b" width=50% height=50%>


Multiple regression testing was conducted, adding one after another the most strongly correlated and statistically significant variables to the bivariate regression of EBRS with therms per household, to generate the most effective model. Variables suspected to be highly collinear with one another, such as multiple variables for maximum educational attainment, were not duplicated in the multiple regression, to avoid multicollinearity and overfitting the model. The strongest multiple regression is in Table 6.


The Adjusted R2 of the multiple regression shows that approximately 32% of variability in the EBRS can be explained by gas consumption per household, median home value, the proportion of buildings in a block group with less than five units, and the proportion of residents whose maximum education attainment is some college. 


## Discussion
As seen in the mapping visualizations, areas associated with high income and most numbers of new buildings are scoring low on the EBRS scale. Interestingly, some rapidly gentrifying areas like Jamaica Plain and the South End are in the lower third of EBRSs, likely due to significant new construction.

The distribution of EBRSs alongside gas consumption highlights inequities and confirms EBRS as a predictor of actual energy burden. Low-income households not only suffer from energy invoices taking up a larger proportion of their income but are also more likely to pay higher energy bills due to inherent property inefficiency.

Many properties in Boston, especially triple deckers and brownstones, still have single building-wide heating systems like boilers with radiators, which are more difficult to submeter. This creates complex landlord-tenant dynamics around energy costs and efficiency improvements.

## Conclusion

<p> Beyond the discussion of utility bill affordability, the apparent inequity of energy efficient housing raises questions on the net-zero future of the City of Boston. Issues of equity saturate the transition to a greener energy economy, and the City’s vision for a carbon free Boston by 2050 is at odds with the current state of housing inefficiency. Though large commercial and residential buildings make up a larger proportion of the City’s emissions than smaller scale residential housing, these homes are still significant contributors to emissions – especially those using high-methane fuels like oil, or operating old, inefficient boilers. As certain areas in the City become increasingly efficient, and electrification becomes the new norm, it is crucial that these households are not left behind in the energy transition. Electrifying the grid by incorporating a higher proportion of renewables in producing electricity will raise electricity rates for all customers. And as some high-income areas become more efficient and reduce natural gas consumption, gas prices could see an overall increase as well. For low-income households operating old systems, this could mean their utility bills grow even larger, exacerbating their energy burdens, and widening the income inequality gap further.  </p>

<p> As low-income households are more likely to be tenants rather than owners, and more likely to live in inefficient housing requiring energy efficiency upgrades, any new regulations enforcing the upgrade of old systems to newer technology must ensure that landlords do not shift the cost of such upgrades to tenants, as energy costs are today. </p>

<p> Future studies on this topic should assess the distribution of energy efficiency upgrades rebates and incentives (touched upon in the heat pumps section above), as well as the distribution of households participating in energy assistance programs. While the barriers to low-to-moderate income participation in energy efficiency programs were not explored in detail, an assessment is necessary.  </p>

<p> This study has shown that high energy burdens and inadequate, poorly maintained, and outdated energy technologies are inextricably linked, and not distributed equally across the City. While billing assistance programs like LIHEAP and winter moratoriums on utility shutoffs and evictions are necessary for the survival of many families, they are not enough to address the system issues at play when it comes to housing quality and safety. The relationship between housing quality and energy costs, as well as the inability to move into safer, more efficient housing, signals that there need to be effective, broad regulatory programs to better fit the needs of the community and address these legacies of environmental hazards and energy inefficiency. The information from this study should be used to target particular areas in Boston, homeowners and occupants with information relevant and accessible to the issues they face, accompanied by broad assistance and energy assessments. Integrated energy, health, and housing funding, resources, and engagement must become a priority for City government, potentially as part of their carbon-free initiatives. Environmental improvement cannot take place if significant at risk, low-income, traditionally marginalized communities, already suffering from environmental hazards and inequity, are left out. </p>



## Policy Recommendations
1. The City of Boston and State of Massachusetts must take action to close the efficiency and housing quality gaps between low-income households and high-income households

2. Any new regulations enforcing system upgrades must ensure landlords don't shift costs entirely to tenants

3. Need for integrated energy, health, and housing funding as part of carbon-free initiatives

4. Environmental improvement cannot proceed without including traditionally marginalized communities already suffering from environmental hazards

***

*This research was conducted in December 2022. For access to the complete paper, including full statistical analyses and methodology details, please [contact me](mailto:baker.cole@northeastern.edu).*
***
## References
<p>Brown, Marilyn A, Anmol Soni, Melissa V Lapsa, Katie Southworth, and Matt Cox. “High Energy Burden and Low-Income Energy Affordability: Conclusions from a Literature Review.” Progress in Energy 2, no. 4 (2020): 042003. https://doi.org/10.1088/2516-1083/abb954. </p>

  <p>Eisenberg, Joel Fred. “Weatherization Assistance Program Technical Memorandum Background Data and Statistics on Low-Income Energy Use and Burdens,” 2014. https://doi.org/10.2172/1132973. </p>
<p>Energy Policy Planning & Analysis Division. “How Massachusetts Households Heat Their Homes.” Mass.gov. Accessed December 16, 2022. https://www.mass.gov/service-details/how-massachusetts-households-heat-their-homes. </p>
<p>“Learn about Home Energy Assistance .” Mass.gov. Accessed December 16, 2022. https://www.mass.gov/service-details/learn-about-home-energy-assistance-liheap. </p>
<p>Mercado, Madison. “Boston Remains Highly Gentrified despite Housing Efforts.” The Daily Free Press, February 18, 2021. https://dailyfreepress.com/2021/02/18/boston-remains-highly-gentrified-despite-housing-efforts/. </p>
<p>Moroney, John. “Heating Worries Mount amid Growing Costs.” NBC Boston. NBC10 Boston, October 21, 2022. https://www.nbcboston.com/news/local/heating-worries-mount-amid-growing-costs/2870216/.</p> 
<p>“When Am I Protected from Having My Utilities Shut off?” Mass.gov. Accessed December 16, 2022. https://www.mass.gov/service-details/when-am-i-protected-from-having-my-utilities-shut-off. </p>
<p>“With Energy Prices Rising, Fire Officials Urge Home Heating Safety.” Mass.gov. Accessed December 16, 2022. https://www.mass.gov/news/with-energy-prices-rising-fire-officials-urge-home-heating-safety. </p>
<p>Zhao, Yiwei. “Heating Costs Hit the Highest Level in More than a Decade.” Sampan, November 21, 2022. https://sampan.org/2022/metro/heating-costs-hit-the-highest-level-in-more-than-a-decade/. </p>
