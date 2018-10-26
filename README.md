# qmetry-test-management-gradle-plugin
QMetry Test Management plugin for Gradle has been designed to seamlessly integrate your CI/CD pipeline with QMetry.

QTMGradlePlugin uploads result file(s) generated in a Gradle project to QTM Enterprise server. The plugin, if used in a gradle project, provides an additional gradle task 'qtmUploadResults'

## To use the plugin,

Use the plugin from anywhere in your gradle project, by including the following code in 'build.gradle' file...
```
plugins
{
	id 'com.qmetry.QTMGradlePlugin' version '1.0'
}

qtmConfig
{
	qtmUrl='https://testmanagement.qmetdry.com/'
	qtmAutomationApiKey='zEzs7iy77D8ARWX8xMFzJRZTzb66W0LCyaK6xdec'
	automationFramework='JUNIT'
	testResultFilePath='/test-results/test/TEST-ispl.sample.AppSecondTest.xml'
	testSuiteId='STR-TS-01'
	project='Demo Project'
	platform='Chrome'
	release='Default Release'
	cycle='Default Cycle'
	build='Demo Build'
}

```

Use the following command from your project.
```
gradle test qtmUploadResults
```


The task qtmUploadResults always looks for qtmConfig in build.gradle file of your project. Provide following details :-

* **qtmUrl** - Url to QMetry Test Management instance
* **qtmAutomationApiKey** - Automation Key
* **automationFramework** - JUNIT/TESTNG/CUCUMBER/QAS/HPUFT
* **testResultFilePath** - Path to result file (or directory for multiple files) relative to build directory
* **testSuiteId (optional)** - Id or Entity key of the target test suite.
* **project** - Project Id or Project Key or Project name
* **platform (Optional)** - Platform Id or Platform Name
* **release (Optional)** - Release Id or Release name
* **cycle (Optional)** - Cycle Id or Cycle Name
* **build (Optional)** - Build Id or Build name
