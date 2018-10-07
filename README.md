# GeoCMS
## Motivation
- existing geospatial content management systems provide limited functionalities for data processing
- enable adding various data sources from GetCapabilities
- get the data from coverages via WCPS for selected polygon

## Target user groups
- Future ONDA DIAS platform users
-

## Methodology
- Define reference data which will be used as a filter for WCPS queries (GADM world borders, levels 0, 1, 2)
- From WCS getCapabilities discover overages

## Results


## Challenges
- Various reference systems require investing more effort to enable combining data
- Various ways to define coordinate order (N/E instead of E/N which OpenLayers supports by default)

## Live demo
- http://173.212.238.231:20081/danubehack/geocms/
