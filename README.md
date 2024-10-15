
# Earthquake Analysis

Earthquakes, a testament to the immense power hidden beneath our feet, have captivated and terrified humanity for millennia. These seismic events, though destructive, hold a fascinating complexity that begs to be understood. This project delves into the depths of historical earthquake data, leveraging the flexibility of Python and the power of machine learning to uncover hidden patterns and explore the potential for predicting earthquake magnitude.

Link for my [Portfolio(Earthquake Analysis)](https://vijaikumarsvk.github.io/Earthquake-Analysis)

## Data and Methodology
Our journey begins with a rich dataset sourced from [Pakistan Meteorological Department.](https://seismic.pmd.gov.pk/)

Documenting a comprehensive record of earthquakes around the world. Each entry in the dataset captures key characteristics of an earthquake, including:

1. **Date and Time:** Pinpointing when the earthquake struck.

2. **Region:** Providing a general location of the seismic event.

3. **Magnitude:** Quantifying the earthquake's energy release on the Richter scale.

4. **Depth** Indicating the depth below the Earth’s surface where the earthquake originated.

5. **Latitude and Longitude:** Precisely mapping the earthquake's epicenter.

Before embarking on our analysis, the raw data underwent a refinement process:

- **Date Transformation:** To facilitate temporal analysis, the 'Date' column, initially stored as text, was converted into a datetime object using pd.to_datetime().

- **Numerical Extraction:** Latitude and Longitude information, embedded within strings, were extracted and converted to numerical values, preparing them for further analysis.

## Exploratory Data Analysis

Armed with a clean and structured dataset, we embarked on Exploratory Data Analysis (EDA), a crucial step in any data science endeavor. EDA allows us to unravel the story hidden within the numbers, revealing intriguing patterns and relationships.

#### Temporal Analysis: Earthquakes Through Time
Visualizing earthquake occurrences over time unveils the dynamic nature of our planet. By plotting earthquake frequency across years, months, and even hours, we gain valuable insights into temporal trends and potential seasonality.

![alt text](https://res.cloudinary.com/dqqjik4em/image/upload/v1729006420/Year_wise_EQ.jpg)
![alt text](https://res.cloudinary.com/dqqjik4em/image/upload/v1729006645/Month_wise_EQ.jpg)

#### Regional Insights: Where do Earthquakes occurs more?

Investigating earthquake magnitudes by region highlights the uneven distribution of seismic activity across the globe. By calculating average magnitudes for each region, we can identify areas prone to more powerful earthquakes and those relatively calmer.

![alt text](https://res.cloudinary.com/dqqjik4em/image/upload/v1729007252/Country_wise_EQ.jpg)

#### Depth vs. Magnitude
Delving deeper, we explored the relationship between an earthquake’s depth and its magnitude. A scatter plot, visualizing these two variables, provides insights into whether deeper earthquakes tend to be more or less intense.

![alt text](https://res.cloudinary.com/dqqjik4em/image/upload/v1729008035/Dp_Vs_mag_wise_EQ.jpg)

#### Detection Methods
Analyzing the distribution of earthquake detection methods — automatic vs. manual — offers a glimpse into how these events are captured and verified. Understanding the prevalence of each method sheds light on potential biases or inconsistencies in the data.

![alt text](https://res.cloudinary.com/dqqjik4em/image/upload/v1729008228/Detection_method.jpg)


## Feature Engineering
Feature engineering is for transforming raw data into a format suitable for machine learning algorithms. This crucial step often involves creating new features from existing ones to enhance the model's predictive power. In our analysis, we engineered two new features:

- **Hour of the Day:** Recognizing that earthquake occurrences might exhibit diurnal patterns, we extracted the hour from the time column. This feature could reveal if earthquakes are more likely to strike at certain times.

- **Country:** Using a Geocoding API, we mapped the latitude and longitude of each earthquake to its corresponding country. This added geographical context could unveil regional variations in earthquake frequency and magnitude.

## Predictive Modeling

With our data fortified with insightful features, we set out to build a machine learning model capable of predicting earthquake magnitude. For this task, we chose the Random Forest Regressor, a robust algorithm well-suited for handling complex, non-linear relationships in data.

The model training involved splitting the dataset into training and testing sets. The Random Forest was trained on the training set and its performance evaluated on the unseen testing set using:

- **Mean Squared Error (MSE):** Quantifies the average squared difference between predicted and actual magnitudes. Lower MSE values indicate better model accuracy. **MSE Score: 15.68%**

- **R-squared (R2) Score:** Using a Geocoding API, we mapped the latitude and longitude of each earthquake to its corresponding country. This added geographical context could unveil regional variations in earthquake frequency and magnitude. **R2 Score: 92.17%**

## Conclusion and Looking Ahead
This analysis has provided valuable insights into earthquake patterns and the potential for predicting their magnitude. We've uncovered temporal trends, regional variations, and relationships between depth and magnitude, showcasing the power of data exploration. Our predictive model, while a promising start, can be further enhanced through.


1. **Expanded Datasets:** Incorporating a larger dataset with a wider temporal and geographical scope can improve model accuracy and generalizability.

2. **Additional Features:** Adding features like fault line proximity, soil types, and tectonic plate movements can provide valuable geological context for prediction.

3. **Algorithm Exploration:** Exploring alternative machine learning algorithms, such as gradient boosting or neural networks, might unlock even greater predictive power.

The ability to forecast earthquakes holds immense potential for disaster preparedness, infrastructure planning, and ultimately, saving lives. This exploration serves as a stepping stone towards a future where we can better anticipate and mitigate the impacts of these powerful natural events.