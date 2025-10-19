## New Year's Eve Party Guest List

A simple, collaborative web application for managing a shared guest list for New Year's Eve celebrations.

### Features

- **Real-time Synchronization**: The guest list is stored in a public JSON document on `jsonblob.com` and automatically refreshes every 15 seconds
- **Collaborative**: Multiple users can add or remove guests simultaneously
- **Festive UI**: Beautiful gradient design with animated fireworks background
- **Responsive**: Works seamlessly on desktop and mobile devices

### How It Works

- The guest list is stored in a public JSON blob at `jsonblob.com`
- The page automatically fetches fresh data every 15 seconds to stay in sync
- When adding or removing guests, the application sends a `PUT` request to update the JSON blob
- Each guest gets a unique avatar with their initials and a deterministic color based on their name

### Setup Instructions

If you want to start with a fresh guest list, create a new JSON blob:

```bash
curl -s -D - -X POST \
  -H "Content-Type: application/json" \
  -d '{"people":[]}' \
  https://jsonblob.com/api/jsonBlob
```

The response will include a `Location` header with the new blob URL. Copy this URL and replace it in the `DATA_URL` constant in `index.html`.

### Technologies Used

- Pure JavaScript (no frameworks)
- Tailwind CSS for styling
- Stage.js for fireworks animation
- JSONBlob API for data persistence
