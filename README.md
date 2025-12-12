# PAWCHA - Taking a Look at Your Food Receipts

Pawcha Agent leverages the power of Large Language Models (LLMs) to analyze and extract structured data from images of food receipts. By simply providing an image of a receipt, the agent can identify key information such as the vendor's name, date, and the total amount. This extracted data is then saved to a database for easy access and management.

## Features

- **Information Extraction**: Automatically extracts the vendor's name, date, and total amount from a receipt image.
- **Data Storage**: Saves the extracted information into a structured database.
- **Simple Interface**: Provides a straightforward web interface for uploading receipt images.
- **Dockerized**: The entire application is containerized for easy deployment and scalability.

## Demo

Comming soon!

## Methods

The agent uses a combination of Optical Character Recognition (OCR) and a powerful Large Language Model to perform its tasks. The process is as follows:

1. **Image Upload**: The user uploads an image of a food receipt through the web interface.
2. **OCR Processing**: The uploaded image is processed by an OCR tool to extract the raw text.
3. **LLM Analysis**: The extracted text is then passed to a Large Language Model, which is prompted to identify and extract the vendor's name, the date of the receipt, and the total amount.
4. **Data Storage**: The extracted information is saved to a SQLite database.

## Architecture

- **Frontend**: A simple HTML page (`frontend/index.html`) that allows users to upload receipt images.
- **Backend**: A Python-based backend built with FastAPI that handles the image uploads, processing, and data storage.
  - `main.py`: The main entry point for the backend, which defines the API endpoints.
  - `agent.py`: Contains the core logic of the agent, including the interaction with the OCR tool and the LLM.
  - `tools.py`: Provides the tools for the agent to use, such as the OCR tool and the database tool.
  - `prompt_schema.py`: Defines the schema for the prompts used by the LLM.
  - `media/receipts.db`: The SQLite database where the extracted information is stored.
- **Docker**: The application is fully containerized using Docker, with a `docker-compose.yml` file for easy setup.

## Setup and Installation

To set up and Pawcha, you will need to have Docker and Docker Compose installed on your system.

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/food-receipt-agent.git
   cd food-receipt-agent
   ```

2. **Create a `.env` file**:
   Create a `.env` file in the root of the project and add your OpenAI API key:
   ```
   OPENAI_API_KEY=your-api-key
   ```

3. **Build and run the application with Docker Compose**:
   ```bash
   docker-compose up --build
   ```

   This will build the Docker images for the frontend and backend and start the application.

## Usage

Once the application is running, you can access the web interface by navigating to `http://localhost:80` in your web browser.

From there, you can upload an image of a food receipt, and the agent will process it and save the extracted information to the database.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
