Readme:

This demonstration shows how to use JDBC over WebSocket with the Kaazing WebSocket Gateway HTML5 Edition. 
The scenario below was tested against the following:

- User Interface
Google Chrome 18.0.1025.163
Apple Safari 5.1.3
Mozilla Firefox 10.0.2

- Patform
Mac OS X 10.7.3

- Kaazing WebSocket Gateway HTML5 Edition 3.2.5

- Backend System
The backend system is based on Apache Camel 2.9.1 and it runs a simple route opening a TCP port where the Gateway 
connects to and executes a query against the JDBC-compliant database which uses the payload of the message as part 
of the SQL statement. 
The backend system is a Maven project and it's recommended that you download the latest version of Maven from 
http://maven.apache.org/download.html

The database used in this demonstration is MySQL and can be downloaded from http://dev.mysql.com/downloads/mysql/

Populate the default test database shipped with MySQL with the file available under $PROJECT_HOME/DB. To do that, 
connect to the MySQL database and run the following command:

$ mysql -u user -p db-name < $PROJECT_HOME/DB/db-name.out

- Setup and Running the demo
Install, setup and start an instance of MySQL or any JDBC-compliant database. If you opt for other database than 
MySQL then you'll have to change the Apache Camel route configuration. See the Apache Camel website 
(http://camel.apache.org) for more information.

Open o terminal console from the $PROJECT_HOME/Backend and run the following command:

$ mvn camel:run

You must have Apache Maven installed and it will download all required components for you to run the backend system 
in this demo.

Copy the web/ folder under $PROJECT_HOME/Gateway folder to your Kaazing WebSocket Gateway HTML5 Edition directory 
under web/extras.

Copy the Kaazing WebSocket Gateway HTML5 Edition JavaScript client library (WebSocket.js) from kaazing-websocket-gateway-html5-3.x.x/lib/client/javascript to kaazing-websocket-gateway-html5-3.x.x/web/extras/web.

Start the Gateway by pointing to the configuration file under $PROJECT_HOME/Gateway called gateway-config-jdbc.xml

Then, point your browser to http://localhost:6001/web/index.html

In the Email address search field type vfranco@diecast.com or jking@sgs.com (if you're using the provided sample 
database)and hit Search.

The customer information should be retrieved from the database and populate the remaining fields on the page.

Typing an invalid or an email address not present in the database should return an alert popup with 
the 'Customer Not Found' message.

If you have any questions, feel free to contact me at mqjabali [at] gmail [dot] com
