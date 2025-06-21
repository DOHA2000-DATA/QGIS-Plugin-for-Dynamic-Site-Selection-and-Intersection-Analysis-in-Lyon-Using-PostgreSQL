# QGIS-Plugin-for-Dynamic-Site-Selection-and-Intersection-Analysis-in-Lyon-Using-PostgreSQL
This project is a QGIS plugin designed to interact directly with a PostgreSQL/PostGIS spatial database containing geospatial data for the city of Lyon. The plugin enables users to dynamically select sites based on spatial queries executed via customizable SQL requests.

Key Features

    Real-time connection to the PostgreSQL database to retrieve spatial data based on the user's selection within QGIS.

    Filtering of sites in Lyon according to the geometry selected by the user, through parameterized SQL queries.

    Calculation and utilization of the percentage of intersection between the selected area and sites in the database, allowing precise spatial analysis.

    Direct visualization of the query results as vector layers within QGIS, facilitating geographic and decision-making analysis.

    User-friendly interface embedded in QGIS, enabling site selection and adjustment of intersection thresholds.

Use Cases

This plugin is targeted at urban planners, GIS specialists, and decision-makers who need to perform detailed spatial analyses on sites in Lyon based on data stored in PostgreSQL. It helps to:

    Quickly identify sites intersecting a specified area above a certain percentage threshold.

    Automate complex database queries to save time.

    Generate thematic maps derived from dynamic site selections.
