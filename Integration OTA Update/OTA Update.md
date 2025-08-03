একদম ঠিক! নিচে তোমার জন্য **Expo OTA Update Integration Guide** টা পুরোপুরি **Markdown** ফরম্যাটে সাজিয়ে দিলাম — future reference বা documentation হিসেবে সরাসরি কপি করে রাখতে পারো ✅

---

````markdown
# ✅ Expo OTA Update Integration Guide (React Native Expo)

A complete step-by-step guide to integrate Over-The-Air (OTA) updates using `expo-updates`.

---

## 🔹 Step 1: Install Required Dependency

Make sure you have `expo-updates` installed in `package.json`:

```json
"expo-updates": "~0.28.17"
```
````

Install if missing:

```bash
npx expo install expo-updates
```

---

## 🔹 Step 2: Configure `app.json`

```json
{
  "expo": {
    "updates": {
      "enabled": true,
      "checkAutomatically": "ON_LOAD",
      "fallbackToCacheTimeout": 0,
      "url": "https://u.expo.dev/YOUR_PROJECT_ID"
    },
    "extra": {
      "eas": {
        "projectId": "YOUR_PROJECT_ID"
      }
    },
    "runtimeVersion": {
      "policy": "appVersion"
    }
  }
}
```

Replace `YOUR_PROJECT_ID` with your real project ID. You can get it using:

```bash
npx expo config --type public
```

---

## 🔹 Step 3: Create OTA Logic Utility

📁 `utils/checkForUpdates.ts`

```ts
import * as Updates from "expo-updates";

export type OTAUpdateStatus = "updated" | "uptodate" | "failed";

export const checkForOTAUpdate = async (): Promise<{
  status: OTAUpdateStatus;
  error?: string;
}> => {
  try {
    const update = await Updates.checkForUpdateAsync();
    if (update.isAvailable) {
      await Updates.fetchUpdateAsync();
      await Updates.reloadAsync();
      return { status: "updated" };
    } else {
      return { status: "uptodate" };
    }
  } catch (error: unknown) {
    const errorMessage =
      error instanceof Error ? error.message : "Something went wrong";
    return { status: "failed", error: errorMessage };
  }
};
```

---

## 🔹 Step 4: Use Logic in a Screen

📁 `screens/CheckUpdateScreen.tsx`

```tsx
import React, { useEffect, useState, useCallback } from "react";
import { View, Text, StyleSheet, ActivityIndicator } from "react-native";
import Toast from "react-native-toast-message";
import { useNavigation } from "@react-navigation/native";
import { checkForOTAUpdate } from "../utils/checkForUpdates";

const CheckUpdateScreen = () => {
  const navigation = useNavigation();
  const [loading, setLoading] = useState(true);
  const [statusMessage, setStatusMessage] = useState("");

  const showToast = useCallback(
    (type, title, message = "", duration = 2000) => {
      Toast.show({
        type,
        text1: title,
        text2: message,
        visibilityTime: duration,
      });
    },
    []
  );

  const handleUpdateCheck = useCallback(async () => {
    const { status, error } = await checkForOTAUpdate();

    switch (status) {
      case "updated":
        showToast("success", "Update Downloaded", "Restarting app...");
        break;
      case "uptodate":
        showToast("success", "You're up-to-date!");
        setTimeout(() => navigation.goBack(), 1500);
        break;
      case "failed":
        showToast("error", "Update check failed", error);
        setTimeout(() => navigation.goBack(), 2000);
        break;
    }

    setLoading(false);
  }, [navigation, showToast]);

  useEffect(() => {
    handleUpdateCheck();
  }, [handleUpdateCheck]);

  return (
    <View style={styles.container}>
      {loading ? (
        <>
          <ActivityIndicator size="large" />
          <Text style={styles.message}>Checking for updates...</Text>
        </>
      ) : (
        <Text style={styles.message}>{statusMessage}</Text>
      )}
    </View>
  );
};

export default CheckUpdateScreen;

const styles = StyleSheet.create({
  container: { flex: 1, justifyContent: "center", alignItems: "center" },
  message: { marginTop: 10, fontSize: 16, textAlign: "center" },
});
```

---

## 🔹 Step 5: Setup `eas.json`

📁 `eas.json`

```json
{
  "cli": {
    "version": ">= 16.7.0",
    "appVersionSource": "remote"
  },
  "build": {
    "preview": {
      "distribution": "internal",
      "channel": "preview",
      "android": {
        "buildType": "apk"
      }
    },
    "production": {
      "autoIncrement": true,
      "channel": "production"
    }
  },
  "submit": {
    "production": {}
  }
}
```

✅ Make sure `channel` is set for each profile. OTA depends on this.

---

## 🔹 Step 6: Build the App with OTA Channel

Preview build:

```bash
eas build --profile preview --platform android
```

Production build:

```bash
eas build --profile production --platform android
```

---

## 🔹 Step 7: Publish OTA Updates

Preview branch:

```bash
eas update --branch preview --message "Fixes & improvements"
```

Production branch:

```bash
eas update --branch production --message "Final release"
```

---

## 🧪 Bonus Tips

- ✅ You can add update check logic directly in your root component if needed.
- ✅ For large updates, use progress bars or modals before `Updates.reloadAsync()`.
- ✅ You can disable auto-restart and ask for user confirmation before reloading.

---

## ✅ Summary Table

| File/Component             | Role                                                  |
| -------------------------- | ----------------------------------------------------- |
| `package.json`             | Ensure `expo-updates` installed                       |
| `app.json`                 | OTA config (`updates`, `runtimeVersion`, `projectId`) |
| `eas.json`                 | Define `channel` for OTA builds                       |
| `utils/checkForUpdates.ts` | OTA update logic                                      |
| `CheckUpdateScreen.tsx`    | Screen to handle and show update result               |
| `eas build` command        | Build with proper `profile` & `channel`               |
| `eas update` command       | Publish OTA to the correct branch                     |

---

Happy Shipping! 🚀

```

```
