---
layout: page
title: "Energy Burden in the Bronx, New York City"
permalink: /bronx-energy-burden/
category: Professional
img: assets/img/maps/bronx-energy-preview.png
importance: 4
---     

Energy Burden (%) is the share of a household’s income spent on home energy costs, expressed as a percentage of income. The energy burden presented in this map was derived from the raw LEAD Tool 2022 tract-level data, using the columns that represent total energy costs for electricity, gas, and fuel across all households. To calculate it, I added the total annual spending on these energy sources and divided that amount by the total household income within each census tract. Areas with lower incomes and older, less efficient housing tend to show higher energy burdens, while parks, industrial zones, or tracts with few or no households often have missing or distorted values, which is why those tracts are masked from the map. This map was created in python using geopandas and folium, and sources are referenced underneath the map.

<div class="map-embed">
  <iframe
    src="{{ '/assets/html/bronx-energy-burden-map.html' | relative_url }}"
    loading="lazy"
    referrerpolicy="no-referrer-when-downgrade"
    title="Interactive map of Energy Burden (%) and hospitals in the Bronx">
  </iframe>
</div>

<p class="map-caption">
  Explore the interactive map above. 
  <a href="{{ '/assets/html/bronx-energy-burden-map.html' | relative_url }}">Open full screen</a>.
</p>

<style>
  /* Map container */
  .map-embed {
    position: relative;
    width: 100%;
    height: 80vh;               /* desktop/tablet */
    border-radius: 12px;
    overflow: hidden;
    background: #111;           /* complements dark tiles */
    margin: 1rem 0 0.5rem;
    box-shadow: 0 10px 25px rgba(0,0,0,.3);
  }
  .map-embed iframe {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    border: 0;
  }
  /* Responsive height */
  @media (max-width: 768px) {
    .map-embed { height: 60vh; }
  }
  @media (max-width: 480px) {
    .map-embed { height: 55vh; }
  }
  .map-caption {
    font-size: 0.95rem;
    color: #777;
    margin-bottom: 2rem;
  }
</style>

## Data Sources

- **Low-Income Energy Affordability Data (LEAD) Tool — 2022**  
  U.S. Department of Energy, NREL. Dataset landing page:  
  [https://data.openei.org/submissions/6219](https://data.openei.org/submissions/6219)  
  *Used for tract-level energy cost aggregates (energy burden).*

- **TIGER/Line Shapefile (2022), State: New York — Census Tracts**  
  U.S. Census Bureau. Catalog record:  
  [https://catalog.data.gov/dataset/tiger-line-shapefile-2022-state-new-york-ny-census-tract](https://catalog.data.gov/dataset/tiger-line-shapefile-2022-state-new-york-ny-census-tract)  
  *Spatial geometries for Bronx census tracts.*

- **U.S. Census Bureau API (ACS 5-Year Profiles: DP03, DP04, DP05, DP02)**  
  U.S. Census Bureau. API documentation:  
  [https://api.census.gov/data.html](https://api.census.gov/data.html)  
  *Economic and housing characteristics (income, poverty rate, households).*