# Firebase Emulator Dockerfiles

This directory contains Dockerfiles for individual Firebase emulators that can be deployed to Render.

## Available Dockerfiles

- `Dockerfile.auth` - Firebase Authentication Emulator (port 9092)
- `Dockerfile.functions` - Firebase Functions Emulator (port 9093)
- `Dockerfile.firestore` - Firebase Firestore Emulator (port 9091)
- `Dockerfile.storage` - Firebase Storage Emulator (port 9094)
- `Dockerfile.all` - All emulators running together

## Configuration Notes

- Each Dockerfile is configured to use the ports specified in your `firebase.json`
- The `PORT` environment variable is set for Render compatibility
- You'll need to copy the following files to your Render deployment:
  - `firebase.json`
  - `firestore.rules` (for Firestore)
  - `firestore.indexes.json` (for Firestore)
  - `storage.rules` (for Storage)
  - `functions/` directory (for Functions)

## Deployment to Render

1. Create a new Web Service on Render
2. Point it to your GitHub repository
3. Select the appropriate Dockerfile for the service you want to deploy
4. Make sure to expose the correct port in your Render service settings
5. Add any required environment variables

Note: For multi-port services, you may need to use a reverse proxy or deploy each emulator separately.