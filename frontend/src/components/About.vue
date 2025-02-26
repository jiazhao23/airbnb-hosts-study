<template>
  <div class="about-container">
    <div class="markdown-content" v-html="compiledMarkdown"></div>
  </div>
</template>

<script>
import { marked } from 'marked';

export default {
  name: 'About',
  data() {
    return {
      markdown: `# Welcome to Geonarvis' First Project  

Created by [Jia Zhao](https://github.com/jiazhao23)

The data source of this project is [Inside Airbnb](https://insideairbnb.com/). The basemap comes from a custom Mapbox Studio project, including:

1. Increased the grayscale of logos, names, and land features

2. Increased the density of POIs of interest to tourists, such as attractions, landmarks, and transportation stations

You can preview this style through this link [Mapbox Studio](https://api.mapbox.com/styles/v1/zhaojia2024/cm6cri5yh007h01s2dy643axe.html?title=view&access_token=pk.eyJ1Ijoiemhhb2ppYTIwMjQiLCJhIjoiY200ZmhzamIyMDgwNjJtcXIwaWNudWllbSJ9._-NLC8BDDwDt__sVALSBXg&zoomwheel=true&fresh=true#14.38/51.50244/-0.13334).
In the scatter plot, the size of the scatter points represents the high or low housing prices. At the bottom of the sidebar, you can find a slider to adjust the scatter point style. Here are the steps to use this map:

## Interactive Steps of the Project  

### Step 1: Select a City  
- Wait for the loading to complete.  

### Step 2: Select the Current View Mode  
- There are two modes:  
  1. **Scatter Plot**  
  2. **Heat Map**  

### Step 3: Check the Type of Host You Want to See  
The listings held by different types of hosts will change according to the currently selected time:  
- **Highly Commercial**: The top 10% of hosts in the current city.  
- **Commercial**: The top 10% to 25% of hosts in the current city.  
- **Semi-Commercial**: The remaining hosts outside the other four types of landlords)
- **Dual Host**: Hosts who hold two houses.  
- **Single Host**: Hosts with one property.  

### Step 4: Drag the Time Bar  
- Observe the changes in data and the map over time.  

## Annual Statistics  
At the bottom of the interface, there are two types of annual statistics on properties of different types of hosts in the city:  
1. **Percentage**: The proportion of properties held by each type of host.  
2. **Absolute Number**: The total count of properties for each type of host.  

## Notes on Geographic Coordinates  
The coordinates of the listing are fuzzy. Airbnb uses a circle with a radius of 150m as a fuzzy buffer to obscure exact locations.  
`
    };
  },
  computed: {
    compiledMarkdown() {
      return marked(this.markdown);
    }
  }
};
</script>

<style>
.markdown-content {
  padding: 20px;
  line-height: 1.6;
}

.markdown-content h1 {
  font-size: 2rem;
  margin-bottom: 1.5rem;
  font-weight: bold;
}

.markdown-content h2 {
  font-size: 1.5rem;
  margin: 2rem 0 1rem;
  font-weight: bold;
}

.markdown-content h3 {
  font-size: 1.2rem;
  margin: 1.5rem 0 1rem;
  font-weight: bold;
  color: #333;
}

.markdown-content p {
  margin-bottom: 1rem;
}

.markdown-content ol {
  margin-left: 1.5rem;
  margin-bottom: 1rem;
}

.markdown-content li {
  margin-bottom: 0.5rem;
}

/* 让链接字体变为蓝色并带下划线 */
.markdown-content a {
  color: blue;
  text-decoration: underline;
}
</style>
