# Streaming Media Microservice

<Seo/>

<MicroserviceBadge text="Multitenant Microservice" type="multitenant"/>
The streaming media microservice is intended to allow streaming storage of binary
data such as audio and video streams. This feature is under development.

::: warning
This microservice is not fully implemented in SiteWhere 2.0
:::

## Microservice Dependencies

| Microservice                                       | Dependency                                      |
| :------------------------------------------------- | :---------------------------------------------- |
| **[Instance Management](../instance-management/)** | Required to initially bootstrap Zookeeper data. |

## Configuration

### Configuration Schema

[Streaming Media Configuration XML Schema](https://sitewhere.io/schema/sitewhere/microservice/streaming-media/current/streaming-media.xsd)

#### Example Configuration

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context"
	xmlns:sm="http://sitewhere.io/schema/sitewhere/microservice/streaming-media"
	xsi:schemaLocation="
           http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.1.xsd
           http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.1.xsd
           http://www.springframework.org/schema/security http://www.springframework.org/schema/security/spring-security-3.0.xsd
           http://sitewhere.io/schema/sitewhere/microservice/streaming-media http://sitewhere.io/schema/sitewhere/microservice/streaming-media/current/streaming-media.xsd">

	<!-- Allow property placeholder substitution -->
	<context:property-placeholder />

	<!-- Streaming Media -->
	<sm:streaming-media />

</beans>
```
