address-book
------------
<p>in <a src="https://git-scm.com/downloads">git bash</a></p>
<p>git clone https://github.com/CharlieSwires/address-book</p>

<p>This contains both the java and React</p>

build
-----
<p>cd address-book/src/main/webapp/address-app</p>
<p>npm run build (you'll need to download <a src="https://nodejs.org/dist/v22.18.0/node-v22.18.0-x64.msi">node</a>)</p>
<p>cd ../../../..</p>
<p>you'll need an application.properties file with the DB username and password
URL</p>
<p>mvn package (you'll need <a src="https://builds.openlogic.com/downloadJDK/openlogic-openjdk/17.0.16+8/openlogic-openjdk-17.0.16+8-windows-x64.msi">openjdk17</a> and <a src="https://maven.apache.org/guides/getting-started/windows-prerequisites.html">maven</a>)</p>

<p>produces address-book.war in target</p>

<p>7zip address-book.war</p>
<p>remove the address-app/node-nodules</p>

deploy
------
<p> You'll need <a src="https://www.docker.com/products/docker-desktop/">docker</a></p>
<p>docker build --tag address:latest .</p>
<p>docker run  --env-file ./env.list --name container2 --link container1 -d -p 8887:8080 address:latest</p>


browser
-------
<p>http://localhost:8887/address-book/address-app/build/index.html</p>

RESTful
-------

<p>http://localhost:8887/address-book/AddressEntry/add</p>
<p>http://localhost:8887/address-book/AddressEntry/delete/{firstName}/{lastName}</p>
<p>http://localhost:8887/address-book/AddressEntry/get/{firstName}/{lastName}</p>
<p>http://localhost:8887/address-book/AddressEntry/get/{lastName} -- returns list of JSON</p>
<p>http://localhost:8887/address-book/AddressEntry/getFirst/{firstname} -- returns list of JSON</p>
<p>http://localhost:8887/address-book/AddressEntry/getAllCSV -- returns CSV file</p>
<p>http://localhost:8887/address-book/AddressEntry/getAll -- returns list of JSON</p>
<p>http://localhost:8887/address-book/AddressEntry/loadAll -- loads db from addressbook.csv</p>

