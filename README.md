# 📱 TrackNPlay

## 📌 Overview
TrackNPlay is an Android app that tracks how much time users spend on apps (especially games), lets them set daily limits, and provides simple analytics on usage.

---

## 🛠️ Tech Stack
- Language: Java
- IDE: Android Studio
- Backend: Firebase (Authentication + Realtime Database)
- Android APIs:
  - UsageStatsManager
  - NotificationManager
  - SharedPreferences
- Charts: MPAndroidChart

---

## Core Architecture

### 🔹 Authentication System
- Firebase Authentication
- Handles:
  - User registration (`createUserWithEmailAndPassword`)
  - User login (`signInWithEmailAndPassword`)
- User data stored in Firebase Realtime Database using UID

---

### 🔹 Usage Tracking System
- Built using `UsageStatsManager`
- Tracks:
  - Time spent per app
  - Last usage time
- Data:
  - Pulled for last 24 hours
  - Filtered and sorted before display

---

### 🔹 App List Display
- Custom adapter (`AppsAdapter`)
- Displays:
  - App name
  - App icon
  - Time spent
  - Usage percentage

---

### 🔹 Profile System
- Retrieves user data from Firebase
- Allows editing of:
  - Name
  - Email
  - Username
  - Password
- Changes updated in Realtime Database

---

### 🔹 Limit System
- Implemented using `SeekBar`
- User sets daily usage limit
- Value stored using `SharedPreferences`
- Compared against daily usage

---

### 🔹 Notification System
- Uses `NotificationManager`
- Trigger:
  - When daily usage exceeds user limit
- Sends reminder notification

---

### 🔹 Weekly Analytics (Bar Chart)
- Built with MPAndroidChart
- Shows usage over last 7 days
- Data:
  - Aggregated per day
  - Converted from ms → hours

---

## Permissions
```xml
<uses-permission android:name="android.permission.PACKAGE_USAGE_STATS"/>
```

User must manually enable usage access in system settings.

---

## 🚀 Running the Project

```bash
git clone https://github.com/1C0DER/TrackNPlay
```

1. Open in Android Studio
2. Connect Firebase project
3. Add `google-services.json`
4. Build & run on device
5. Enable usage access permission

---

## 📌 Notes
- Usage data is processed locally
- Firebase is only used for authentication + user data
- No real-time tracking (aggregated stats only)
