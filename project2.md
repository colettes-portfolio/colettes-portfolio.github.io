# A Geospatial Analysis of Residential Energy Consumption and Affordability

## Executive Summary
This report attempts to estimate energy burden using average income information with average energy consumption data and identify its spatial distribution in combination with rebate and energy savings data as well as demographic indicators. By doing so, this report aims to identify areas with the highest opportunity for further energy efficiency programs and areas most at risk for high energy burdens. The findings highlight specific block groups of the city where increased energy efficiency programming would have the maximum benefit, while also revealing pressing needs for increased investment in energy-efficient housing solutions in low-income areas.

## Research Questions
 * How can areas in Boston/MA with the highest opportunity for additional or increased energy efficiency programs be identified (in order to alleviate estimated energy burdens)?
  * How can areas most at risk for high energy burdens be identified?

## Data Sources & Methods
### Data
This study used three datasets to estimate the energy burden in Boston and identify neighborhoods where there should be greater uptake of energy efficiency programs:

1. City of Boston Property Assessment dataset
   - Property details for all unique properties in the city
   - 133,071 individual residential properties
   - Key fields: property ID, number of units, heat type, property use type

2. Mass Save CY2021 Residential Customer Study
   - Household customer numbers
   - Total electricity and natural gas consumption at block group level
   - Average electricity and gas consumption per household calculated
   - Average electricity and natural gas rates for 2021

3. American Community Survey (2015-2019)
   - Demographic indicators at block group/census tract levels from BARI

### Methods
A significant amount of data processing and manipulation was required to ensure all datasets were in the same format for joining, and to standardize the data for consistency and accuracy. Although none of these primary datasets are inherently spatial, each contained identifiers for block group and census tracts. The geospatial dataset, a shapefile of Boston's neighborhoods, Census Tracts and Block Groups, was joined onto other datasets for spatial analysis.

Estimated energy burden was calculated as:
```
Estimated Annual Energy Costs / Median Annual Income = Estimated Energy Burden
```

## Results & Analysis 

### Energy Consumption Patterns 

#### Average Household electricity use per block group: 
This map shows the average household electricity use for each block group in Boston. The data suggests that the highest electricity consumption occurs in the downtown area and parts of the South End. Other areas with higher-than-average electricity usage include East Boston, parts of Dorchester, and parts of Roxbury. In contrast, areas such as West Roxbury and Hyde Park tend to have lower than average electricity consumption. 

