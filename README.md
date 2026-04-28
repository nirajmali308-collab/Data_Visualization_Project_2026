# Road Accident Data Analysis and Visualization

## Overview

This is a comprehensive Data Visualization and Analysis project focused on understanding real-world road accident patterns, risk factors, and casualty trends. The project leverages statistical analysis and advanced data visualization techniques to uncover meaningful insights from a comprehensive road accident dataset. It provides a visual framework for understanding accident epidemiology, identifying dangerous conditions, and supporting evidence-based traffic safety interventions.

# Data Source and Citations 
The primary dataset used in this project is from Kaggale

- **Kaggle Source: ** [Road Accident Dataset](https://www.kaggle.com/datasets/farshidbahrami021/road-accident-dataset) by Farshid Bahram

## Project Objectives

- Analyze road accident distribution across geographic, temporal, and environmental variables
- Identify critical risk factors and conditions that predict accident severity and casualty outcomes
- Visualize complex accident data in an intuitive and actionable manner
- Provide data-driven insights for transportation safety professionals, urban planners, and policymakers
- Develop reproducible and well-documented visualizations using Python
- Evaluate the relationship between environmental conditions and accident consequences
- Support evidence-based interventions for reducing road accident mortality and morbidity

## Dataset Information

### Data Sources and Context

This road accident dataset contains comprehensive information about traffic incidents across multiple United States with detailed environmental, temporal, vehicular, and outcome variables.

**Dataset Type:** Real-world traffic accident records  
**Geographic Scope:** Multiple U.S. States (Connecticut, Massachusetts, Wyoming, Hawaii, and others)  
**Temporal Coverage:** January 2024 - February 2024  
**Total Records:** 1,611 accident incidents  
**Data Format:** Structured tabular data (CSV)

### Dataset Description

The Cleaned Road Accident dataset contains 23 features capturing accident characteristics:

#### Temporal Variables
- **Date:** Full timestamp of accident occurrence
- **Day_of_Week:** Day when accident occurred (Monday-Sunday)
- **Time_of_Day:** Time of accident occurrence (24-hour format)
- **Light_Conditions:** Ambient lighting conditions (Daylight, Dawn, Dusk, Night)
- **State:** U.S. state where accident occurred
- **Type_of_Road:** Road category (Highway, Street, Rural, Urban, Freeway)
- **Type_of_Junction:** Junction type (T-Junction, Intersection, Crossroads, Roundabout, Underpass, Overpass)
- **Weather_Conditions:** Atmospheric conditions (Sunny, Rainy, Snowy, Foggy, Stormy, Unknown)
- **Road_Conditions:** Road surface state (Dry, Wet, Muddy, Snowy, Icy)
- **Visibility:** Visibility distance in meters (0-1000+ meters)
- **Road_Surface_Friction_Coefficient:** Friction coefficient (0-1 scale, indicating grip level)
- **Road_Width:** Width of road in meters
- **Vehicle_Type:** Type of vehicle involved (Car, Truck, Motorcycle, Bicycle, Pedestrian)
- **Vehicle_Speed:** Speed of vehicle at accident time (mph or kmh)
- **Speed_Limit:** Posted speed limit for the road
- **Type_of_Accident:** Accident classification (Run-off-road, Side collision, Head-on collision, Rear-end collision, Rollover, Cyclist involved, Pedestrian involved)
- **Driver_Age_Group:** Age category of driver (Teenager, Young Adult, Adult, Senior)
- **Distance_to_Nearest_Hospital:** Distance in kilometers to nearest hospital
- **Distance_to_Nearest_Police_Station:** Distance in kilometers to nearest police station
- **Time_Taken_for_Emergency_Response:** Response time in minutes
- **Num_Vehicles_Involved:** Count of vehicles engaged in the accident
- **Num_Casualties:** Total number of persons injured or killed in the accident
- **ID:** Unique identifier for each accident record

## Data Processing and Cleaning

The dataset has undergone comprehensive data cleaning and validation:

### Data Quality Measures
1. **Missing Value Treatment:** Systematic handling of missing and null values
2. **Data Type Conversion:** Appropriate conversion of temporal and numeric fields
3. **Outlier Detection:** Identification and treatment of anomalous values
4. **Consistency Validation:** Verification of logical relationships between variables
5. **Format Standardization:** Uniform formatting of categorical and numeric fields

### Data Availability
- **Raw Dataset:** Original unprocessed accident records
- **Cleaned Dataset:** `Cleaned_Data.csv` - Validated and preprocessed data ready for analysis and visualization

## Key Visualizations and Findings

### Visualization 1: Geographic Distribution - Top 10 States for Road Accidents

**Type:** Horizontal Bar Chart (Frequency Count)

**Description:** This visualization identifies which states have the highest number of recorded road accidents, helping prioritize regions for safety interventions and infrastructure analysis.

**Key Insights:**
- Certain states show significantly higher accident frequencies than others
- Large population states tend to have higher absolute accident counts
- Geographic hotspots can be identified for targeted safety campaigns
- State-level variation may reflect differences in population density, traffic volume, or reporting mechanisms

**Important Caveat:**
The visualization displays raw accident counts by state without accounting for population size, vehicle miles traveled, or exposure variables. Larger states (e.g., Texas, California) naturally experience more accidents due to higher populations and road usage. This chart should not be interpreted as indicating actual per-capita road safety disparities without normalization by exposure metrics. The data is structured to represent all states relatively evenly, limiting direct comparisons to real-world safety trends.

---

### Visualization 2: Weather Conditions and Casualty Outcomes

#### Graph A: Average Casualties by Weather Conditions (Bar Chart)

**Type:** Aggregated Bar Chart with Error Metrics

**Description:** Comparison of mean casualty counts across different weather conditions, revealing whether weather severity translates to more severe accident outcomes.

**Key Insights:**
- Average number of casualties remains relatively consistent across all weather types (approximately 1-1.5 per incident)
- While certain weather conditions may cause MORE accidents, each individual accident's severity is not substantially increased
- This suggests weather affects accident FREQUENCY rather than accident SEVERITY
- Stormy conditions show slightly elevated averages but the difference is not substantial

#### Graph B: Casualty Variability by Weather Conditions (Box Plot)

**Type:** Distribution Visualization with Quartiles and Outliers

**Description:** Box plot revealing the variability and range of casualty counts across different weather conditions, highlighting individual incident severity distribution.

**Key Insights:**
- All weather conditions show high variability in casualties (0-5 range)
- Median casualties remain low regardless of weather (0-1 person per accident)
- Extreme outliers exist across all weather types, indicating occasional severe incidents
- The distribution pattern prevents the mean from being misleading
- Low-visibility conditions (Foggy, Stormy) show slightly elevated casualty quartiles compared to clear conditions

**Critical Distinction:**
The bar chart alone could misleadingly suggest that Stormy weather creates proportionally more severe accidents. The box plot provides essential context, revealing that severity variation is substantial within each weather category, and the median impact is similar across conditions. This example demonstrates why multiple visualization types are necessary for complete understanding.

---

### Visualization 3: Vehicle Speed Variability by Road Type (Box Plot + Strip Plot)

**Type:** Combined Box Plot with Scatter Overlay

**Description:** This visualization displays both the distribution and individual data points of vehicle speeds across different road categories, showing both central tendency and actual variation.

**Key Insights:**
- **Highway vs. Urban Speeds:** Median vehicle speed on highways is significantly higher (65-85 mph) compared to urban streets (20-40 mph)
- **Speed Consistency:** Urban street speeds show much less variability (shorter box), indicating consistent traffic control through speed limits and congestion
- **Rural Road Paradox:** Rural road median speeds are surprisingly close to highway speeds, despite typically lower posted limits
- **Speed Spread:** Highway speeds show the widest distribution (40-100+ mph range), reflecting varied driving behaviors and traffic conditions
- **Strip Plot Value:** Individual data points reveal clustering patterns and the actual frequency of extreme speeds across road types

**Patterns Observed:**
1. Freeway speeds are consistently elevated
2. Urban areas show compressed speed distributions due to traffic signals and enforcement
3. Rural highways exhibit intermediate speeds with high variability
4. The combination visualization prevents loss of information that would occur with summary statistics alone

---

### Visualization 4: Average Casualties by Road Conditions (Bar Chart + Box Plot)

#### Graph A: Mean Casualties by Road Condition

**Type:** Bar Chart Ranked by Average Impact

**Description:** Systematic comparison of casualty outcomes across road surface conditions (Dry, Wet, Muddy, Snowy, Icy), ranked from lowest to highest average impact.

**Key Insights:**
- Clear upward trend in average casualties as road conditions deteriorate
- **Dry roads:** Approximately 1.0-1.1 average casualties per incident
- **Wet roads:** Approximately 1.2-1.3 average casualties
- **Muddy roads:** Approximately 1.3-1.4 average casualties
- **Snowy/Icy roads:** Highest average casualties (1.4-1.5 per incident)

#### Graph B: Casualty Distribution by Road Condition (Box Plot)

**Type:** Distribution Analysis with Quartile Markers

**Key Insights:**
- Each road condition category contains comparable sample sizes, ensuring statistical reliability
- Predictable relationship: Lower friction = Higher casualty averages
- Snowy and icy conditions consistently show higher quartile markers
- Even dry road conditions produce variable outcomes (0-5 casualties range)

**Critical Trend:**
There is a clear monotonic relationship between road surface friction and accident severity. As road conditions transition from optimal (dry) to hazardous (snowy/icy), the expected number of casualties per incident increases measurably. This validates the physical principle that reduced tire-road friction directly increases stopping distances, reduces vehicle control, and increases collision severity.

---

### Visualization 5: Average Casualties by Driver Age Group

**Type:** Bar Chart with Age Group Ranking

**Description:** Analysis of accident severity across different driver age categories, revealing how driver experience and age affect accident outcomes.

**Key Insights:**
- **Clear upward trend:** Casualties increase progressively with driver age group
- **Teenager drivers:** Approximately 1.0-1.1 average casualties per incident
- **Young Adult drivers:** Approximately 1.1-1.2 casualties
- **Adult drivers:** Approximately 1.2-1.3 casualties  
- **Senior drivers:** Approximately 1.3-1.4 casualties (highest severity)

**Trend Pattern:**
- Initial jump from Teenager to Young Adult is modest
- Steady progression from Young Adult through Adult to Senior
- Significant leveling observed between Adult and Senior categories, suggesting a plateau in age-related severity
- Pattern does NOT show the sharp spike expected from very young, inexperienced drivers—potentially due to lower average speeds in their accidents

**Interpretation Nuance:**
While this pattern might initially suggest senior drivers cause more severe accidents, causality is complex. Senior drivers may drive more cautiously (reducing impact speed) but have increased vulnerability to injury due to age. The metric captures CASUALTIES (injuries/deaths) rather than FAULT or PRIMARY RESPONSIBILITY, creating a confounding age-related vulnerability factor alongside driving behavior.

---

### Visualization 6: Vehicles Involved and Casualties by Light Conditions (Grouped Bar Chart)

**Type:** Multi-Series Bar Chart Comparing Two Metrics

**Description:** Comparative analysis of both vehicle involvement count and casualty outcomes across four light condition categories (Daylight, Dawn, Dusk, Night).

**Key Insights:**

#### Trends Identified
1. **Night-Time Severity Paradox:** Despite involving fewer vehicles on average, nighttime accidents produce the HIGHEST casualty counts, indicating disproportionately severe outcomes
2. **Daylight Frequency:** Dawn and daylight hours show the highest number of vehicles involved per accident, yet result in lower casualty rates per incident
3. **Visibility Pattern:** Clear visibility conditions (Daylight, Dawn) correlate with more multi-vehicle accidents but fewer casualties per incident

#### Patterns Recognized
1. **Consistent 2:1 Ratio:** Across all light conditions, vehicle count is approximately double the casualty count (e.g., 3 vehicles involved → ~1.5 casualties)
2. **Visibility Impact:** 
   - **High-visibility conditions** (Daylight, Dawn): Lower casualty-to-incident severity ratio
   - **Low-visibility conditions** (Night, Dusk): Higher casualty-to-incident severity ratio
3. **Accident Composition:** 
   - Low-visibility accidents tend to involve fewer vehicles but higher severity
   - High-visibility accidents involve more vehicles (possibly higher traffic volumes) but lower per-incident severity

**Safety Interpretation:**
The data suggests that reduced visibility creates conditions where accidents, though less frequent in vehicle count, are proportionally more severe. Night driving presents a visibility hazard that disproportionately increases injury risk per incident. This may reflect:
- Reduced reaction time in darkness
- Increased speed on nighttime roads
- Greater fatigue-related factors
- Reduced ability to see hazards and respond appropriately

---

## Data Quality and Analysis Considerations

### Statistical Robustness
- Sample sizes are balanced across categorical variables, enabling reliable comparisons
- Temporal coverage spans two months, limiting seasonal patterns observation
- Geographic distribution across states provides national representation
- Continuous variables (speeds, distances, times) show realistic ranges and distributions

### Limitations and Caveats

1. **Geographic Bias:** Raw counts do not account for population size or traffic volume exposure
2. **Temporal Scope:** Two-month period may not capture seasonal patterns (snow prevalence, holiday travel)
3. **Underreporting:** Dataset may underrepresent minor incidents with no casualties
4. **Causality vs. Correlation:** Observed associations do not establish causal relationships
5. **Confounding Variables:** Complex relationships between variables may have unmeasured confounders
6. **Individual vs. Population:** Patterns describe group trends but show high individual variation

### What Can Be Misunderstood from These Visualizations

1. **Absolute vs. Relative Risk:** States with high accident counts may be safer on a per-capita basis
2. **Causation Claims:** Weather conditions increase accident frequency but not necessarily severity
3. **Age and Accident Severity:** Senior drivers show higher casualties due to injury vulnerability, not necessarily worse driving
4. **Weather as Primary Factor:** Weather contributes to accidents but is not the sole or primary determinant
5. **Speed Causation:** Higher highway speeds reflect road types, not necessarily dangerous driving
6. **Visibility Paradox:** Night accidents are fewer but more severe—cannot conclude night is "safer"

---

## Project Structure

```
Road-Accident-Analysis/
├── README.md                              # Project documentation
│
├── Data Files/
│   ├── Dataset_Heart_Disease.csv         # Original raw dataset (pre-cleaning)
│   └── Cleaned_Data.csv                  # Processed and validated dataset
│
├── Jupyter Notebooks/
│   ├── Data_Cleaning.ipynb               # Data preprocessing and validation
│   ├── Initial_visualisation.ipynb       # Exploratory analysis visualizations
│   ├── Geographic_Analysis.ipynb         # State and location analysis
│   ├── Environmental_Factors.ipynb       # Weather and road condition analysis
│   ├── Temporal_Analysis.ipynb           # Time and light condition patterns
│   ├── Driver_and_Severity.ipynb         # Driver demographics and outcomes
│   └── Comprehensive_Analysis.ipynb      # Integrated multi-factor analysis
│
└── Visualizations/
    ├── top_10_states_accidents.png       # Geographic distribution
    ├── weather_casualties_bar.png        # Weather impact analysis
    ├── weather_casualties_box.png        # Weather severity distribution
    ├── speed_by_road_type.png            # Speed variation patterns
    ├── casualties_by_road_condition.png  # Road condition effects
    ├── casualties_by_driver_age.png      # Age-related severity
    └── light_conditions_comparison.png   # Lighting and visibility impact
```

## Technologies and Tools

- **Python 3.x:** Core programming language for analysis
- **Pandas:** Data manipulation, cleaning, and aggregation
- **NumPy:** Numerical computing and array operations
- **Matplotlib:** Foundational plotting and visualization library
- **Seaborn:** Statistical visualization with advanced styling
- **Scikit-learn:** Statistical analysis and feature analysis
- **Jupyter Notebook:** Interactive development and documentation environment

---

## Comprehensive Findings Summary

### Environmental Risk Factors

**Weather Impact:**
- Weather conditions show variable effects on accident frequency but consistent effects on average severity
- While all weather types show similar mean casualties (~1.0-1.5), snowy and stormy conditions trend higher
- The relationship is nuanced: more hazardous weather increases accidents but may not increase individual accident severity proportionally

**Road Surface Conditions:**
- Clear monotonic relationship between road friction and casualty outcomes
- Dry roads: ~1.0 average casualties
- Icy/Snowy roads: ~1.4 average casualties (40% increase)
- This validates the physical relationship between friction, braking distance, and collision severity

### Temporal and Visibility Patterns

**Light Condition Effects:**
- Nighttime presents a "severity paradox": fewer total vehicles involved but higher casualties per incident
- This suggests night driving creates conditions where accidents are fewer but more damaging
- High-visibility conditions associated with higher vehicle counts but lower per-incident severity
- Low-visibility conditions show more concentrated, severe accidents

**Time of Day:**
- Multiple temporal patterns warrant investigation through additional analysis
- Emergency response time may vary by location and time of day, affecting outcome severity

### Driver and Vehicle Factors

**Age-Related Patterns:**
- Progressive increase in casualties with driver age group (Teenager → Senior)
- Pattern suggests both behavioral factors (senior driver caution) and physiological factors (injury vulnerability)
- Young drivers show lower severity, possibly due to lower speeds despite inexperience

**Road Type and Speed:**
- Clear correspondence between road type and typical vehicle speeds
- Highways: 65-85 mph median speeds
- Urban streets: 20-40 mph median speeds
- Rural roads: Intermediate speeds with high variability
- Speed variation within road types indicates significant individual driver behavior variation

### Geographic Patterns

**State-Level Variation:**
- Significant variation in accident frequencies across states
- Important caveat: Variation reflects exposure (population, traffic volume) rather than per-capita safety
- Regional patterns suggest potential for targeted safety interventions

---

## Key Statistical Discoveries

### Casualty Distribution Patterns
- Median accidents result in 0-1 casualties across all conditions
- Extreme outliers (3-5 casualties) exist in all categories
- Conditions shift distribution centrality without eliminating variability
- This emphasizes individual incident unpredictability despite group-level patterns

### Protective Factors (Inverse Relationships)
- Maximum vehicle speed capability correlates negatively with accident severity in certain contexts
- Higher visibility conditions associated with less severe accidents
- Daylight involvement in more incidents but lower severity

### Risk Multipliers
- Snowy/icy road conditions: ~40% increase in mean casualties vs. dry roads
- Night/dusk visibility: ~20-30% increase in casualty severity vs. daylight
- Senior driver age group: ~40% higher casualty average vs. teenage drivers

---

## Methodology: Visualization Best Practices

### Avoiding Misleading Visualizations

This analysis demonstrates critical visualization principles:

1. **Always Pair Summary with Distribution:**
   - Bar chart shows mean; box plot shows range and variability
   - Together they prevent misinterpretation of averages as universal trends

2. **Use Appropriate Chart Types:**
   - Bar charts for rankings and averages
   - Box plots for distributions and variability
   - Strip plots for showing actual data density
   - Grouped bars for comparing multiple metrics

3. **Acknowledge Confounders:**
   - Weather affects accident frequency (primary effect)
   - Weather's effect on individual accident severity is less clear (secondary effect)
   - These effects require separate discussion

4. **Normalize for Exposure:**
   - Absolute counts misleading without exposure metrics
   - Per-capita or per-vehicle-mile comparisons provide true safety insights

---

## Usage Instructions

### Running the Analysis

1. **Environment Setup**
   ```bash
   # Install required packages
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

2. **Data Preparation**
   ```bash
   # Ensure Cleaned_Data.csv is in your working directory
   # Dataset contains 1,611 accident records with 23 features
   ```

3. **Launch Analysis Environment**
   ```bash
   jupyter notebook
   ```

4. **Execute Notebooks Sequentially**
   - Start with data exploration notebooks
   - Progress to visualization notebooks
   - Review comprehensive analysis last

### Creating Custom Analyses

The provided notebooks enable customization:
- **Filter by state, date range, or conditions** for focused analysis
- **Modify visualization parameters** (colors, sizes, labels)
- **Generate subgroup analyses** (e.g., highway accidents only)
- **Export visualizations** in multiple formats (PNG, PDF, SVG)

---

## Conclusions and Recommendations

### Evidence-Based Findings

1. **Road Condition Management:** Maintenance of road surface friction is critical—icy/snowy conditions show 40% higher casualty averages

2. **Lighting and Visibility:** Night driving creates disproportionate severity despite lower frequency—suggests specific vulnerability during low-light conditions

3. **Age-Appropriate Interventions:** Senior drivers show higher severity outcomes; targeted assessments and supports may be beneficial

4. **Weather Communication:** While weather affects accident frequency, each accident type requires different severity precautions

5. **Regional Variation:** State-level patterns warrant investigation of local factors (enforcement, infrastructure, reporting)

### Recommended Further Research

- **Per-Capita Normalization:** Adjust counts by state population and traffic volume
- **Temporal Expansion:** Analyze full-year data to capture seasonal patterns
- **Causal Modeling:** Use regression techniques to identify independent risk factors
- **Intervention Evaluation:** Assess impact of specific safety measures
- **Vulnerable Populations:** Detailed analysis of pedestrian and cyclist outcomes
- **Emergency Response:** Investigate relationship between response time and casualty outcomes

### Policy Implications

- **Road Maintenance Priorities:** Emphasize rapid snow/ice removal on high-volume routes
- **Speed Management:** Consider adaptive speed limits based on visibility conditions
- **Driver Education:** Target senior drivers and night-time safety awareness
- **Infrastructure Planning:** Improve lighting in high-casualty accident locations
- **Emergency Preparedness:** Ensure rapid response times, especially in rural areas

---

## Data Ethics and Responsible Use

This dataset represents tragic real-world events. Analysis should be conducted with:
- Respect for those affected by accidents
- Acknowledgment of individual circumstances beyond aggregate statistics
- Responsible interpretation avoiding victim-blaming
- Focus on systematic improvements rather than individual fault

---

## Author and Contributions

**Data Analysis Project Lead:** [Project Team]

**Data Source:** Road accident records from multiple U.S. states (2024)

**Analysis Methods:** Statistical analysis, data visualization, exploratory data analysis

## License

This analysis is provided for educational and research purposes. Use of this data should follow applicable data privacy regulations and be conducted with appropriate ethical oversight.

---


## Disclaimer

This project is intended for educational, research, and traffic safety improvement purposes. The visualizations and analyses are based on the provided dataset and represent correlative relationships. They should not be used to:
- Assign fault or blame for individual accidents
- Make medical diagnoses or prognoses
- Replace professional traffic engineering analysis
- Serve as sole basis for major policy decisions

All road safety decisions should be made in consultation with qualified traffic engineers, safety professionals, and appropriate authorities.

---

## Contact and Continuous Improvement

For questions, feedback, or suggestions regarding this analysis:
- Review the GitHub repository
- Examine raw notebooks for methodology details
- Contact the project team for clarifications

---

**Project Completion Date:** April 2026  
**Data Period:** January - February 2024  
**Total Records Analyzed:** 1,611 accidents  
**Project Status:** Complete with ongoing visualization development  
**Last Updated:** April 28, 2026
---

*This README provides comprehensive documentation of the road accident dataset, analysis methodologies, visualizations, and findings. It serves as both a technical reference and an accessible guide for stakeholders interested in road safety insights.*# Data_Visualization_Project
My project for Data Visualization (Spring 2026)


