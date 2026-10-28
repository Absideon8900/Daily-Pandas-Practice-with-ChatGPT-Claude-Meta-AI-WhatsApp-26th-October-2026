# Daily Pandas Practice with ChatGPT, Claude, Meta AI (WhatsApp) 26th October 2026
<b>🌍 New dataset: River Water Quality Monitoring</b></br>
Imagine you're a GIS Analyst studying river pollution across eastern India.</br>
```Python
import pandas as pd
import numpy as np

df = pd.DataFrame({
    "station_id": [101, 102, 103, 104, 105, 106, 107, 108, 109, 110],
    "district": [
        "Kolkata", "Howrah", "Patna", "Guwahati", "Kolkata",
        "Cuttack", "Patna", "Howrah", "Cuttack", "Guwahati"
    ],
    "river": [
        "Hooghly", "Hooghly", "Ganga", "Brahmaputra", "Hooghly",
        "Mahanadi", "Ganga", "Hooghly", "Mahanadi", "Brahmaputra"
    ],
    "ph": [7.2, 6.4, 7.8, 7.1, np.nan, 6.2, 8.1, 6.7, 7.4, np.nan],
    "dissolved_oxygen": [6.8, 4.2, 7.1, 6.5, 5.1, 3.8, 7.5, np.nan, 6.2, 5.9],
    "pollution_level": [
        "Low", "High", "Low", "Moderate", "Moderate",
        "High", "Low", "High", "Moderate", "Moderate"
    ]
})

print(df)
```
<b>Challenge 1 — Missing data</b></br>
Some pH readings are missing. Your task is to create a new DataFrame called clean_df containing only stations where the pH reading is available.</br>
Write the code yourself.</br>
Hint: you may use <code>.isna()</code> or <code>.notna()</code> with Boolean filtering. Which approach will you choose? 😎</br>

# Solution (Script)
```Python
import pandas as pd
import numpy as np

df = pd.DataFrame({
    "station_id": [101, 102, 103, 104, 105, 106, 107, 108, 109, 110],
    "district": [
        "Kolkata", "Howrah", "Patna", "Guwahati", "Kolkata",
        "Cuttack", "Patna", "Howrah", "Cuttack", "Guwahati"
    ],
    "river": [
        "Hooghly", "Hooghly", "Ganga", "Brahmaputra", "Hooghly",
        "Mahanadi", "Ganga", "Hooghly", "Mahanadi", "Brahmaputra"
    ],
    "ph": [7.2, 6.4, 7.8, 7.1, np.nan, 6.2, 8.1, 6.7, 7.4, np.nan],
    "dissolved_oxygen": [6.8, 4.2, 7.1, 6.5, 5.1, 3.8, 7.5, np.nan, 6.2, 5.9],
    "pollution_level": [
        "Low", "High", "Low", "Moderate", "Moderate",
        "High", "Low", "High", "Moderate", "Moderate"
    ]
})
clean_df = df.copy()
clean_df["ph"] = clean_df["ph"].fillna(clean_df["ph"].mean())
clean_df["dissolved_oxygen"] = clean_df["dissolved_oxygen"].fillna(clean_df["dissolved_oxygen"].mean())
#print(clean_df)
```

# Script (Solution)
```
PS C:\Users\hp\Downloads\sql_practice(0)> & C:\Users\hp\AppData\Local\Programs\Python\Python313\python.exe "c:/Users/hp/Downloads/sql_practice(0)/text.py"
   station_id  district        river      ph  dissolved_oxygen pollution_level
0         101   Kolkata      Hooghly  7.2000               6.8             Low
1         102    Howrah      Hooghly  6.4000               4.2            High
2         103     Patna        Ganga  7.8000               7.1             Low
3         104  Guwahati  Brahmaputra  7.1000               6.5        Moderate
4         105   Kolkata      Hooghly  7.1125               5.1        Moderate
5         106   Cuttack     Mahanadi  6.2000               3.8            High
6         107     Patna        Ganga  8.1000               7.5             Low
7         108    Howrah      Hooghly  6.7000               5.9            High
8         109   Cuttack     Mahanadi  7.4000               6.2        Moderate
9         110  Guwahati  Brahmaputra  7.1125               5.9        Moderate
PS C:\Users\hp\Downloads\sql_practice(0)> 
```

# Script (Visualization)
<img width="766" height="590" alt="output" src="https://github.com/user-attachments/assets/c27e7889-9915-46ab-ba03-c1a13b75b2de" />
