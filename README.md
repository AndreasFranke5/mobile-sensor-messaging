# Mobile Sensor Messaging App

Flutter application for real-time IoT sensor monitoring and device messaging over MQTT.

The app connects to hardware sensors via an MQTT broker, displays live telemetry, and supports bi-directional messaging between the mobile client and connected devices. A Firebase backend handles authentication, push notifications, and data persistence.

## Architecture

```
flutter-app/      Flutter/Dart mobile client (Android/iOS/Web)
arduino/          Embedded firmware for sensor nodes
raspberry-pi/     MQTT relay and local data processing
backend-server/   Firebase Functions, Auth, and Realtime Database
hardware/         Hardware schematics and component notes
```

## Stack

| Layer | Technology |
|---|---|
| Mobile frontend | Flutter 3, Dart, BLoC |
| Device communication | MQTT (`mqtt_client`) |
| Push notifications | Firebase Messaging |
| Auth and persistence | Firebase Auth, Firebase Realtime Database |
| Sensor firmware | Arduino C++ / ESP32 |
| State management | BLoC + injectable DI |
| QR pairing | `mobile_scanner` |

## Features

- Real-time sensor data over MQTT
- Firebase authentication with Google Sign-In
- Push notifications for threshold alerts
- QR code-based device pairing
- BLoC state management with freezed data classes
- Multi-platform Flutter build (Android, iOS, Web)

## Getting started

```bash
cd flutter-app
flutter pub get
flutter run
```

A Firebase project with Realtime Database, Authentication, and Messaging enabled is required. Update `google-services.json` / `GoogleService-Info.plist` for your Firebase project before building.
