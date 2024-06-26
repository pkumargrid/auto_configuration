# auto_configuration
----------------------------------------------------------------------------
# Understanding Configuration and Auto-Configuration in Spring Boot

## Difference between Regular Configuration and Auto-Configuration

Regular configuration in Spring involves manually defining and configuring beans using Java configuration classes, XML files, or component scanning. Developers explicitly specify the beans and their dependencies, providing fine-grained control over the application's configuration.

Auto-configuration, on the other hand, is a feature of Spring Boot that automatically configures beans based on the classpath and the presence of certain conditions. Spring Boot analyzes the environment and classpath to provide sensible defaults and pre-configured beans for common use cases, significantly reducing the amount of manual configuration required.

## Conditional Annotations in Regular Configuration Classes

Conditional annotations, such as `@ConditionalOnProperty` or `@ConditionalOnClass`, can be used in regular configuration classes to conditionally enable or disable bean definitions based on specific conditions. These annotations work as expected in regular configuration classes, allowing developers to customize the bean creation process based on various factors such as the presence of certain classes or properties.

## Customizing the Auto-Configuration Process

The auto-configuration process in Spring Boot can be customized in several ways:
- **Excluding Auto-Configuration**: Developers can exclude specific auto-configuration classes using the `@EnableAutoConfiguration` annotation's `exclude` attribute or by setting the `spring.autoconfigure.exclude` property in `application.properties`.
- **Customizing Bean Creation**: Developers can customize the creation of auto-configured beans by providing their own bean definitions with the same names. Spring Boot will prioritize manually defined beans over auto-configured beans.
- **Creating Custom Auto-Configuration**: Developers can create custom auto-configuration classes by implementing the `AutoConfiguration` interface or using the `@Configuration` annotation with `@Conditional` annotations to conditionally enable bean definitions.

## Condition for Tomcat Server to Start on Port 8080

The condition that causes a Tomcat server to start on port 8080 when the application starts is typically controlled by the property `server.port` in Spring Boot's application configuration. If the `server.port` property is not explicitly set in `application.properties` or `application.yml`, the default port used by Spring Boot is 8080. Developers can customize the server port by setting the `server.port` property to a different value in the application configuration.


---
# Exercises
# Spring Boot Auto-Configuration and Debugging Guide

## Overview

This guide provides an overview of debugging auto-configuration and disabling built-in auto-configurations in Spring Boot applications.

## Debugging Auto-Configuration

To debug auto-configuration in a Spring Boot application, follow these steps:

1. **Enable Debug Logging**: Set the log level to `DEBUG` for the `org.springframework.boot.autoconfigure` package in your logging configuration. This allows you to see detailed information about which auto-configuration classes are being processed and which beans are being created during application startup.

   Example using `application.properties`:
   ```
   logging.level.org.springframework.boot.autoconfigure=DEBUG
   ```

   Example using `application.yml`:
   ```yaml
   logging:
     level:
       org.springframework.boot.autoconfigure: DEBUG
   ```

2. **View Logs**: With debug logging enabled, detailed logs will be displayed in your console or log files during application startup. These logs show the auto-configuration process, including which auto-configuration classes are evaluated and which conditions are checked.

## Disabling Built-In Auto-Configurations

You can disable built-in auto-configurations in Spring Boot applications based on specific conditions. Here's how:

1. **Using Conditional Annotations**: Use Spring Boot's `@ConditionalOn...` annotations, such as `@ConditionalOnProperty`, to conditionally enable or disable auto-configuration based on specific conditions. For example, you can use `@ConditionalOnProperty` to enable or disable auto-configuration based on the presence or value of a configuration property.

2. **Removing Built-In Auto-Configurations**: You can remove built-in auto-configurations by using the `exclude` attribute of the `@EnableAutoConfiguration` annotation or by specifying the exclusions in the `spring.autoconfigure.exclude` property in `application.properties`. This allows you to selectively disable specific built-in auto-configurations that are not required for your application.

## Additional Notes

- Debugging auto-configuration and customizing the auto-configuration process gives you fine-grained control over the configuration of your Spring Boot application, allowing you to tailor it to your specific requirements and conditions.

---

Feel free to expand upon each section with additional details, examples, or instructions based on your specific needs and project context.

---

Feel free to expand upon each section with additional details or examples based on your specific requirements and project context.
