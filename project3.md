# Beyond the Burden: Pathways to Urban Resilience in the Energy Crisis of Massachusetts

## Executive Summary
Rising energy burdens in Massachusetts, exacerbated by socioeconomic disparities and market volatility, significantly undermine urban resilience by increasing vulnerability amongst households. While short-term strategies like heat assistance are necessary for maintaining survival for many households in the Commonwealth, they are palliative and are not adequate, not addressing the underlying causes and changes in conditions that have generated these conditions for households. This study quantifies energy burdens across Massachusetts from 2017-2022, assesses their correlation with socioeconomic and demographic indicators, and proposes interventions to reduce these burdens and strengthen urban resilience.

***

*This research was conducted in April 2024. For access to the complete paper, including full statistical analyses and methodology details, please [contact me](mailto:baker.cole@northeastern.edu).*

***
## Research Questions
- How have energy burdens in Massachusetts evolved from 2017-2022?
- What are the correlations between energy burdens and socioeconomic and demographic indicators?
- How can large price shocks on specific utilities impact different types of customers?

## Data Sources & Methods
### Data

1. **Non-heating Electricity and Natural Gas:**
   - MassSave Customer Profile Dashboard data
   - Detailed household customer numbers and consumption at block group level (2017-2022)
   - Transformed into metrics: average non-heating electricity consumption and gas consumption per household
   
2. **Alternative Fuel Consumption:**
   - State of Massachusetts annual reports on household heating costs
   - Estimates for oil, bottled gas (kerosene, propane), wood, electric resistance heating
   - Applied uniformly across block groups

3. **American Community Survey Data (ACS):**
   - 5-year 2022 Table B25040 for heating fuel types
   - Annual median income estimates
   - Demographic indicators

### Methods
*Quantitative Analysis:*
- Combined estimated fuel consumption with annual energy price data (2017-2022)
- Calculated costs for various energy types including basic electricity service, electric heat, natural gas, oil, wood, bottled gas
- Created weighted average energy cost per block group based on fuel type proportions
- Estimated energy burden using: expenditure on utility costs / median household income

*Qualitative Analysis:*
- Interviews with energy assistance professionals
- Analysis of media coverage using GDELT tool
- Text analysis of television coverage

## Results & Analysis

### Temporal Changes in Energy Burden

The results of the statistical analysis show that average energy costs and energy burden for many MA residents increased overall from 2017-2022, with residents shifting from one energy burden group to another. 

<img src="https://github.com/user-attachments/assets/877fd74f-91fc-4a6d-8e91-a9326ff3ac03" alt="Annual estimated energy burdens across Massachusetts census tracts (2017-2022)" title="Annual estimated energy burdens across Massachusetts census tracts (2017-2022)" align="center" hspace="60" vspace="60" width="100%" height="100%">

The counts at each level of energy burden group vary from year to year. For example, from 2017-2018, there is a decrease in the up to 2% energy burden group and a corresponding increase in the 2-5% and 5-8% burden groups. The up to 2% burden group has the highest number of census tracts across all years, indicating that most MA residents have lower energy burdens. Also true is that the above 15% burden group has the lowest count, suggesting that fewer census tracts have experienced very high energy burdens across this time period. However, there are sizeable shifts across the years. In 2020, the Up to 2% and 2-5% burden groups experienced notable increases, while the 5-8% burden group saw a significant decrease. In 2021 and 2022, the 8-15% and 5-8% burden groups grew significantly, resulting in a decrease in the 2-5% and up to 2% groups.  The Above 15% burden group has remained stable, making up the smallest proportion across all years.

<img src="assets/img/burden_change.gif" alt="Energy Burden Changes 2017-2022" align="center" hspace="60" vspace="60" width="100%" height="100%">


### Income Group Analysis
The results of average energy burdens by year and income group of census tracts reveal which income groups experienced the largest changes in burdens, and when:
<img src="https://github.com/user-attachments/assets/32e10458-aa80-4d7e-a8de-e2df275d1785" alt="by year and income grp" title="yr group" align="center" hspace="60" vspace="60" width="90%" height="90%">

The lowest income groups experienced both the largest burdens across all years, but also the largest changes in their estimated energy burdens, particularly in 2022. 

### Statistical Relationships

I tested my estimate for burden against several existing vulnerability and resiliency scores, like the SVI score (from the CDC), the EJScreen index (EPA), the Community resiliency Score (FEMA). I found that my estimates for burden had a strong inverse relationship with most community resiliency scores, suggesting that communities with higher energy burdens are indeed less equipped to prepare for, adapt to, and recover from hazards. 

