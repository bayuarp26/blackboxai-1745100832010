
Built by https://www.blackbox.ai

---

```markdown
# Tracking Link Generator

## Project Overview

The Tracking Link Generator is a simple web application that allows users to create tracking links for URLs. It captures tracking data such as IP addresses and geolocation (latitude and longitude) when the tracking link is accessed. This information can be useful for analytics and tracking user engagement. The application is built with Node.js and Express.

## Installation

To set up the Tracking Link Generator application on your local machine, follow the steps below:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/tracking-link-generator.git
   cd tracking-link-generator
   ```

2. Install the required dependencies:
   ```bash
   npm install
   ```

3. Start the server:
   ```bash
   npm start
   ```

4. Open your browser and navigate to `http://localhost:3000`.

## Usage

### Create a Tracking Link

To create a tracking link, make a POST request to the `/create-link` endpoint with the URL you want to track. For example:

```bash
curl -X POST http://localhost:3000/create-link -H "Content-Type: application/json" -d '{"url": "https://example.com"}'
```

The response will include the generated tracking URL.

### Accessing Tracking Page

To view the tracking page for a specific link, navigate to:
```
http://localhost:3000/track/{id}
```
where `{id}` is the unique identifier generated for your tracking link.

### Send Tracking Data

When a user accesses the tracking link, tracking data can be sent to the server using a POST request to `/track/{id}/data`. An example payload would be:

```json
{
  "latitude": "37.7749", 
  "longitude": "-122.4194"
}
```

### Redirect to Original URL

To redirect users to the original URL after tracking, use:
```
http://localhost:3000/redirect/{id}
```
This will redirect the user to the original URL associated with the tracking link.

## Features

- Create tracking links for any valid URL.
- Capture and log tracking data such as IP address and geolocation.
- Serve a tracking page for each generated link.
- Redirect users to the original URL after capturing tracking data.
- In-memory storage for links and tracking data (note: data will not persist after server restarts).

## Dependencies

The project relies on the following npm packages, defined in `package.json`:

- [express](https://www.npmjs.com/package/express): Fast, unopinionated, minimalist web framework for Node.js
- [uuid](https://www.npmjs.com/package/uuid): Generate RFC-compliant UUIDs.

## Project Structure

Here’s the structure of the project:

```
tracking-link-generator/
├── node_modules/           # npm packages
├── public/                 # static files (e.g., HTML pages)
│   └── track.html          # tracking page
├── package.json            # project dependencies and scripts
├── package-lock.json       # exact version dependencies
└── server.js               # main server file
```

## License

This project is licensed under the MIT License. See the LICENSE file for more details.

```

Feel free to modify any specific sections, like the repository URL or add licensing details as applicable to your project!