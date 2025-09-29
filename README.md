# VIBE CODDED Option-Sentiment-Calculator
Analyze options chains to determine market sentiment with weighted scoring.

**⚠️ Disclaimer**: 
This tool is for educational and analytical purposes only. It should not be considered as financial advice. Always conduct your own research and consult with financial professionals before making investment decisions.

# Options Sentiment Calculator
A sophisticated web application for analyzing options chains to determine market sentiment using weighted scoring algorithms. This tool helps traders and analysts understand market positioning through comprehensive options flow analysis.

## 🚀 Features

### Core Analytics
- **Real-time Sentiment Scoring** - Composite sentiment score from -100 (bearish) to +100 (bullish)
- **Put/Call Ratio Analysis** - Volume and open interest ratio calculations
- **Time-weighted Analysis** - Near-term vs long-term sentiment differentiation
- **Implied Volatility Assessment** - Market fear/greed indicators

### Expiration Analysis
- **Multiple Time Frames** - Current month to 12-month LEAPS analysis
- **Term-specific Sentiment** - Separate calculations for different expiration periods
- **Time Decay Weighting** - Near-term options have amplified sentiment impact

### Visualizations
- **Interactive Charts** - Volume distribution and expiration analysis
- **Real-time Updates** - Dynamic calculations as you add data
- **Color-coded Sentiment** - Visual indicators for bullish/bearish/neutral states
- **Responsive Design** - Works seamlessly on desktop and mobile

### Web Server (Recommended)
For best performance, serve the files through a web server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server

# Using PHP
php -S localhost:8000
```

Then navigate to `http://localhost:8000`

## 📊 How to Use

### Adding Options Data
1. **Select Option Type** - Choose Call or Put
2. **Set Expiration Period** - From current month to 12-month LEAPS
3. **Enter Strike Price** - The option's strike price
4. **Input Volume** - Trading volume for the session
5. **Add Open Interest** - Outstanding contracts
6. **Set Implied Volatility** - IV percentage
7. Click **"Add Option"** to include in analysis

### Sample Data
Use the provided sample buttons to see the calculator in action:
- **Bullish Sample** - Heavy call volume, low put/call ratios
- **Bearish Sample** - Protective put buying, high implied volatility
- **Neutral Sample** - Balanced call/put activity across timeframes

### Interpreting Results

#### Sentiment Score
- **+50 to +100** - Strong Bullish
- **+25 to +49** - Bullish
- **+10 to +24** - Slightly Bullish
- **-10 to +10** - Neutral
- **-11 to -25** - Slightly Bearish
- **-26 to -50** - Bearish
- **-51 to -100** - Strong Bearish

#### Key Metrics
- **Put/Call Ratio** - Values > 1.0 suggest bearish sentiment
- **Near-term Bias** - Short-term directional sentiment
- **Long-term Bias** - Longer-term market outlook
- **Average IV** - Overall market uncertainty level

## 🧮 Calculation Methodology

### Sentiment Scoring Algorithm
The calculator uses a multi-factor weighted approach:

```
Base Score Factors:
- Put/Call Ratio Impact: ±40 points
- Volume Bias: ±30 points  
- Open Interest Bias: ±20 points
- Implied Volatility: ±10 points

Time Weighting:
- Heavy near-term activity: +10% amplification
- Heavy long-term activity: -10% dampening
```

### Term Classification
- **Near-term**: Current month, Next month
- **Medium-term**: 2-3 months out
- **Long-term**: 6-12 month LEAPS

### Main Dashboard
The intuitive interface displays real-time sentiment analysis with visual indicators.

### Analytics View
Metrics include put/call ratios, volume analysis, and term-specific sentiment.

### Chart Visualizations
Interactive charts showing volume distribution and expiration analysis.

## 🔧 Technical Details

### Built With
- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Charts**: Chart.js for interactive visualizations
- **Styling**: Custom CSS with CSS Grid and Flexbox
- **Responsive**: Mobile-first design approach

## 📈 Advanced Features
### Custom Weighting
The algorithm considers multiple factors with intelligent weighting:
- **Volume patterns** - Unusual activity detection
- **Time decay** - Expiration proximity impact
- **Volatility context** - Market fear assessment
- **Position sizing** - Open interest implications

### Market Context
The calculator provides context through:
- Historical sentiment comparison
- Volatility regime analysis
- Time-to-expiration adjustments
- Cross-timeframe analysis
