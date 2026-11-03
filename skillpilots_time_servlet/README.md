# SkillPilots – Time Servlet Project

This Maven web application implements the SkillPilots task:

> Create a servlet that returns the current server time in JSON format.

## Requirements
- JDK 17 or later
- Apache Maven
- Apache Tomcat 10.1 or later (Jakarta Servlet 6)

## Run in IntelliJ IDEA / Eclipse
1. Extract the ZIP file.
2. Open the `skillpilots_time_servlet` folder as a Maven project.
3. Wait for Maven to download dependencies.
4. Build the project:
   ```bash
   mvn clean package
   ```
5. Deploy `target/time-servlet.war` to Tomcat 10.1.
6. Start Tomcat and open:
   `http://localhost:8080/time-servlet/api/time`

Example response:
```json
{"currentTime":"2026-11-03T16:42:00"}
```
The actual value is generated from the server clock.

## Implementation
- `TimeServlet.java` creates the servlet.
- `doGet()` reads `LocalDateTime.now()`.
- The response content type is `application/json`.
- `@WebServlet("/api/time")` maps the endpoint to `/api/time`.
- `web.xml` is included as the web application descriptor; the annotation supplies the servlet mapping.

## Important
This project uses `jakarta.servlet` and therefore requires Tomcat 10.1+.
It is not compatible with Tomcat 9 without changing the servlet imports and dependency.
