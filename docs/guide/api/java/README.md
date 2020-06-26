# Using SiteWhere Java API

<Seo/>

SiteWhere provides a Java API for accessing the REST API of SiteWhere. This guide shows how to use
SiteWhere Java API to interact with an instance of SiteWhere.

## Importing the Library

SiteWhere Java Client library is published on [Maven Central](https://search.maven.org/search?q=a:sitewhere-java-client)
for using dependency management tools, such as Apache Maven or Gradle.

If you are using [Apache Maven](https://maven.apache.org/), add the following dependency to your `pom.xml`.

```xml
<dependency>
    <groupId>com.sitewhere</groupId>
    <artifactId>sitewhere-java-client</artifactId>
    <version>2.1.x</version>
</dependency>
```

If you are using [Gradle](https://gradle.org/), add the following dependency to your `build.gradle`.

```groovy
implementation 'com.sitewhere:sitewhere-java-client:2.1.x'
```

## Creating a client instance

A new client with the default settings may be created as follows:

```java
ISiteWhereClient client = SiteWhereClient.newBuilder()
    .build().initialize();
```

The default settings are:

| Attribute | Value     |
| :-------- | :-------- |
| Protocol  | HTTP      |
| Hostname  | localhost |
| Port      | 80        |
| Username  | admin     |
| Password  | password  |

::: warning
Since SiteWhere 2.1.x the default `Port` number changed from 8080 to 80.
:::

Note that the `initialize()` method must be called before using the client. This sets
up the template and connects to the server to acquire a JWT.

To change the default connection settings use:

```java
SiteWhereClient client = SiteWhereClient.newBuilder()
    .withConnectionTo("https", "myhost", 8081)
    .build().initialize();
```

To connect as a different user use:

```java
SiteWhereClient client = SiteWhereClient.newBuilder()
    .forUser("myuser", "mypassword")
    .build().initialize();
```

## Interacting with SiteWhere Object Model

Once the client has been initialized, methods on it may be invoked to interact with the data
model on the remote SiteWhere instance. There are two types of calls, global calls and
tenant-specific calls.

The image below shows an UML Class Diagram of SiteWhere Object Model that can help you undestand
the component of the system.

<InlineImage src="/images/guide/api/object-model.png" caption="SiteWhere Object Model UML Class Diagram"/>

### Global Calls

For global calls, no extra information is required in order to make the invocation.

These are the **Global** calls of SiteWhere API:

- [System API](./system-api/)
- [Users API](./user-api/)
- [Tenant API](./tenant-api/)

### Tenant Calls

For calls that are tenant-specific, more information must be passed along with each method invocation.
You must provide the tenant id and tenant authentication token which are passed as headers to the REST
call (along with the JWT used for all calls).

These are the **Tenant** calls of SiteWhere API:

- [Area API](./area-api/)
- [Area Type API](./area-type-api/)
- [Asset API](./asset-api/)
- [Asset Type API](./asset-type-api/)
- [Batch Operations API](./batch-operations-api/)
- [Command Invocation API](./command-invocations-api/)
- [Customer API](./customer-api/)
- [Customer Type API](./customer-type-api/)
- [Device API](./device-api/)
- [Device Assignment API](./assignment-api/)
- [Device Command API](./device-command-api/)
- [Device Event API](./device-event-api/)
- [Device Group API](./device-group-api/)
- [Device State API](./device-state-api/)
- [Device Status API](./device-state-api/)
- [Device Type API](./device-type-api/)
- [Schedule API](./schedule-api/)
- [Scheduled Job API](./scheduled-job-api/)
- [Zone API](./zone-api/)
