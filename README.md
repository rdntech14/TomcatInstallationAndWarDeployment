Tomcat Installation & War Deployment
=====
This example demonstrate how to install tomcat and deploy .war file

**Steps to follow**

1. Download Tomcat zip file from https://tomcat.apache.org/download-80.cgi#8.5.31
2. unzip the file and place it at location

3. On terminal navigate to tomcat location and add execute permission to all .sh files

```
cd <path_to_tocmat_bin_folder>
ls -l
chmod +x *.sh
ls -l
./startup.sh
```

4. Open browser and navigate to http://localhost:8080/
5. This is show default Tomcat apache page
6. To stop tomcat server
```
./shutdown.sh
```
7. To create users to access or manage tomcat -
update tomcat/apache-tomcat/conf/tomcat-users.xml with following xml content

```
<?xml version='1.0' encoding='utf-8'?>
<tomcat-users>
    <role rolename="manager-gui"/>
    <role rolename="manager-script"/>
    <role rolename="manager-jmx"/>
    <role rolename="manager-jmx"/>
    <role rolename="admin-gui"/>
    <role rolename="admin-script"/>
    <user username="admin" password="admin" roles="manager-gui,manager-script,manager-jmx,manager-status,admin-gui,admin-script"/>
</tomcat-users>
```

8. Export "Web Dynamic Project" as .war from Eclipse.
*Refer project : https://github.com/rdntech14/CreateRESTFulService . Output file will be CreateRESTFulService.war*

9. Navigate to tomcat/apache-tomcat/webapps and place .war file.
10. Restart tomcat
11. URL *http://localhost:8080/CreateRESTFulService/rest/employee/list* will return result
