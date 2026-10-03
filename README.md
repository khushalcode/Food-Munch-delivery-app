# Food Munch: Delivery App

The delivery partner app. Accept jobs, navigate to pickup and drop-off, track earnings.

| | |
|---|---|
| Package | `com.foodmunch.delivery` |
| Version | 1.0.0+1 |
| Flutter / Dart | Flutter 3.38+ (stable), Dart `^3.10.0` |
| Backend | `https://foodmunch.com` |

## Features

- **Jobs:** realtime order and ride requests with sound alerts, accept / reject, status updates
- **Navigation:** Google Maps with route polylines, pickup and drop-off markers, live location sharing (foreground service)
- **Earnings:** earning reports with charts, disbursements, wallet and cash in hand
- **Account:** profile, vehicle details, refer and earn, notifications, chat with customers and stores
- **Modules:** delivery module and ride module
- **Other:** multi-language (EN, AR, BN, ES)

## Folder structure

```
lib/
├── api/
├── common/
├── features/     # auth, dashboard, delivery_module, ride_module, disbursement,
│                 # earning_reports, my_account, profile, refer_and_earn, chat, ...
├── helper/
├── interface/
├── theme/
├── util/
└── main.dart
```

Every feature folder follows `controllers / domain / screens / widgets`.

## Run and build

```bash
flutter pub get
flutter run
flutter build apk --release --split-per-abi
```

## Configuration

- App name and backend URL: `lib/util/app_constants.dart`
- Firebase: `android/app/google-services.json`, `ios/Runner/GoogleService-Info.plist`
- Google Maps key: `AndroidManifest.xml` (`com.google.android.geo.API_KEY`)
- Location permission ("allow all the time") is required for background tracking
- Signing: see the [root README](../README.md#release-signing)

## CI

Built automatically as `delivery-apk` by the [root workflow](../.github/workflows/build-apk.yml).