# Weather Data Analysis Dashboard
<img width="630" height="400" alt="image" src="https://github.com/user-attachments/assets/b5fbff01-86c7-4af7-87f7-b7a8b781214d" />
<img width="630" height="400" alt="image" src="https://github.com/user-attachments/assets/a265bebe-453c-4213-b9c5-f09de709c671" />


## 📊 Project Overview

This project is a comprehensive **Weather Data Analysis Dashboard** built using **Power BI** and integrated with **WeatherAPI**. The dashboard provides real-time weather information, air quality indices, and forecast data for multiple cities, presented through an interactive and visually appealing interface with modern glassmorphism design.

## 🎯 Project Objectives

The primary goal of this project is to create a dynamic, real-time weather monitoring system that:
- Fetches live weather data from WeatherAPI.com
- Visualizes current weather conditions and forecasts
- Tracks air quality metrics across different pollutants
- Provides location-based weather insights
- Enables easy comparison between multiple cities

## ✨ Key Features

### 🌡️ Real-Time Weather Monitoring
- **Current Temperature** with weather condition status (Mist, Clear, Rain, etc.)
- **Humidity Levels** tracking moisture in the atmosphere
- **Wind Speed** measurements in Km/h
- **Visibility** distance measurements
- **Atmospheric Pressure** readings
- **UV Index** for sun exposure awareness
- **Precipitation** tracking (rainfall data)

### 📈 Weather Forecast
- **7-Day Weather Forecast** with daily temperature predictions
- **Temperature Trend Graph** showing forecast patterns
- Visual representation of temperature variations throughout the week
- Weather condition icons for each forecasted day

### 🌫️ Air Quality Index (AQI) Dashboard
Comprehensive air quality monitoring with multiple pollutant tracking:
- **PM10** (Particulate Matter 10)
- **PM2.5** (Particulate Matter 2.5)
- **O3** (Ozone levels)
- **SO2** (Sulfur Dioxide)
- **NO2** (Nitrogen Dioxide)
- **CO** (Carbon Monoxide)
- Overall **AQI Score** with color-coded indicators (Good/Moderate/Poor)

### 🌅 Sunrise & Sunset Information
- Daily sunrise time tracking
- Daily sunset time tracking
- Helps in planning outdoor activities

### 📍 Multi-City Support
- Quick switching between different cities
- Pre-configured cities with easy navigation
- Location-based data fetching

### 🎨 Modern UI/UX Design
- Clean glassmorphism design aesthetic
- Dark theme for comfortable viewing
- Intuitive card-based layout
- Color-coded visual indicators
- Responsive and professional appearance

### 📊 Chance of Rain Prediction
- Daily rain probability percentages
- Visual bar chart representation
- Weekly rain forecast tracking

## 🛠️ Technologies Used

### Core Technologies
- **Power BI Desktop** - Primary dashboard development tool
- **WeatherAPI.com** - Real-time weather data source
- **DAX (Data Analysis Expressions)** - Custom calculations and measures
- **Power Query (M Language)** - Data transformation and API integration

### Data Processing
- JSON format data parsing
- Web connector for API calls
- Dynamic data refresh capabilities
- Data modeling and relationships

## 📋 Prerequisites

Before setting up this project, ensure you have:

