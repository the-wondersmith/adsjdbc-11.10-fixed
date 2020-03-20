# ADSJDBC 11.10 (fixed)
### A patched JDBC driver for SAP's Advantage Database Server v11.10

The latest (easily) available version of the JDBC driver published by SAP for Advantage Database Server doesn't play nicely with newer (read: remotely modern) versions of Java because it doesn't implement methods for `supportsSavepoints()` and `getDatabaseMinorVersion()`.

The driver supplied in this repository is identical in every way to the version that can be [downloaded directly from SAP](https://devzone.advantagedatabase.com/dz/content.aspx?Key=20&Release=19&Product=12&Platform=4) with the exception of the additional methods. 

The `supportsSavepoints()` and `getDatabaseMinorVersion()` were added by cloning their "nearest neighbor" functionally speaking - (`supportsConvert()` and `getDatabaseMajorVersion()` respectively). This means that those methods are effectively useless as they won't return the data that's actually being requested, they'll only return data that matches the expected type.

The modifications were made using [ReCaf](https://github.com/Col-E/Recaf). The driver is provided as is, with no support or plans for future maintenance, and without any connection or support from SAP or the Advantage Database team.

I've made it available here in the hopes that someone else finds it as useful as I have.
