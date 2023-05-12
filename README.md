# MuleSoft CI CD using GitHub Actions

## Prerequisites
- If you are using the HTTP Listener as source for your flow, you need to set its host to `0.0.0.0` and its port to `${http.port}`
- [Click Here for more information](https://docs.mulesoft.com/mule-runtime/4.4/deploy-to-cloudhub)

## Configure the CloudHub Deployment Strategy (pom.xml)

As we waned to automate the Mule project deployment using Maven commands, the first step is to modify our `pom.xml` file and add the Cloudhub deployment strategy. Open your `pom.xml` file and inside the `plugin` element with the `groupId` equal to `org.mule.tools.maven` add the configuration tag like below

```
<configuration>
	<!--  Adding the below tag for CI-CD Purpose -->
	<cloudHubDeployment>
		<uri>https://anypoint.mulesoft.com</uri>
		<muleVersion>${mule.version}</muleVersion>
		<username>${anypoint.username}</username>
		<password>${anypoint.password}</password>
		<environment>${env}</environment>
		<applicationName>${app.name}</applicationName>
		<businessGroup>${businessGroup}</businessGroup>
		<workerType>${wokerType}</workerType>
		<workers>${workerSize}</workers>
		<objectStoreV2>true</objectStoreV2>
	</cloudHubDeployment>
	<!--  Adding the below tag for CI-CD Purpose -->
</configuration>
```
