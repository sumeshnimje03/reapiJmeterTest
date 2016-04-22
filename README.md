# xM API Jmeter Runner

Basic useful feature list:

 * Uses the jmeter-gradle-plugin https://github.com/kulya/jmeter-gradle-plugin/wiki to allow the running of jmeter tests automatically


To run functional test:
```./gradlew functionalTest jmeterRun```

To run performance load test:
```./gradlew performanceTest jmeterRun```

To open JMeter Edit mode:
```./gradlew addToJmeterClasspath jmeterEditor```

# Configuration
xMatters On-demand Configuration Requirements
Tests assume a default site timezone of US/Eastern. Please update:
the Default Site in xMod: US/Eastern.
the timezone of the company admin that will run the tests: US/Eastern
Tests require that french is enabled as a selectable language in the company under test.
User 'rdOnly' exists with the following configuration:
ID: rdOnly
Web Login Password: 1000
Roles: Read-only User

User 'groupSupervisor' exists with the following configuration:
ID: groupSupervisor_xm102
Web Login Password: 1000
Roles: Group Supervisor

# Environment Variables

To modify edit src/test/jmeter/jmeter.properties
Each script contains a test element named "Environment Variables", with the following settings:

* host: this is the hostname of the on-demand deployment
* port: generally this will be 443 for deployments in the DC. Change to suit.
* db_ip_port: the IP and Port of Database machine. The port for postgres is usually 5432
* db_name: the name of the database used for xMod
* db_pwd: the password used to connect to database. This can be found under xMod installation folder's common.property file.
* username: the userId for a company admin in the company under test
* password: the password for the company admin
* timeout_ms: timeout for all requests. If reached, a test will fail.
* protocol: http or https
* defaultSiteData: UUID of the default site. Available via the API button on the site details page.
* application_uuid: UUID of Communicatioin Plan used for Integration Builder testing
* integration_uuid: UUID of Integration Builder in Communication Plan under test
* integration_client_secret_id: UUID of integration client secret id
* groupSupervisor_username: the Group Supervisor Role username

### Stuff used to make this:

 * https://github.com/kulya/jmeter-gradle-plugin/wiki
 * https://vic-confluence.xmatters.com/display/ENG/xM+API+Automated+Regression+and+Load+Test