I then brought in over 70 variables gathered from the American Community Survey in order to build a model. 

After examining correlations between variables, including using caution for multicollinearity, which can be difficult to avoid in such analyses, a backward stepwise regression approach was used, starting with a saturated model of all variables, gradually eliminates variables from the model that do not explain the outcome and that may be too highly correlated with one another.  
The final model: 
<img src="https://github.com/user-attachments/assets/df003451-c11f-470b-b889-584a83440f7b" alt="by year and income grp" title="yr group" align="center" hspace="60" vspace="60" width="60%" height="60%">
The final model shows that 56% of the variability in energy burden is explained by family poverty percentage, the percentage of households with bachelor’s degrees as their highest level of education, the percentage of housing units that are substandard, unemployment rate, ethnic heterogeneity, and eviction filing rate. The model indicates that factors associated with economic hardship (like family poverty percentage and unemployment rate) are positively correlated with the dependent variable, while indicators of socioeconomic advantage (such as higher educational attainment) show a negative correlation. Ethnic heterogeneity negatively correlates with the dependent variable, suggesting that areas with a higher mix of ethnic backgrounds might have, on average, lower energy burdens or less socioeconomic hardship. Eviction filing rates have a smaller but significant positive relationship which underscores that families experiencing hardships and increased energy burdens may be at increased risk for losing their housing and being evicted. The statistical significance of all predictors is strong (p < 0.01). 

### Interview Findings

I conducted an in-depth interview with the Energy Director of a community action agency in a major Massachusetts city. Key insights include:

- Evolution of Energy Assistance Programs: Community action agencies are focusing more on energy efficiency work to address the growing gap between income-scarce and income-secure populations.
- Federal Funding Challenges: Timing of federal funding, such as LIHEAP, often lags behind seasonal needs, impacting program effectiveness.
- Shift to Energy Efficiency: There's a trend towards energy efficiency measures and conversions to Air Source Heat Pumps (ASHP), primarily funded by utilities.
- Affordability vs. Environmental Goals: While ASHP conversions reduce carbon emissions, some customers face higher costs due to elevated electric rates.
- Equity and Advocacy: There's a strong focus on ensuring equitable access to energy assistance, including support for immigrants and non-English speakers.
- Landlord-Tenant Dynamics: Challenges arise in improving heating systems when landlords are unreachable or relationships are strained.
- Future Outlook: There's a need for increased funding and potential policy changes, such as including cooling assistance and extending LIHEAP calendars.
- Vulnerable Populations: Predatory electric competitive suppliers pose challenges for vulnerable communities.
- Impact of Moratoriums: COVID-19 shut-off moratoriums provided temporary relief but led to a surge in applications once lifted.

# Discussion

