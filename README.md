# chap-docker

[![Powered by Docker](https://img.shields.io/badge/Powered%20by-Docker-blue?style=flat-square&logo=docker)](https://www.docker.com)

Climate Health Analysis Platform Docker

## How to Run

1.  **Set up your environment variables:**

    - This project requires a `.env` file for configuration.
    - Copy the example file: `cp .env.example .env`
    - Open the newly created `.env` file and fill in the required values:
      - `GOOGLE_SERVICE_ACCOUNT_EMAIL`: Your Google Service Account email.
      - `GOOGLE_SERVICE_ACCOUNT_PRIVATE_KEY`: Your Google Service Account private key. Make sure to format the private key correctly, including the `-----BEGIN PRIVATE KEY-----` and `-----END PRIVATE KEY-----` markers, and replace newline characters with `\n` if you are putting it on a single line (though it's generally better to keep the newlines as in the original key file).

    Your `.env` file should look something like this:

    ```
    GOOGLE_SERVICE_ACCOUNT_EMAIL=your-service-account@example.iam.gserviceaccount.com
    GOOGLE_SERVICE_ACCOUNT_PRIVATE_KEY="-----BEGIN PRIVATE KEY-----\nYOUR_MULTI_LINE_PRIVATE_KEY_HERE\n-----END PRIVATE KEY-----\n"
    ```

2.  **Run the project using Docker Compose:**

    - Execute the following command in your terminal:
      ```bash
      docker compose up -d
      ```
    - This command will pull the necessary Docker images (if needed) and start the services defined in `compose.yml` in detached mode (`-d`).

3.  **Accessing the application:**
    - Once the containers are up and running, the application will be available at [http://localhost:8000](http://localhost:8000).
    - You can verify that the application is running correctly by visiting the health check endpoint: [http://localhost:8000/health](http://localhost:8000/health).

## Stopping the application

- To stop the running services, use the command:
  ```bash
  docker-compose down
  ```