![image](https://github.com/user-attachments/assets/bfe55410-0f73-4b17-8d1a-54ea35bfb10f)

#### Average household gas use for each block group in Boston: 

The data reveals that neighborhoods such as Dorchester , Mattapan, Jamaica Plain, and parts of Brighton tend to have the highest gas consumption, while areas like Mission Hill, South Boston, the South End, and Charlestown tend to have lower than average gas consumption. Many properties in Boston, especially triple deckers and brownstones, still have single building-wide heating systems like boilers with radiators, which are more difficult to submeter. Although landlords could invest in upgrades to submeter each apartment, they may find it cost prohibitive or inefficient to do so. As a result, landlords pay the utility bill and try to recoup these costs through rent increases, often telling tenants that heat is included in their base rent costs. This creates a market failure where both tenants and landlords have little incentive to conserve energy. For tenants living in inefficient buildings with heat-included rents, even if they are not paying monthly utility bills, they could still be facing increased costs due to energy costs being absorbed in the rent. While this cost increase may have benefits for some tenants, such as protection from market fluctuations and reduced monthly financial strain, it also creates an energy burden. Some building owners may try to increase rents to amounts greater than the overall utility costs, especially during years with higher gas prices, which places an even greater financial burden on tenants.
Policies that encourage the inclusion of energy costs in base rents could be appropriate if they lead to greater efficiency via investments in energy-efficient construction. However, if investing in individual metering of apartments is their response to challenges associated with higher utility costs, not investing in energy efficiency infrastructure, it will also not lead to greater energy efficiency at these properties. If building owners have no incentive to reduce the energy intensity of their properties since they can recoup costs via rent increases, properties’ energy burden ratio can still have a negative impact on tenants as they may be unable to afford the rent in these buildings.

![image](https://github.com/user-attachments/assets/bef855b3-906b-4e6b-ac26-86bac6f0a9a8)

#### Estimated average annual energy costs per household for each block group in Boston

The data suggests that the highest energy costs tend to occur in the North End, parts of Roxbury, parts of Dorchester, Brighton, and Mattapan. In contrast, areas such as East Boston, South Boston, East Dorchester, and Roslindale tend to have lower than average energy costs. 

![image](https://github.com/user-attachments/assets/298a8c5e-f646-4d7f-9520-e197818a8d19)

#### Average household gas savings resulting from utility energy efficiency programs for each block group in Boston

The data shows that the highest savings tend to occur in neighborhoods such as Roxbury, Allston/Brighton, and West Roxbury. In contrast, areas such as South Boston, parts of Dorchester, and East Boston tend to have lower than average gas savings. Though the highest savings are appearing in the same areas as some of the highest average usage numbers, notably, the quantities of savings are quite low. 

![image](https://github.com/user-attachments/assets/2ab927ff-4179-4f49-bd3f-dcaa5178bfe9)

#### Average household electricity savings resulting from utility energy efficiency programs for each block group in Boston

The data shows that the highest savings tend to occur in Jamaica Plain, and parts of Dorchester and Mattapan. In contrast, areas such as the North End, the South End, and Easton Boston tend to have lower than average electricity savings. Similar to the gas savings estimates, though many of the areas with higher-than-average electricity consumption seem to have the highest savings estimates, which is a good sign that neighborhoods are well targeted, the savings themselves are minimal. A household using 10,000 kWh per year (some of the highest in the city) saving 600 kWh per year (more than any of the block groups saved) will only have a 6% reduction in their annual cost. 

![image](https://github.com/user-attachments/assets/db88b5a2-033c-4de2-86a3-d2d0e3a632cd)

The estimated energy burden map shows that certain neighborhoods, such as Roxbury, Mattapan, and Dorchester, have a higher estimated energy burden than others. These neighborhoods also tend to have lower median household incomes, which suggests that energy costs may be disproportionately burdensome for low-income households in these areas. Additionally, certain block groups within neighborhoods have higher estimated energy burdens than others, indicating that energy burden may be a localized issue within some neighborhoods. The map of areas with the worst energy burden highlights block groups with the highest estimated energy burden in the city. These areas tend to be in neighborhoods with lower median household incomes, such as Roxbury, Mattapan, and Dorchester, explored further in Figure 9.

![image](https://github.com/user-attachments/assets/d63ce279-fec1-46e4-9d55-a628e96bb8a4)

### Socioeconomic Relationships

#### Bivariate choropleth map showing the relationship between estimated energy burden and high-income residents
Reveals a clear pattern: high-income areas tend to have lower estimated energy burdens than low-income areas. This highlights the potential unequal distribution of energy burden across different income groups within the city of Boston. Some of the wealthiest areas, like Roslindale, West Roxbury, Charlestown, the South End and Bay Village have low burdens and high incomes. Recall Figure 2, on concentration of energy-efficient (but expensive) heat pump technology. The areas of highest density of that tech are located in areas that are the wealthiest, and also some of the lowest burdens. 

![image](https://github.com/user-attachments/assets/64b6cabe-da3e-4918-aa4c-6c8268773d0a)

#### Bivariate choropleth map showing the relationship between estimated energy burden and limited English proficiency
Reveals that areas with a higher percentage of residents who are limited English proficient tend to have higher estimated energy burdens. This suggests that language barriers may make it difficult for households to access energy-saving programs and resources, leading to higher energy costs. 

![image](https://github.com/user-attachments/assets/2bc40afe-da3d-40fc-ab17-0cc5ced47b6d)

#### Bivariate choropleth map showing the relationship between estimated energy burden and the percentage of residents who are renters 
Indicates that areas with a higher percentage of renters tend to have higher estimated energy burdens. Renters may be less likely to invest in energy-saving measures, such as insulation or weatherization since they do not own the property and may not see a direct benefit from these investments. 

![image](https://github.com/user-attachments/assets/7278c980-e204-4fb2-959d-103914b1c6bf)

#### Priority areas for intervention
Map of areas with both the worst energy burden, lowest electric and savings, and higher concentrations of multifamily houses with between 2 and 6 units, shows block groups that have both a high estimated energy burden and low average savings from utility energy efficiency programs. These areas may be particularly in need of targeted outreach and assistance to help households reduce their energy costs. They are largely concentrated in Roxbury, Mattapan, and Dorchester, though there are a few elsewhere (Brighton and Charlestown, Hyde Park, JP). This information could be useful in designing policies meant to target low efficiency properties with high risk residents, and is the culmination of the report’s analytical efforts.

![image](https://github.com/user-attachments/assets/b7bc7eee-b908-44e2-8137-f5bd60b9336d)

## Discussion
<p>This report has highlighted specific block groups of the city where increased energy efficiency programming would have the maximum benefit. While these specific areas are important, the analysis conducted in this paper highlights the pressing need for increased investment in energy-efficient housing solutions in low-income areas. The findings suggest that residents in these areas are not only more likely to experience energy burden, but they are also more likely to live in housing that is of poorer quality and in need of upgrades. This highlights a significant equity issue, where those who can least afford additional costs are burdened with high energy costs and may live in substandard housing. This study has attempted to show that high energy burdens and dense, old housing with out-of-date energy technologies are inextricably linked, and not distributed equally across the City. However, future studies should leverage other details in the City of Boston's property assessment data to investigate whether the "quality" of housing can be assessed with greater granularity.</p>

<p>Beyond the discussion of utility bill affordability, the apparent inequity of energy efficient housing raises questions on the net-zero future of the City of Boston. Issues of equity saturate the transition to a greener energy economy, and the City's vision for a carbon free Boston by 2050 is at odds with the current state of housing inefficiency. Though large commercial and residential buildings make up a larger proportion of the City's emissions than smaller scale residential housing, these homes are still significant contributors to emissions -- especially those using high-methane fuels like oil, or operating old, inefficient boilers. As certain areas in the City become increasingly efficient, and electrification becomes the new norm, it is crucial that these households are not left behind in the energy transition. Electrifying the grid by incorporating a higher proportion of renewables in producing electricity may raise electricity rates for all customers. And as high-income areas become more efficient and reduce natural gas consumption, by doing efficiency conversions like heat pump installations, gas prices could see an overall increase as well as demand decreases. For low-income households operating old systems, this could mean their utility bills grow even larger, exacerbating their energy burdens, and widening the income inequality gap further.</p>


## Conclusion 
<p>The City of Boston and State of Massachusetts must take action to close the efficiency and housing quality gaps between low-income households and high-income households, especially in the context of moving forward with carbon free planning.
To address this issue, there needs to be a concerted effort by the City of Boston and the State of Massachusetts to increase access to energy-efficient housing for low-income residents. This could include programs that provide funding for energy-efficient upgrades to existing housing stock, incentives for developers to build energy-efficient housing in low-income areas, and initiatives that prioritize the retrofitting of public housing with energy-efficient technologies.
The information from this study should be used to target particular areas in Boston, homeowners and occupants with information relevant and accessible to the issues they face, accompanied by broad assistance and energy assessments. Integrated energy, health, and housing funding, resources, and engagement must become a priority for City government, potentially as part of their carbon-free initiatives. Environmental improvement cannot take place if significantly at risk, low-income, traditionally marginalized communities, already suffering from environmental hazards and inequity, are left out. Notably, these solutions cannot be implemented in a vacuum and must be tailored to the unique needs of each community. This includes taking into account factors such as language barriers, cultural norms, and others that may impact the effectiveness of these programs. Moving forward, it will be essential for policymakers to prioritize the development of sustainable, equitable housing policies that address the energy efficiency and quality of housing in low-income areas. Failure to do so will only exacerbate the energy burden faced by low-income households and hinder efforts to transition to a low-carbon, sustainable energy future for Boston.</p>

## Policy Recommendations
1. Increase access to energy-efficient housing for low-income residents through:
   - Funding for energy-efficient upgrades to existing housing stock
   - Incentives for developers to build energy-efficient housing in low-income areas
   - Initiatives prioritizing retrofitting of public housing with energy-efficient technologies

2. Target particular areas in Boston with information relevant and accessible to the issues they face, accompanied by broad assistance and energy assessments

3. Make integrated energy, health, and housing funding, resources, and engagement a priority for City government

4. Ensure solutions are tailored to community needs, considering:
   - Language barriers
   - Cultural norms
   - Other factors that may impact program effectiveness

***

*This research was conducted in April 2023. For access to the complete paper, including full statistical analyses and methodology details, please [contact me](mailto:baker.cole@northeastern.edu).*

## References
Brown, Marilyn A, Anmol Soni, Melissa V Lapsa, Katie Southworth, and Matt Cox. “High Energy Burden and Low-Income Energy Affordability: Conclusions from a Literature Review.” Progress in Energy 2, no. 4 (2020): 042003. https://doi.org/10.1088/2516-1083/abb954.
Eisenberg, Joel Fred. “Weatherization Assistance Program Technical Memorandum Background Data and Statistics on Low-Income Energy Use and Burdens,” 2014. https://doi.org/10.2172/1132973
Moroney, John. “Heating Worries Mount amid Growing Costs.” NBC Boston. NBC10 Boston, October 21, 2022. https://www.nbcboston.com/news/local/heating-worries-mount-amid-growing-costs/2870216/.

