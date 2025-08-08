
# Assignment 02 – Geoprocessing

## 1. Dataset 1 – My Restaurants
A collection of my favorite restaurants in Bangalore, geolocated as points. This dataset represents a part of my personal daily life and food habits in the city.

**File:** `blr-restaurants.geojson`

---

## 2. Related Dataset – Namma Metro Lines & Stations
The official route and station network of the Bengaluru Namma Metro, represented as line and point geometries. Each line is color-coded according to the real network map.  
I sourced the base data from the [geohacker/namma-metro GitHub repository](https://github.com/geohacker/namma-metro) and then modified it slightly to improve formatting and visualization.

**File:** `metro_lines_styled_cgpt.geojson`

---

## 3. Proposed Methodology
The workflow combines the restaurant locations with the metro network to calculate realistic travel times from my home to each restaurant using the metro system.

### Steps:
1. **Input**: Select a target restaurant from `blr-restaurants.geojson`.
2. **Find nearest station** to that restaurant from `metro_lines_styled_cgpt.geojson` (Euclidean or network distance).
3. **Determine route** from home station to the restaurant’s nearest station via the metro line network:
   - Identify line(s)
   - Account for any **line changes**
4. **Calculate walking distance/time**:
   - From home to nearest station
   - From final station to the restaurant
5. **Calculate metro travel time**:
   - Based on line speeds and station-to-station distances
6. **Sum total travel time** = walking time + metro time + transfer time.
7. **Output**: Ranked list of restaurants by shortest total travel time.

---

## 4. Workflow Diagram
*(To be drawn in diagrams.net, PowerPoint, or similar)*

```
[Home] 
   ↓ (walk)
[Nearest Metro Station to Home] 
   ↓ (metro ride)
[Transfer if needed] 
   ↓ (metro ride)
[Nearest Metro Station to Restaurant] 
   ↓ (walk)
[Restaurant]
```

---

## 5. Potential Uses
- Identifying the most accessible restaurants in Bangalore via metro
- Exploring how metro expansion changes accessibility to food spots
- Urban mobility and lifestyle mapping
