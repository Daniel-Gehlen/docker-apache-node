# Docker, Apache e Node

## Technical Report

### Challenge:
The challenge consisted of creating a development and production environment for a web application using Docker Compose, Apache, Node.js, and other web technologies such as HTML, CSS, and JavaScript.

### Proposed Solution:
To meet the challenge requirements, three services were created in the docker-compose.yml file:

1. **Web Service (web):**
   - Uses the httpd:latest image of Apache to serve static HTML files.
   - Maps port 80 of the container to port 80 of the host, allowing access to the application via a browser.
   - Uses a volume to mount the host's html directory inside the Apache's default directory.

2. **Development Service (dev):**
   - Uses the node:latest image to create a development environment.
   - Executes the npm run dev command, assuming there is a script configured in the package.json file to start a development server.
   - Maps port 3000 of the container to port 3000 of the host.
   - Uses a volume to mount the host's html directory inside the /app directory in the container.

3. **Production Service (prod):**
   - Also uses the node:latest image.
   - Executes the npm start command, assuming there is a script configured in the package.json file to start a production server.
   - Maps port 8080 of the container to port 8080 of the host.
   - Uses a volume to mount the host's html directory inside the /app directory in the container.

### Results Achieved:
- A complete environment was built for the development and production of a web application.
- Docker Compose simplified the management and configuration of containers, providing a consistent and replicable environment.
- The use of Apache as a web server and Node.js for the development and production environment allows for a flexible and scalable configuration.

### Next Steps:
- Explore the integration of other technologies and services, such as databases, load balancers, and CI/CD systems.
- Refine the configuration of the development environment to improve developers' efficiency and productivity.
- Implement scalability and monitoring strategies to ensure the performance and availability of the application in production.
