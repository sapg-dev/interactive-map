# Interactive World Map with svgMap

## Description
This project demonstrates how to create an **interactive world map** using the **svgMap** JavaScript library. The map displays *GDP per capita* and its change from the previous year for each country. However, for demonstration purposes, only data for a few countries is included to make the example concise and manageable.

## How to Use
1. Open the `index.html` file in a modern web browser to view the interactive world map.
2. Hover over the countries included on the map to view a tooltip displaying the GDP per capita and its change from the previous year.

## Code Structure
- The `index.html` file contains the complete HTML structure, including links to the **svgMap library** and CSS via CDN.
- A `div` with the id `svgMap` is where the interactive world map is rendered.
- The **svgMap** is initialized with JavaScript, and data for a few countries is provided in the `values` object within the `data` property.

## Note on Country Data
In this example, data is provided for only a few countries to keep the code concise and manageable. In a real-world scenario, you would likely want to include data for many more, or all, countries. However, this would require a *much larger JSON file* to hold the data.

## Dependencies
- [**svgMap**](https://github.com/StephanWagner/svgMap) for creating the interactive world map.
- [**svg-pan-zoom**](https://github.com/ariutta/svg-pan-zoom) for enabling pan and zoom features on the SVG map.

## Example Code Snippet
```html
new svgMap({
    targetElementID: 'svgMap',
    data: {
        data: {
            gdp: {
                name: 'GDP per capita',
                format: '{0} USD',
                thousandSeparator: ',',
                thresholdMax: 50000,
                thresholdMin: 1000
            },
            change: {
                name: 'Change to year before',
                format: '{0} %'
            }
        },
        applyData: 'gdp',
        values: {
            AF: {gdp: 587, change: 4.73},
            AL: {gdp: 4583, change: 11.09},
            DZ: {gdp: 4293, change: 10.01}
            // ... add more country data as needed
        }
    }
});
