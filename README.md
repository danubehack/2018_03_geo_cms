# GeoCMS
## Motivation
- existing geospatial content management systems provide limited functionalities for data processing
- enable adding various data sources from GetCapabilities
- get the data from coverages via WCPS for selected polygon
- combine data from multiple coverages via WCPS, original idea pertained to night light correlated with population, due to lack of data shifted to infrared

## Target user groups
- Users requiring data manipulation and visualisation functionalities via web application
- Users wishing to combine data from multiple rastered sources
- Users interested in simple access to sentinel data

## Methodology
- Define reference data which will be used as a filter for WCPS queries (GADM world borders, levels 0, 1, 2)
- Import necessary data from Sentinel to WCS
- From WCS getCapabilities discover coverages
- Utilize WCPS for realtime processing on coverages, examples
-- aggregation of all population values within a polygon
-- correlation of population data with infrared levels

## Results
- Viewer allowing for on-the-fly aggregation of coverage data (population) based on polygons (NUTS)
- Automatically fetching the projection of coverage and reprojection to the projection of the viewer
- Aligning the projection of different coverages before calculation, then cross correlate (simple difference) between population and infrared
- Automatic reversal of coordinates due to different coverage setups (and bugs in the frameworks)
- Viewer for correlation of population data with infrared levels still in progress, time delay due to first setting up data services

## Challenges
- Copernicus data difficult to process, thus selected bands from LEVEL-2A pertaining to infrared data were imported to a WCS (bands 8a, 11, 12)
- Various reference systems require investing more effort to enable combining data
- Various ways to define coordinate order (N/E instead of E/N which OpenLayers supports by default)
- WCPS returns error when the selection polygon extends over the coverage extent
- WCPS poorly documented pertaining to crs transformation for on-the-fly merge of coverages with different projections

## Live demo
- http://173.212.238.231:20081/danubehack/geocms/
