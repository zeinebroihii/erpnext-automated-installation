ERPNext Docker Setup

Overview

This repository contains a Docker Compose setup for deploying ERPNext
version 13 with Nginx as a reverse proxy. It includes configuration for
essential ERPNext services such as backend, database, Redis, and more.
The setup also integrates custom ERPNext apps from GitHub repositories.

Table of Contents

\- \[Features\](#features) - \[Getting Started\](#getting-started) -
\[Configuration\](#configuration) - \[Usage\](#usage) - \[Custom
Apps\](#custom-apps) - \[Contributing\](#contributing) -
\[License\](#license)

Features

\- ERPNext v13: The main application. - Docker Compose: For
orchestrating multi-container Docker applications. - Nginx: Configured
as a reverse proxy. - Custom Apps: Integration of additional ERPNext
apps from GitHub. - MariaDB: Database service. - Redis: For caching and
queuing. - WebSocket Support: For real-time features.

Getting Started

Prerequisites

\- Docker - Docker Compose

Installation

1\. Clone the Repository:

\`\`\`bash git clone
https://github.com/yourusername/erpnext-docker-setup.git cd
erpnext-docker-setup \`\`\`

2\. Configure Environment Variables:

Create a \`.env\` file in the root directory of the project and set the
following environment variables:

\`\`\`env DB_HOST=db DB_PORT=3306 REDIS_CACHE=redis-cache:6379
REDIS_QUEUE=redis-queue:6379 SOCKETIO_PORT=9000 \`\`\`

3\. Start the Services:

\`\`\`bash docker-compose up -d \`\`\`

Configuration

Docker Compose

The \`docker-compose.yml\` file defines the following services:

\- backend: ERPNext backend service. - configurator: Sets configuration
parameters. - create-site: Creates a new ERPNext site and installs
apps. - db: MariaDB database service. - frontend: ERPNext frontend
service. - queue-long: Long-running background tasks. - queue-short:
Short-running background tasks. - redis-queue: Redis for queue
management. - redis-cache: Redis for caching. - scheduler: Scheduled
tasks. - websocket: WebSocket service for real-time features. - nginx:
Nginx as a reverse proxy.

Nginx Configuration

The \`nginx.conf\` file is used to configure Nginx as a reverse proxy
for the ERPNext frontend service. It forwards requests to the frontend
container and handles WebSocket connections.

Usage

1\. Access ERPNext:

Open your browser and go to
\[http://localhost:8080\](http://localhost:8080) to access the ERPNext
application.

2\. Check Logs:

To view the logs of a specific service, use:

\`\`\`bash docker-compose logs \<service-name\> \`\`\`

Custom Apps

This setup integrates two custom ERPNext apps:

\- erpnext-restaurant: A restaurant management plugin. - frappe_helper:
A helper app for Frappe.

These apps are installed during the site creation process.

Contributing

If you\'d like to contribute to this project, please fork the repository
and submit a pull request. Contributions are welcome!

Notes:

1\. Formatting: Ensure code blocks and commands are correctly formatted.
2. Links: Replace placeholders such as
\`https://github.com/yourusername/erpnext-docker-setup.git\` with actual
URLs if they are specific. 3. Add a LICENSE File: If you have not
already, create a \`LICENSE\` file with the details of the MIT License
or any other license you choose.

Feel free to adjust or expand upon this template as needed!
