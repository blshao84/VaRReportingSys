# VaRReportingSys
Required softwares: JDK8, Docker, node, pm2, 
1. Checkout source code from git repository
2. To build: ./gradlew --parallel build
3. To install: ./gradlew installLocal (should run after gradlew build)
4. To Run (from project root):
	1. cd scripts/initialize/db/
	2. ./start_db_refresh.sh: this will create a docker instance for postgres (db)
	3. go to project root
	4. cd install
	5. pm2 start bct.config.js: it will create two jvms is the var-server and the other is the zuul-server. zuul is the proxy and var-server is the main web service. 
5. To Test: Import Postman apis, and run the test API

Project Structure:
core: interfaces
var-service: business logic
servers/var-server: http server
