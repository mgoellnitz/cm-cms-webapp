# CoreMedia Content Management Server

CoreMedia Content Management Server assembled with Gradle to illustrate, what a 
Gradle based CoreMedia workspace might look like.

This demo gradle script assembles a plain, uncustomized CoreMedia Content 
Management Server in a stripped down variant of how the original Maven based 
workspace layout from CoreMedia does it.

It is meant as a hint that a migration from the Apache Maven build system (not 
its dependency management and repositories) would be an advantage for 
readability and maintence of CoreMedia workspaces.

This repository in itself is feedback about the topic, but feel free to send
any comment e.g. via the [issues][issues] section at GitHub.

Find mirrors of this git repository at [gitlab][gitlab] and [github][github].


## Prerequisites

- Access to the CoreMedia Maven artifact repositories

- A valid license file

- A prepared (MySQL) database


## Usage

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


## DB preparation steno

Create ab account with http://www.db4free.net/ and integrate the access data into 
the sql.properties in this workspace.


[issues]: https://github.com/mgoellnitz/cm-cms-webapp/issues
[github]: https://github.com/mgoellnitz/cm-cms-webapp
[gitlab]: https://gitlab.com/mgoellnitz/cm-cms-webapp
