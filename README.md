CoreMedia Content Management Server for MenuSite
================================================

Demo gradle script to assemble a plain, uncustomized CoreMedia Content Management 
Server in a stripped down variant of how the original Maven based workspace layout 
from CoreMedia does it.

Additionally a CoreMedia 7 compatible version of the good old MenuSite document types 
has been added, which is in some respects different from the original one and thus 
cannot be derived from the old JARs provided by CoreMedia. Despite all that it still
works with their content and serves well as a backend for the Tangram MenuSite examples
"example-coma-spring" from the Tangram examples at https://github.com/mgoellnitz/tangram-examples

Prerequisites
-------------

- Access to the CoreMedia Maven artifact repositories

- A valid license file

- A prepared (MySQL) database

Usage
-----

Customizing

Change the values in the few config files presented in this workspace as needed. 
E.g. the database access definetely needs some tuning. Add a license file license.zip 
to the properties/corem directory.

Building

```
gradle build
```

Running

It is not possible to start a CoreMedia Content Server as a WAR-Package. It needs 
to be exploded. I was not able to achieve this with the gradle tomcat module referenced 
by the build.gradle script in this workspace. You will definetely have to copy the 
created artifact to a tomcat container to be able to start it.

```
mv build/libs/coremedia.war /some/where/my/tomcat/resides/webapps
```

DB preparation steno
====================

Create ab account with http://www.db4free.net/ and integrate the access data into 
the sql.properties in this workspace.
