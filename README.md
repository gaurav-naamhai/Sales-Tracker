# WeatherLens — Weather Impact Analysis Dashboard

A production-grade analytics dashboard built entirely in Python (Dash + Plotly).

## Features
- Temperature vs Sales scatter with regression line & rainfall colour encoding
- Rainfall vs Traffic scatter with correlation stats
- Seasonal heatmaps (Sales / Traffic)
- Monthly averages grouped bar chart
- Rain intensity % impact chart (5 buckets)
- Day × Week heatmap
- Interactive season filter & metric switcher

## Local Run
```bash
pip install -r requirements.txt
python app.py
# Open http://localhost:8050
```

## Deploy to Render (free tier)
1. Push this folder to a GitHub repo
2. New Web Service → connect repo
3. Build command: `pip install -r requirements.txt`
4. Start command: `gunicorn app:server`
5. Done ✅

## Deploy to Railway
```bash
railway init
railway up
```

## Deploy to Heroku
```bash
heroku create your-app-name
git push heroku main
```

## Swap in Real Data
Replace the synthetic generation block (lines 11–32 in app.py) with:
```python
df = pd.read_csv("your_data.csv", parse_dates=["date"])
```
Required columns: `date`, `temperature`, `rainfall`, `sales`, `traffic`