1. **Power BI Desktop** (Latest version recommended)
   - Download from: [Microsoft Power BI](https://powerbi.microsoft.com/desktop/)

2. **WeatherAPI Account & API Key**
   - Sign up at: [WeatherAPI.com](https://www.weatherapi.com/)
   - Free tier available with sufficient API calls for testing
   - API key required for authentication

3. **Basic Knowledge**
   - Understanding of Power BI interface
   - Familiarity with data visualization concepts
   - Basic understanding of REST APIs (helpful but not mandatory)

## 🚀 Installation & Setup

### Step 1: Get Your WeatherAPI Key

1. Visit [WeatherAPI.com](https://www.weatherapi.com/)
2. Create a free account
3. Navigate to your dashboard
4. Copy your API key (keep it secure)

### Step 2: Configure Power BI Data Source

1. Open Power BI Desktop
2. Click **Get Data** → **Web**
3. Enter the WeatherAPI URL:
   ```
   https://api.weatherapi.com/v1/forecast.json?key=YOUR_API_KEY&q=CITY_NAME&days=7&aqi=yes
   ```
4. Replace `YOUR_API_KEY` with your actual API key
5. Replace `CITY_NAME` with your desired location

### Step 3: Data Transformation

1. In Power Query Editor:
   - Expand the JSON structure
   - Navigate through nested records:
     - `current` → Current weather data
     - `forecast` → Forecast data
     - `location` → Location information
     - `air_quality` → AQI metrics
   
2. Rename columns for clarity:
   - `temp_c` → Temperature
   - `humidity` → Humidity
   - `wind_kph` → Wind Speed
   - etc.

3. Set appropriate data types:
   - Numbers for temperature, humidity, wind speed
   - Date/Time for forecast timestamps
   - Text for location names and conditions

4. Click **Close & Apply**

### Step 4: Create DAX Measures

Create calculated measures for enhanced functionality:

```dax
// Current Temperature with unit
Current Temperature = 
FORMAT([Temperature], "0.0") & "°C"

// AQI Status
AQI Status = 
SWITCH(
    TRUE(),
    [PM10] <= 50, "Good",
    [PM10] <= 100, "Moderate",
    [PM10] <= 150, "Unhealthy for Sensitive Groups",
    [PM10] <= 200, "Unhealthy",
    [PM10] <= 300, "Very Unhealthy",
    "Hazardous"
)

// Rain Probability Formatting
Rain Chance = 
FORMAT([chance_of_rain], "0.00%")
```

### Step 5: Build Visualizations

1. **Main Temperature Card**
   - Use Card visual
   - Display current temperature
   - Add location and condition as titles
   - Apply custom formatting with orange gradient

2. **Weather Metrics Cards**
   - Humidity, Wind Speed, Visibility, Pressure
   - UV Index, Precipitation
   - Use icons for visual appeal

3. **Forecast Line Chart**
   - X-axis: Days of the week
   - Y-axis: Temperature values
   - Add data labels
   - Format with appropriate colors

4. **AQI Gauge Visual**
   - Use Gauge or Donut chart
   - Color code based on AQI ranges
   - Display PM10 value prominently

5. **AQI Pollutants Cards**
   - Individual cards for each pollutant
   - Color coding: Green (Good), Yellow (Moderate), Red (Poor)

6. **Rain Probability Chart**
   - Horizontal bar chart
   - Show daily rain percentages
   - Color gradient from low to high probability

7. **City Selector**
   - Use buttons or slicers
   - Enable quick city switching
   - Apply parameters for dynamic API calls

## 📊 Dashboard Components

### Left Panel
- **City Name & Temperature Display**
- **Weather Condition Status**
- **Quick City Navigation Buttons**
- **Core Weather Metrics:**
  - Humidity percentage
  - Wind Speed
  - Visibility range
  - Atmospheric Pressure
  - UV Index
  - Precipitation amount

### Center Panel
- **7-Day Forecast Icons & Temperatures**
- **Temperature Trend Graph**
- **Air Quality Index (AQI) Gauge**
- **Individual Pollutant Readings:**
  - PM10, PM2.5, O3, SO2, NO2, CO

### Right Panel
- **Sunrise & Sunset Times**
- **Weekly Rain Probability Chart**
- **Date Indicators**

## 🔄 Data Refresh

### Manual Refresh
- Click **Refresh** button in Power BI Desktop
- Data updates from WeatherAPI in real-time

### Scheduled Refresh (Power BI Service)
1. Publish the report to Power BI Service
2. Configure dataset settings
3. Set up scheduled refresh:
   - Hourly, Daily, or Custom intervals
   - Ensure gateway configuration if required
   - Monitor refresh history for failures

### API Rate Limits
- Free tier: Check WeatherAPI limits
- Plan API calls accordingly
- Consider caching for frequently accessed data

## 🎨 Design Considerations

### Color Scheme
- **Primary Background:** Dark theme (#1a1a1a)
- **Accent Color:** Orange gradient (#FF6B35)
- **Card Backgrounds:** Semi-transparent with blur effect (glassmorphism)
- **Text Colors:** White and light gray for contrast
- **AQI Colors:**
  - Green: Good air quality
  - Yellow: Moderate air quality
  - Red: Poor air quality

### Typography
- **Headers:** Bold, large fonts for temperature
- **Body Text:** Clear, readable fonts for metrics
- **Icons:** Weather-specific icons for visual context

### Layout Principles
- Card-based modular design
- Logical grouping of related information
- Visual hierarchy emphasizing key metrics
- Responsive spacing and alignment

## 📈 Use Cases

This weather dashboard can be utilized for:

1. **Personal Weather Monitoring**
   - Daily weather tracking for planning activities
   - Travel preparation based on forecasts

2. **Business Applications**
   - Retail: Weather-based inventory planning
   - Agriculture: Crop management decisions
   - Logistics: Route planning based on conditions
   - Construction: Project scheduling

3. **Health & Safety**
   - Air quality monitoring for sensitive individuals
   - UV index tracking for outdoor workers
   - Storm preparedness

4. **Educational Projects**
   - Learning Power BI and API integration
   - Data visualization portfolio pieces
   - Teaching weather patterns and metrics

5. **Research & Analysis**
   - Climate trend studies
   - Correlation analysis with business metrics
   - Environmental monitoring

## 🎓 Learning Outcomes

By completing this project, you will learn:

- ✅ How to integrate external APIs with Power BI
- ✅ JSON data parsing and transformation
- ✅ Creating dynamic, parameter-based queries
- ✅ Building interactive visualizations
- ✅ Implementing custom DAX measures
- ✅ Modern UI/UX design in Power BI
- ✅ Data refresh and scheduling strategies
- ✅ Working with real-time data sources

## 🔧 Customization Options

### Adding More Cities
1. Create a parameter table with city names
2. Configure dynamic API URL using parameters
3. Add city selector slicer/buttons

### Additional Weather Metrics
- Feels like temperature
- Cloud cover percentage
- Moon phase information
- Historical weather comparison

### Advanced Features
- Weather alerts and notifications
- Multi-language support
- Custom weather animations
- Integration with other data sources (traffic, events)

## ❗ Troubleshooting

### Common Issues & Solutions

**Issue:** API authentication error
- **Solution:** Verify API key is correct and active
- Check WeatherAPI dashboard for usage limits

**Issue:** Data not refreshing
- **Solution:** Check internet connectivity
- Verify API endpoint URL is correct
- Review Power Query steps for errors

**Issue:** Incorrect data types
- **Solution:** Use Power Query to set proper data types
- Apply transformations before loading data

**Issue:** Visualizations not displaying
- **Solution:** Check field mappings in visual properties
- Ensure data model relationships are correct

**Issue:** Slow dashboard performance
- **Solution:** Reduce number of API calls
- Implement data caching
- Optimize DAX measures

## 📚 Additional Resources

### Official Documentation
- [WeatherAPI Documentation](https://www.weatherapi.com/docs/)
- [Power BI Documentation](https://docs.microsoft.com/power-bi/)
- [DAX Function Reference](https://docs.microsoft.com/dax/)
- [Power Query M Reference](https://docs.microsoft.com/powerquery-m/)

### Related Tutorials
- [How to Develop a Power BI Dashboard with WeatherAPI](https://thedeveloperyt.com/how-to-develop-a-power-bi-dashboard-with-weatherapi/)
- Power BI Community Forums
- WeatherAPI Examples and Use Cases

### Learning Resources
- Microsoft Power BI Learning Path
- DAX Patterns and Best Practices
- API Integration Tutorials

## 🤝 Contributing

Contributions are welcome! If you'd like to improve this project:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

Suggestions for improvements:
- Additional visualizations
- New weather metrics
- Performance optimizations
- UI/UX enhancements
- Documentation improvements

## 📄 License

This project is open-source and available under the MIT License. Feel free to use, modify, and distribute as needed.

## 🙏 Acknowledgments

- **WeatherAPI.com** for providing reliable weather data
- **Microsoft Power BI** team for the amazing visualization platform
- **Power BI Community** for inspiration and support
- **The Developer YT** for the comprehensive tutorial

## 📧 Contact & Support

For questions, suggestions, or support:
- GitHub Issues: [Create an issue]
- Email: [Your email]
- LinkedIn: [Your profile]

---

## 🌟 Project Statistics

- **Dashboard Pages:** 2 (Bangalore, Hyderabad) - Expandable to more cities
- **Visualizations:** 15+ interactive components
- **Data Sources:** WeatherAPI REST API
- **Refresh Frequency:** Configurable (Real-time capable)
- **Metrics Tracked:** 15+ weather and air quality parameters

---

**⭐ If you found this project helpful, please consider giving it a star!**

**📌 Last Updated:** December 2024

---

## 🎯 Project Status

✅ **Completed Features:**
- Real-time weather data integration
- Multi-city support
- Air quality monitoring
- 7-day forecast visualization
- Sunrise/sunset tracking
- Rain probability charts
- Modern glassmorphism UI

🚧 **Future Enhancements:**
- Historical weather data analysis
- Weather alerts and notifications
- Comparison mode for multiple cities
- Mobile-responsive design
- Export functionality for reports
- Integration with additional weather APIs

---

*Built with ❤️ using Power BI and WeatherAPI*

