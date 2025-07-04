## Build a Modern E-Commerce App with Flutter, Firebase, BLoC, and Clean Architecture

![Flutter CI](https://github.com/yourusername/e-commerce-app/workflows/Flutter%20CI/badge.svg)
![Flutter Tests](https://github.com/yourusername/e-commerce-app/workflows/Flutter%20Tests/badge.svg)

Welcome to the Project E-Commerce App! This guide will walk you through the steps to create a fully functional e-commerce application using Flutter and Firebase, following Clean Architecture principles and managing state with BLoC.

## Features

- User authentication (Sign-up, Login) using Firebase.
- Product listing and category filtering.
- Shopping cart functionality.
- Real-time product data updates with Firestore.
- Organized codebase using Clean Architecture for scalability and maintainability.
- Continuous Integration and Deployment with GitHub Actions.

## Technologies Used

- **Flutter**: For building a cross-platform mobile application.
- **Firebase**: For authentication, Firestore database, and cloud storage.
- **BLoC**: For state management.
- **Dart**: The programming language used with Flutter.
- **GitHub Actions**: For CI/CD pipelines.

## CI/CD Pipeline

This project uses GitHub Actions for Continuous Integration and Deployment:

- **CI Pipeline**: Automatically runs tests, code analysis, and builds the app on every push to main and pull requests.
- **CD Pipeline**: Automatically deploys the app to Firebase App Distribution and Firebase Hosting when a new version tag is pushed.

For more details on the CI/CD setup, see the [CI/CD documentation](.github/workflows/README.md).