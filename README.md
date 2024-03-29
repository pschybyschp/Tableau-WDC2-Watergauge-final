# Tableau-WDC2-Watergauge
To use this webdataconnector (WDC2.0) please follow along with the descriptions on https://tableau.github.io/webdataconnector/docs/
You need to have a local node server running or you upload the WDC to a node server in the web.

 WDC will be available through following site:
https://www.logistikjunge.de/Tableau/watergaugeWDC.html

The WDC consist of following entities:
- water.js -> Usability/UX for the forms
- watergauge.css -> color etc formating for the forms
- watergauge.js -> main coding to load data into Tableau including schema definition and getjson requests etc
- WatergaugeWDC.html -> forms

The Tableau Webdataconnector Watergauge is based on the Tableau Webdataconnector Watergaugestations. 
- It loads master data of the watergauge stations available in Germany. 
- It loads master and transactional data of the watergauge stations available in Germany. 
- It loads historical data of the watergauge stations available in Germany as initial and incremental load. 
It provides 3 forms to filter the data which should be loaded.

Major improvments comparing to Tableau Webdataconnector Watergaugestations:
- Incremental load of historical data
- Data model: Fields for connection are predefinied (UUID) and for historical data (UUIC/Shortname)
- Provision of a form to filter watergaugestations by waters
- After selection of a speccific water additionaly the form enables to filter watergaugestations by locations based on the distance to the water source and a radius
- The WDC contains also some simple logic to improve the usability of the form (water.js)

The form contains a dropdown list of all available waters.
To populate this dropdown list following REST-API is used:
https://www.pegelonline.wsv.de/webservices/rest-api/v2/waters.json

Depending on the user selection following REST-API resources are used:
User select 'All waters':  https://www.pegelonline.wsv.de/webservices/rest-api/v2/stations.json

User select a specific water with or without use of location filter:
https://www.pegelonline.wsv.de/webservices/rest-api/v2/stations.json?waters=RHEIN&km=680&radius=50

The documentation of the data can be accessed using 
https://www.pegelonline.wsv.de/webservice/dokuRestapi


