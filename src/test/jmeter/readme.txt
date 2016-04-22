Currently, some of the test suites defined by the jmx projects require data to be pre-loaded before running.  
In addition, those common to all are detailed in the jmeter properties file, e.g. default site uuid.

Additional data is required for the following:

General:
- the Default Site in xMod: US/Eastern.
- Tests require that French is enabled as a selectable language in the company under test.
- Phone Extension must be enabled for the company.
- User 'xm-suport' exists in Company "Template" with the following configuratioin"
-- ID: same as the value set in "username" Environment Variable. I.e. "xm-support"
-- Web Login Password: the same as the value set in "password" Environment Variable. I.e. "complex"

People/Group/Find People/Add Shift to Group:
- User 'rdOnly' exists with the following configuration:
-- ID: rdOnly
-- Web Login Password: 1000
-- Roles: Read-only User
- User 'groupSupervisor' exists with the following configuration:
-- ID: groupSupervisor_xm102
-- Web Login Password: 1000
-- Roles: Group Supervisor
-- First Name: groupSupervisor
-- Device: Home Email : support-home@mailinator.com

Shifts:
 - A group named "Engineering" has already been created in the "ems" company of endor.shared-dev.xmatters.com
 - The Engineering group must contain the following shifts, in addition to the default "24x7" shift:
  - "EventRotationLF" shift, which has a rotation based on events, from last to first
  - "EventRotationSF" shift, which has a rotation based on events, from second to first
  - "SchedRot" shift, a shift with a rotation based on schedules
  - "ShiftRot" shift, a shift with a rotation based on shifts
  - "BestO Shift!", a shift used for whitespace tests

Add a Device:
- a user with "Read Only" role, credentials: "rdOnly:1000"
- MY_VDEVICE_PROVIDER protocol provider
- the following user service providers:
 - XMAPIAppleUSP
  - device name: "Apple Push"
 - XMAPIAndroidUSP
  - device name: "Android Push" 
 - XMAPIBBPushUSP
  - device name: "Blackberry Push"
 - XMAPIEmailUSP
 - XMAPIFaxUSP
  - device name: "Fax"
 - XMAPIGenericUSP
  - device name "Generic"
 - XMAPIPagerUSP
 - XMAPISMSUSP
 - XMAPIVoiceIVRUSP
  - device name: "Voice IVR"
 - XMAPIVoiceUSP
 - Active licenses must contain those of Apple.  If they're missing add them by:
  - uploading xmodLicense.txt from http://10.2.0.195:8080/job/KEY-GEN-5.0/
  - then create Apple protocol provider
  - create XMAPIAppleUSP, associate the Apple PP
  - add APPLE_PUSH to the list of available device types

Remove Member from Group/Add Shift to Group:
- User "Team Lead" exists with the following configuration
-- ID: tlead
-- Web Login Password: Password1
-- Roles: Group Supervisor, Support User
- User "Subscription Supervisor" exists with the following configuration
-- ID: subsup
-- Web Login Password: complex
-- Roles: Subscription Supervisor


Integration Builder
- Import Communication Plan CloudToCloud (src/test/setupData/IntegrationBuilder/) to the company and get the Application UUID