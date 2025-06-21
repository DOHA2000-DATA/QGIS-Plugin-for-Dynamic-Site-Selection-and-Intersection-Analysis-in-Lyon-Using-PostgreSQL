QGIS Plugin for Dynamic Site Selection and Intersection Analysis in Lyon Using PostgreSQL
Overview

This QGIS plugin provides a powerful interface to dynamically select and analyze spatial sites within the city of Lyon, leveraging a PostgreSQL/PostGIS spatial database. Users can execute spatial SQL queries based on geometries selected directly in QGIS, with advanced filtering based on the percentage of intersection between selected areas and database features. This facilitates accurate spatial decision-making for urban planning, environmental analysis, and more.
Features
<img width="298" alt="12" src="https://github.com/user-attachments/assets/8f2e8bd7-7c99-44b5-bd2d-d7e90837b7d8" />


![image](https://github.com/user-attachments/assets/a51a9805-fc05-4851-b99a-bc40d544999f)


    Direct connection to PostgreSQL/PostGIS spatial database containing Lyon site data.

    Dynamic SQL queries triggered by user selections on the QGIS map canvas.

    Calculation of percentage intersection between selected geometries and database features.

    Filtering of sites based on customizable intersection threshold values.

    Results are displayed as QGIS vector layers for easy visualization and analysis.

    Simple, intuitive GUI integrated within the QGIS interface.

    Supports selection of points, polygons, or multipolygons on the map.

    New: Generation of a statistical report summarizing query results, including number of selected sites, area coverage, and intersection statistics in PDF or CSV format.

Requirements

    QGIS 3.x or higher

    PostgreSQL database with PostGIS extension enabled

    Spatial data loaded in PostgreSQL representing Lyon sites with geometry column

    Python environment compatible with QGIS Python plugins (PyQGIS)

    Optional: ReportLab or pandas libraries for report generation (depending on implementation)

Installation

    Download or clone the plugin repository:

    git clone https://github.com/yourusername/lyon-site-selection-plugin.git

    Open QGIS.

    Go to Plugins > Manage and Install Plugins...

    Click on Install from ZIP (if you have zipped the plugin folder) or copy the plugin folder to your QGIS plugin directory.

    Enable the plugin from the plugin manager.

    Open the plugin panel and configure your PostgreSQL connection settings.

Usage

    Load or ensure your Lyon site spatial layers are available in PostgreSQL.

    In QGIS, select one or more features (polygons, multipolygons) representing areas of interest.

    Open the plugin panel from the QGIS toolbar.

    Configure the PostgreSQL connection if not already set.

    Set the intersection threshold percentage (e.g., 20% means the site must overlap the selected area by at least 20%).

    Execute the query.

    The plugin will fetch sites from PostgreSQL intersecting the selected geometry with at least the specified percentage of overlap.

    Results will be displayed as a new vector layer in your QGIS project.

    Generate a detailed statistical report summarizing:

        Number of sites selected

        Total and average intersection area

        Percentage coverage statistics

        Other relevant spatial statistics

    The report can be exported in PDF or CSV formats for sharing and documentation.

How It Works

The plugin uses spatial SQL to query the PostgreSQL database with a command similar to:

SELECT *
FROM sites
WHERE ST_Intersects(geom, ST_GeomFromText(:selected_geom, 4326))
AND (ST_Area(ST_Intersection(geom, ST_GeomFromText(:selected_geom, 4326))) / ST_Area(geom)) * 100 >= :threshold;

Where:

    :selected_geom is the geometry WKT of the selected area in QGIS.

    :threshold is the user-defined minimum intersection percentage.

The plugin then computes statistics on the query results and allows exporting a report.
Contributing

Contributions, issues, and feature requests are welcome! Feel free to:

    Open issues for bugs or feature suggestions

    Submit pull requests with improvements or fixes

    Share feedback to improve usability

License

This project is licensed under the MIT License — see the LICENSE file for details.
Contact

Your Name
Email: idrissimounadidoha@gmail.com
LinkedIn:https://www.linkedin.com/in/doha-idrissi-mounadi-68b9801a4/
