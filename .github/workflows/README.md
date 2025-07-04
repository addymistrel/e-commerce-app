# CI/CD Setup for E-Commerce App

This directory contains GitHub Actions workflow configurations for Continuous Integration (CI) and Continuous Deployment (CD) of the E-Commerce Flutter application.

## Workflow Files

### CI Workflow (`ci.yml`)

This workflow runs on every push to the `main` branch and on pull requests targeting the `main` branch. It performs the following tasks:

1. **Testing and Analysis**:
   - Runs `flutter analyze` to check for code issues
   - Runs `flutter test` to execute all tests

2. **Android Build**:
   - Builds an Android APK
   - Uploads the APK as an artifact

### CD Workflow (`cd.yml`)

This workflow runs when a tag with the format `v*` (e.g., `v1.0.0`) is pushed. It handles the deployment process:

1. **Android Deployment**:
   - Builds an Android App Bundle
   - Deploys to Firebase App Distribution

2. **iOS Build**:
   - Builds the iOS app (without code signing)
   - Note: For actual App Store deployment, additional steps would be needed

3. **Web Deployment**:
   - Builds the web version
   - Deploys to Firebase Hosting

## Required Secrets

To use these workflows, you need to set up the following secrets in your GitHub repository:

- `FIREBASE_TOKEN`: Firebase CLI authentication token
- `FIREBASE_ANDROID_APP_ID`: Your Firebase Android app ID
- `FIREBASE_PROJECT_ID`: Your Firebase project ID
- `FIREBASE_SERVICE_ACCOUNT`: Firebase service account JSON (for hosting deployment)

## How to Use

### For Regular Development

Simply push your changes to the `main` branch or create a pull request. The CI workflow will automatically run tests and build the app.

### For Releases

1. Tag your release commit:
   ```bash
   git tag v1.0.0
   git push origin v1.0.0
   ```

2. The CD workflow will automatically build and deploy your app to the configured platforms.

## Customization

You can customize these workflows by editing the YAML files. Common customizations include:

- Changing the Flutter version
- Adding more test steps
- Configuring different deployment targets
- Adding notifications (Slack, email, etc.)
