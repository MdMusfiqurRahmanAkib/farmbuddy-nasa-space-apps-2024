# FarmBuddy

Data-driven farming support with NASA Earth observation data and AI.

FarmBuddy is the project our team, **Team Proborton**, built for the **NASA Space Apps Challenge 2024**, where it received NASA's **Galactic Problem Solver** recognition.

Farmers make big decisions with very little information: when to plant, what to grow, how to deal with a sick crop, and what to do with land that sits unused. FarmBuddy brings weather, soil and crop information together in one place, so those decisions can be based on data. The site works in both English and Bangla.

**Live site:** https://mdmusfiqurrahmanakib.github.io/farmbuddy-nasa-space-apps-2024/

## Features

| Feature | What it does |
| --- | --- |
| Predictive climate analytics | Estimates the risk of flood, deluge and drought from rainfall, temperature, humidity, soil moisture and river levels with a Random Forest model, and explains the reason behind each prediction. |
| Soil health and crop suitability | Shows soil health and moisture information and suggests suitable crops and fertilisers. |
| AI plant disease detection | Upload a photo of a leaf and a deep learning model identifies the disease (corn common rust, potato blight or tomato bacterial spot) with a treatment note. |
| Land utilisation | A marketplace where landowners can list unused fertile land for lease, so it can be farmed. |
| English and Bangla | Switch the whole site between the two languages with one click. |

## Built with

- **Frontend:** HTML, Tailwind CSS, JavaScript, Chart.js, Font Awesome
- **Backend:** Python, Flask, TensorFlow and Keras, OpenCV, scikit-learn, pandas
- **Data:** NASA SMAP soil moisture and NASA Earthdata

## Project structure

```
index.html                          home page
predictive-climate-analytics.html   climate risk dashboard
soil-health-assessment.html         soil health and crop suitability
plant-disease-detection.html        upload a leaf image for diagnosis
land-utilization.html               land leasing marketplace
about.html, contact.html, login.html
css/, js/, images/                  styles, scripts (including the language switcher) and images
backend/
    plant_disease_api.py            Flask API for disease detection (POST /predict)
    climate_analytics_api.py        Flask API for climate risk analysis (POST /run_analysis)
    models/plant_disease_model.h5   trained disease detection model
    data/weather_data.csv           sample weather and soil data
    requirements.txt
```

## How to run

**Website:** open `index.html` in a browser, or use the live site above.

**Plant disease detection** needs the Python backend running on your computer:

```bash
pip install -r backend/requirements.txt
```

```bash
python backend/plant_disease_api.py
```

The API starts at http://127.0.0.1:5000, which is the address the disease detection page calls.

**Climate risk analysis** has its own API:

```bash
python backend/climate_analytics_api.py
```

Both APIs use port 5000 by default, so run one at a time.

## Notes

FarmBuddy was built in a weekend for a hackathon. The weather dataset and the land listings are samples for the demo, and the disease model covers three diseases.

## Team Proborton

- Md. Musfiqur Rahman Akib
- Samah Feroz ([@SamahFeroz](https://github.com/SamahFeroz))
- Tanvir Joy ([@thisistanvirjoy](https://github.com/thisistanvirjoy))

The original hackathon repository is [SamahFeroz/Team-Proborton](https://github.com/SamahFeroz/Team-Proborton). This copy keeps its full commit history and organises the files for easier use.
