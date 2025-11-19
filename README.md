# NST BLR Superstars API

A simple Express.js API to manage and display user profiles for Newton School Bangalore Superstars.

## Features

- View list of all users
- View individual user profiles
- JSON API endpoints for programmatic access
- Rate limiting for API protection (100 requests per 15 minutes per IP)

## Installation

```bash
npm install
```

## Running the Application

```bash
npm start
```

The server will start on http://localhost:3000

## API Routes

### Web Routes (HTML)

- `GET /` - Displays a list of all users
- `GET /:username` - Displays the profile page for a specific user

### API Routes (JSON)

- `GET /api/users` - Returns an array of all usernames
- `GET /api/users/:username` - Returns the JSON data for a specific user

## Data Structure

User data is stored in JSON files in the `data/` folder. Each file should be named `{username}.json` and contain:

```json
{
  "username": "demo",
  "name": "Demo User",
  "email": "demo@example.com",
  "bio": "This is a demo user profile",
  "location": "Bangalore, India",
  "customization": {
    "backgroundColor": "#2c3e50",
    "backgroundImage": "",
    "profileImage": "https://via.placeholder.com/150"
  }
}
```

### Customization Options

The `customization` object is optional and allows users to personalize their profile pages:

- **backgroundColor**: Hex color code for the page background (e.g., `"#2c3e50"`)
- **backgroundImage**: URL to a background image (leave empty `""` for solid color)
- **profileImage**: URL to a profile picture

**Note**: Text color is automatically calculated based on the background color to ensure optimal contrast and readability.

## Adding New Users

To add a new user, create a new JSON file in the `data/` folder with the user's information following the structure above. The `customization` object is optional - if omitted, default styling will be used.