The quantitative and qualitative analysis can be summarized into three key findings. Between 2017-2022, there was:
1.	A large increase in the magnitude of energy burdens being experienced by households.
2.	A large increase in the quantity of areas experiencing higher energy burdens.
3.	These increases were particularly concentrated among low-income and minority communities, vulnerable residents, and those already experiencing economic hardship like unemployment and existing poverty.
![image](https://github.com/user-attachments/assets/42674af4-31ed-4c80-b023-9ae2639d018c)

These findings are particularly concerning given Massachusetts's aggressive pursuit of carbon reduction and fossil fuel-free goals. The transition, while essential for decarbonization, has led to sizable rate hikes due to clean energy charges and necessary grid enhancements.

<p>Massachusetts is one of twelve states where residents can choose to buy electricity from a supplier other than their default utility. In the late 1990s, lawmakers set the system up under the impression that a competitive “free-market” approach would result in lower prices for customers. Findings from the "Consumers Continue to Lose Big" report by the Massachusetts Attorney General's Office in 2021 provide an empirical backdrop that contextualizes the disparities observed in energy burdens, especially among communities with high proportions of residents with limited English proficiency, low-income status, as well as communities of color. This was echoed by Knittle, who emphasized that this market is problematic because of the dishonest sales tactics many sellers use, often pretending to be representatives of Eversource and National Grid to switch customers over, or promising rates that do not exist. Legally, competitive suppliers need a person’s informed consent before they switch an account to a new plan, but in practice, this does not happen. Due to the complexity of electricity bills, the average consumer cannot understand their power bill and that they have been switched to a different supplier. The 2021 report reveals that these communities paid $525 million more than necessary over six years highlights a critical resilience deficit: the inability of these populations to withstand and recover from financial shocks induced by predatory energy pricing, and the failure of the government to adequately protect their citizens from the hazard ("Consumers Continue to Lose Big," 2023). The report finds that low-income customers in the Commonwealth are twice as likely to sign up with individual competitive electric suppliers, and that they are charged at rates higher than non-low-income customers are. Of the top 100 census tracts identified in this study as having the highest energy burdens in 2022, all of them lie within the municipalities identified as having the highest premiums per kwh and the highest proportion of low-income residents enrolled in competitive supply contracts. The report covers a six year period, showing increasing losses annually, but limited advancement for legislation to protect residents. These financial losses exacerbate the potential energy burden faced by these communities by further increasing their share of income spent on utility bills. This can force households to make untenable choices between heating and other necessities ("Consumers Continue to Lose Big," 2023). Returning to the UK Energy Research Centre’s definition of price security in a resilient energy system, “avoiding unnecessary price spikes due to supply/demand imbalances or poor market operation”, the Massachusetts’s government, by continuing to allow the competitive supply market to operate while having been proven to both target and negatively impact already vulnerable households, has failed its residents and has undermined their resiliency (Whitaker et al. 2009). </p>

<p>This analysis has revealed a growing energy burden among Massachusetts households. Despite LIHEAP funding, which has consistently provided some relief to those who are eligible, the quantitative evidence suggests that such short-term measures are becoming increasingly inadequate. As Massachusetts aggressively pursues carbon reduction and fossil fuel-free goals, passing its climate law in 2021 which requires electricity generation to be net-zero by 2050, residents are being passed higher energy rates. This transition, while essential for decarbonization, has led to sizable rate hikes due to clean energy charges and the necessary grid enhancements to support electrification. In February 2024, Eversource and National Grid requested further rate hikes to enhance the power grid and accommodate the growing demand from electric vehicles and heat pumps. They are requesting approximately $2.4 billion over the next five years for grid improvements to convert the grid for renewable energy production and make it more resilient and capable of handling the surge in electrification (IER 2024). Eversource is looking to pass on $400 million of its costs over the next five years, while National Grid is seeking reimbursement for about $2 billion (IER 2024). Both utilities plan to recover money for other grid fixes through customer rate increases. If these plans get approved, five years from now, the average Eversource residential customer will pay nearly $5 a month more than today, while National Grid residential customers will pay an additional charge of nearly $7 a month, and “neither amount includes the cost of the increased power that the home may be consuming by then if they have electrified” (IER 2024). The proposed future rate increases by Eversource and National Grid underscore a critical issue: the transition to clean energy, though vital for environmental sustainability, is imposing a heavy financial burden on residents, and will impact low-income households the most.</p>

<p>In addition, LIHEAP funding is depleted by heating assistance needs before summer, which now, as climate effects like heat waves are intensifying, leaves many households without essential financial assistance to deal with higher electricity bills during the cooling season. And, unlike for some heating customers, there is currently no legal framework in Massachusetts which requires utilities to provide electricity service during heat waves in the instance of non-payment, and shutoffs are allowed. For low-income households, more likely to live in older buildings without central air conditioning or modern shading technology, as well as living in areas with less heat resistant infrastructure like parks and trees, the burden of heat and risk to health is larger. </p>

<p>Increases in Federal Funding for weatherization and electrification programs have been significant, but not enough. The state has recognized that incentivizing conversions to heat pumps and electrification will assist them in achieving their carbon goals. The Massachusetts Clean Energy and Climate Plan for 2025 and 2030 includes metrics for the adoption of heat pumps in the building sector – which implies a total 790,000 residential heat pumps operating in 2030, from an estimated 280,000 in 2020. According to Mass Save’s KPI documents, it appears that the incentive provides installed heat pumps for 10,594 customers in 2020, and 16,235 in 2021 (“Quarterly Reports – MA Energy Efficiency Advisory Council,” n.d.). Some may have been installed independently, but this is unknown. Heat pump installations are not the only method MassSave possesses to reach its goal for electrification, but it is the most common conversion. In order to reach the 2030 goal for 483,000 more electrified homes, MassSave will require an average of 70,000 installation of heat pumps per year from 2025 through 2030, a threefold increase of its current rate (“Quarterly Reports – MA Energy Efficiency Advisory Council,” n.d.; “Massachusetts Commission on Clean Heat Final Report” 2022). And, electricity rates are currently so steep in the Commonwealth, that for some customers, even with maximum rebates for heat pump conversions, converting to electricity is not a viable choice, as keeping their old heat sources is currently more cost effective than converting to electricity. If designed with equity in mind, the Massachusetts transition to a new energy economy could offer low-income households the opportunity to meet their energy requirements more affordably. </p>

<p>The limitations of this study include those faced by any residential energy consumption study, a lack of granular data. Alternative fuel type energy consumption data, or patterns of energy consumption by property type or by demographic would significantly enhance the ability of this study to correlate energy burden with socioeconomic factors or other indicators. This study also did not discuss the relationships between homeowners and renters, and their unique relationships to energy burden. Renters in large apartment buildings often do not pay their heating bills and instead have their cost of housing increased by landlords instead, which although some would still be eligible for LIHEAP funding, may result in different impacts on their lives than discussed here. Additionally, the analysis did not fully capture the seasonal variability of energy burdens, with seasonal pricing fluctuations and detailed energy rates by supplier too complex a layer to incorporate into this analysis. Data on the spread of energy efficiency programs were, regrettably, too limited, only available through part of 2020, offering only a glimpse into this of how they were distributed across the state. Also absent from this study is incorporating the results of the Massachusetts Consumer Study, to show how the competitive supply predatory pricing would have changed the estimated energy burdens.</p>

<p>Future research should try to bridge these gaps. Investigating the long-term effects of policies that target energy burdens like weatherization programs and heat pump conversions is important for crafting sustainable community and regulatory responses. Modelling the repercussions of energy price hikes and the demands of energy with increasing summer temperatures on energy burdens is also necessary. </p>



## Policy Recommendations
<p> The key finding of this analysis is that the energy burdens faced by Massachusetts’ communities have grown disproportionately heavy for low-income and minority communities, intensifying socioeconomic disparities. Heightened energy burdens from price shocks such as those experienced in 2022 undermines their resilience, limiting the ability of these communities to withstand and recover from economic stress. As the Commonwealth strides toward its decarbonization goals, impact on energy pricing may deepen these fissures between income groups. Current energy policies and lack of regulation of utilities and of the competitive supply market may continue to widen the gap between income groups, which demands regulatory attention. The current pace of clean energy technology conversions is wanting due to: the lack of funding, the high rates for electricity service from utilities disincentivizing ASHP adoption, the cost of conversions (even with rebates) being too high for lower income households, and the lack of community knowledge and information sharing on clean energy. Continuing now with business as usual will widen the energy efficiency gap and leave already cost-burdened families extremely vulnerable as their energy costs rise. At some point, enough electrification will have taken place, and enough clean energy will be procured by the State that the cost of electricity will decrease significantly, and the cost of using older heating technologies may increase exponentially. This will result in households who have maintained old heating technology at a significant disadvantage, to face even higher energy burdens than they already do. Higher income families, or those who have successfully converted to electric technologies will weather the energy pricing storm without risk. The following policy recommendations attempt to shrink burdens in a long-term capacity, reduce vulnerability to pricing shocks, and to reduce the energy efficiency gap between income groups: </p>

   * Regulate Energy Pricing: If unable to end the competitive supply market for electricity in the state, the Commonwealth must implement stricter oversight to prevent predatory pricing and business tactics ensure fairness in energy costs for all.
   * Expand Subsidies: Increase funding for home energy efficiency improvements targeted at low-income households as a long-term solution for reducing energy price shocks.
   * Expand short-term assistance: Increase LIHEAP funding to levels where cooling season demands of residents can be met.
   * Inclusive Community Outreach: Enhance outreach programs to ensure vulnerable populations are aware of resources and can avail necessary assistance without fear of deportation.
   * Equitable Infrastructure Upgrades: Advocate for policies that consider the financial capabilities of all residents.
   * Equitable Energy Transition: Advocate for clean energy upgrades which are available and affordable to all and that upgrades to high income residents do not inadvertently increase energy costs for low-income residents.

An increased energy burden does not just strain the economy by preventing households from spending money in other categories of goods; it is a substantial public health and social equity concern that undermines urban resilience by escalating community vulnerability to economic shocks. Community action programs are a crucial survival mechanism for families in Massachusetts, but their power and reach are insufficient to fully mitigate all of these challenges alone, which are increasing alongside the cost of living, higher energy costs, and increasing demand for energy as a whole. Improving energy efficiency and affordability directly contributes to community resilience, economic stability, and quality of life. 

***

*This research was conducted in April 2024. For access to the complete paper, including full statistical analyses and methodology details, please [contact me](mailto:baker.cole@northeastern.edu).*

***
## References

<p>Brown, Anna, Ashvin Dayal, and Cristina Rumbaitis del Rio. 2012. “From Practice to Theory: Emerging Lessons from Asia for Building Urban Climate Change Resilience.” Environment and Urbanization 24 (October): 531–56. https://doi.org/10.1177/0956247812456490.</p>

<p>Brown, Marilyn A., Anmol Soni, Ameet D. Doshi, and Charlotte King. 2020. “The Persistence of High Energy Burdens: A Bibliometric Analysis of Vulnerability, Poverty, and Exclusion in the United States.” Energy Research & Social Science 70 (December): 101756. https://doi.org/10.1016/j.erss.2020.101756.</p>

<p>Campanella, Thomas J. 2006. “Urban Resilience and the Recovery of New Orleans.” Journal of the American Planning Association 72 (2): 141–46. https://doi.org/10.1080/01944360608976734.</p>

<p>CBS Boston, dir. 2022. Home Heating Oil Prices Skyrocket. https://www.youtube.com/watch?v=fSDBEfW4nmw.</p>

<p>Choate, Jo-Ann, and Mark Wolfe. 2011. “National Energy Assistance Survey,” November.</p>

<p>Drehobl, Ariel, Lauren Ross, and Roxana Ayala. 2020. “An Assessment of National and Metropolitan Energy Burden across the United States.” American Council for an Energy-Efficient Economy, September.</p>
Food and Agriculture Organization. 2011. “Measuring Resilience.” 2011. https://www.fao.org/3/al920e/al920e00.pdf.</p>

<p>Fortin, Matt, and Staff Reports. 2022. “Some Mass. Residents See Utility Bills Triple. Here’s Why Rates Are Skyrocketing.” NBC Boston (blog). December 5, 2022. https://www.nbcboston.com/news/local/some-mass-residents-see-utility-bills-more-than-triple-heres-why-rates-are-skyrocketing/2911487/.</p>

<p>IER. 2024. “Massachusetts Utilities Ask for Rate Increases to Convert the Grid to Renewable Energy and Massive Electrification.” IER (blog). February 26, 2024. https://www.instituteforenergyresearch.org/the-grid/massachusetts-utilities-ask-for-rate-increases-to-convert-the-grid-to-renewable-energy-and-massive-electrification/.</p>

<p>“MACustomerProfile - Entities.” n.d. Accessed April 20, 2024. https://insight.dnv.com/MACustomerProfile?_gl=1*1mwa3qc*_ga*MTUyMzI1MDIyNi4xNzA4OTAzODQ4*_ga_DYYE3X0DZL*MTcxMzY0MDY3Mi4xLjEuMTcxMzY0MDY4Ni4wLjAuMA..</p>

<p>“Massachusetts Commission on Clean Heat Final Report.” 2022, November.</p>

<p>“Massachusetts Household Heating Costs | Mass.Gov.” n.d. Accessed April 20, 2024. https://www.mass.gov/info-details/massachusetts-household-heating-costs.</p>

<p>“MassGIS Data: Public Utility Service Providers | Mass.Gov.” n.d. Accessed April 20, 2024. https://www.mass.gov/info-details/massgis-data-public-utility-service-providers.</p>

<p>Maxim, Alexandra, and Emily Grubert. 2022. “Anticipating Climate-Related Changes to Residential Energy Burden in the United States: Advance Planning for Equity and Resilience.” Environmental Justice 15 (3): 139–48. https://doi.org/10.1089/env.2021.0056.</p>

<p>“Quarterly Reports – MA Energy Efficiency Advisory Council.” n.d. Accessed April 20, 2024. https://ma-eeac.org/results-reporting/quarterly-reports/.</p>

<p>Ribeiro, David. 2017. “Indicators for Local Energy Resilience,” June.</p>

<p>WCVB Channel 5 Boston. 2022. “Massachusetts Residents Face Sticker Shock with Home Heating Oil Prices.” Youtube. 2022. https://www.youtube.com/watch?v=J0Zh94WPmoI&t=1s.</p>

<p>Whitaker, Jeanette, Chaudry Modassar, Ekins Paul, Ramachandran Kannan, Shakoor Anser, Skea Jim, Strbac Goran, and Wang Xinxin. 2009. “Building a Resilient UK Energy System.” Working Paper REF UKERC/WP/ES/2009/023. UK Energy Research Centre. https://d2e1qxpsswcpgz.cloudfront.net/uploads/2020/03/building-a-resilient-uk-energy-system.pdf.</p>

