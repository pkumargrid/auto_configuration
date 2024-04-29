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

Feel free to expand upon each section with additional details or examples based on your specific requirements and project context.
