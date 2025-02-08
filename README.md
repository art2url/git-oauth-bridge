
# GitHub OAuth Server

This repository provides a simple Node.js + Express backend that handles GitHub OAuth authentication. It exchanges the GitHub authorization code for an access token and retrieves user information.

## Repository Name Suggestion
**git-oauth-bridge**

## Features
- Handles GitHub OAuth authentication
- Exchanges authorization code for access token
- Retrieves authenticated GitHub user's information
- Configurable via environment variables
- CORS-enabled for integration with front-end applications

## Prerequisites
- Node.js and npm installed on your machine
- A GitHub OAuth application with Client ID and Client Secret

## Setup

1. **Clone the Repository:**
```bash
git clone https://github.com/art2url/git-oauth-bridge.git
cd git-oauth-bridge
```

2. **Install Dependencies:**
```bash
npm install
```

3. **Configure Environment Variables:**
Create a `.env` file in the root directory with the following content:
```env
GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret
PORT=3000 # Optional, defaults to 3000
```

4. **Run the Server:**
```bash
node server.js
```

## API Endpoints

### POST `/auth/github`
Handles GitHub OAuth authentication by exchanging the authorization code for an access token and retrieving user information.

#### Request Body:
```json
{
  "code": "<github_authorization_code>"
}
```

#### Successful Response:
```json
{
  "access_token": "<github_access_token>",
  "github_username": "<github_username>"
}
```

#### Error Responses:
- **400 Bad Request:** If the authorization code is missing or invalid.
- **500 Internal Server Error:** If there's an issue during the OAuth flow.

## License
This project is licensed under the MIT License.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
