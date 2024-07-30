# URL Shortener App - Frontend

This is the frontend of the URL Shortener application that allows users to shorten long URLs. The frontend is built with React and interacts with a backend developed using Spring Boot and a PostgreSQL database. The application can be containerized using Docker.

## Features
- Shorten long URLs.
- Redirect shortened URLs to the original URL.
- View all shortened URLs.
- Delete shortened URLs.

## Technologies Used
- **Frontend**: React
- **Backend**: Spring Boot
- **Database**: PostgreSQL
- **Containerization**: Docker

## Prerequisites
Before you begin, ensure you have the following installed on your machine:
- [Node.js](https://nodejs.org/) (for frontend development)

## Installation
1. **Clone the repository:**

    ```bash
    git clone https://github.com/ShaunaMartyn123/frontend.git
    ```

2. **Setup the frontend:**

    ```bash
    cd frontend
    npm install
    ```

## Running the Application

### Without Docker

1. **Run the frontend:**

    Navigate to the frontend directory and start the application:

    ```bash
    cd frontend
    npm start
    ```

## Adjusting API Endpoints

To ensure the frontend communicates correctly with the backend, you need to update the API endpoints in your frontend code to match the URL created by the backend container. 

For example, if your backend container is running on port `54961`, update the API endpoints as follows:

1. Open the files where API calls are made, such as `src/components/UrlForm.js` and `src/components/UrlList.js`.

2. Replace the default localhost URL with the correct port for your backend container. 

For example, in `src/components/UrlForm.js`:

```javascript
try {
    const response = await axios.post('http://localhost:54961/api/urls', null, { params: { originalUrl } });
    onShorten(response.data);
    setOriginalUrl('');
    setError('');
} catch (error) {
    setError('Failed to shorten the URL');
} ```

## Usage

1. **Access the application:**

    Open your web browser and go to `http://localhost:3000`.

2. **Shorten a URL:**

    Enter a long URL in the input field and click the "Shorten" button. The shortened URL will be displayed.

3. **View all shortened URLs:**

    The list of all shortened URLs can be viewed on the main page.

4. **Delete a shortened URL:**

    Click the "Delete" button next to a shortened URL to remove it from the list.


