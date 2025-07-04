# Setting Up GitHub Secrets for CI/CD

This document explains how to set up the required GitHub secrets for the CI/CD pipeline of the E-Commerce Flutter app.

## Required Secrets

The following secrets need to be configured in your GitHub repository:

1. `FIREBASE_TOKEN`
2. `FIREBASE_ANDROID_APP_ID`
3. `FIREBASE_PROJECT_ID`
4. `FIREBASE_SERVICE_ACCOUNT`

## How to Set Up GitHub Secrets

1. Go to your GitHub repository
2. Click on "Settings" tab
3. In the left sidebar, click on "Secrets and variables" > "Actions"
4. Click on "New repository secret"
5. Add each of the required secrets as described below

## Obtaining the Secret Values

### FIREBASE_TOKEN

This is a Firebase CLI authentication token:

1. Install Firebase CLI if you haven't already:
   ```bash
   npm install -g firebase-tools
   ```

2. Login to Firebase:
   ```bash
   firebase login:ci
   ```

3. Copy the token that is displayed after successful authentication

### FIREBASE_ANDROID_APP_ID

This is your Firebase Android app ID:

1. Go to the [Firebase Console](https://console.firebase.google.com/)
2. Select your project
3. Go to Project Settings (gear icon)
4. In the "Your apps" section, find your Android app
5. Copy the App ID (it looks like `1:123456789012:android:abcdef1234567890`)

### FIREBASE_PROJECT_ID

This is your Firebase project ID:

1. Go to the [Firebase Console](https://console.firebase.google.com/)
2. Select your project
3. The project ID is displayed at the top of the Project Settings page

### FIREBASE_SERVICE_ACCOUNT

This is a JSON key for a Firebase service account:

1. Go to the [Firebase Console](https://console.firebase.google.com/)
2. Select your project
3. Go to Project Settings > Service accounts
4. Click "Generate new private key"
5. Download the JSON file
6. Copy the entire contents of the JSON file

## Verifying Your Setup

After setting up all the secrets, you can verify that they are correctly configured:

1. Go to your GitHub repository
2. Click on "Actions" tab
3. Select one of the workflows
4. Click "Run workflow"
5. Check if the workflow runs successfully

If there are any issues with the secrets, the workflow will fail and provide error messages that can help you troubleshoot.

## Security Considerations

- Never commit these secrets to your repository
- Regularly rotate your Firebase service account keys
- Limit the permissions of the service account to only what is needed for CI/CD
