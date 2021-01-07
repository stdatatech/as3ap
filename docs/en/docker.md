AS3AP support installation base on docker image. User can experience all AS3AP features by installing AS3AP docker image.

#### Prerequisite
* Docker Engine has installed and configured.
* User has docker hub account and has granted access to image.
* User login into docker hub.

#### Getting Started

* First usage on *nix

AS3AP container can use mounted volume to store user data into local disk, such as system settings, user preference, chart definition, dashboar definition, etc. These data will not lost when user try to launch new AS3AP container with new image.<br>

The following sample shows how to use local /tmp/AS3AP to keep user data.
```shell
docker run -d -p 3000:3000 -p 8080:8080 -v /tmp/AS3AP:/opt/AS3AP/u-data stdatatech/AS3AP /opt/AS3AP/bin/start.sh <your ipaddress> 8080 
```

!> \<your ipaddress\> in above command sample should be user local host IP addreass. In most case, user can  set to 127.0.0.1

When above docker command executed successfully, user can AS3AP start page by accessing to http://localhost:3000 via any WebBrowser. Default user password is admin/admin. <br>

License is still required when running AS3AP in docker. User can contact us to acquire license. One license only allow one AS3AP container instance in running status.

* List running AS3AP containers

```shell
docker container ls | grep stdatatech/AS3AP
```
```shell
docker container ls --all | grep stdatatech/AS3AP
```

* Stop AS3AP

```shell
docker stop <your container ID>
```

* Restart AS3AP
 
```shell
docker start <container ID>
```

* Upgrade AS3AP

```shell
docker run -d -p 3000:3000 -p 8080:8080 -v /tmp/AS3AP:/opt/AS3AP/u-data stdatatech/AS3AP /opt/AS3AP/bin/start.sh <your ipaddress> 8080 
```

#### Use Sample Data

* Download Sample Data

User can download latest sqlite database file demo.db.gz from https://github.com/stdatatech/dash-examples/releases. <br>

Execute the following command on Linux or Mac to extract demo database
```shell
  gzip -d demo.db.gz
```
Use any available extract tool on Windows to extract demo database.

User can create sqlite database source after get demo.db file. [Reference](sqlite)

!> Please create a new sqlite datasource which name with 'demo'. 'demo' is the default name of sample charts and dashboard. It would be easy for user to see sample charts and dashboard when import sample charts and dashboard.

* Download Sample Charts and Dashboards

User can download predefined sample charts and dashboard from github https://github.com/stdatatech/dash-examples

![Example](dash-example.jpg)

After download and extract sample charts and dashboard definition, user will have a bunch of json files. Please reference to [Import/Export](imexport) to import charts and dashboard samples.