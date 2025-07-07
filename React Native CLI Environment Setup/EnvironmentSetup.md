দারুন! তুমি যেহেতু প্রজেক্ট তৈরি করে ফেলেছো, নিচে তোমার জন্য শুধুমাত্র **Environment Setup (Markdown format)** বাংলা ভাষায় সাজিয়ে দিচ্ছি — যেন সহজে সংরক্ষণ করতে পারো।

---

```markdown
# ✅ React Native CLI Environment Setup for Windows (TypeScript Ready)

> 🎯 এই গাইড শুধুমাত্র environment setup এর জন্য। ধরেই নেওয়া হচ্ছে তুমি ইতোমধ্যে React Native CLI প্রজেক্ট তৈরি করেছো।

---

## 🛠️ Step 1: Java JDK 17 ইনস্টল ও সেটআপ

### 🔹 Java ইনস্টল:

- ডাউনলোড লিংক: https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html
- ইনস্টল লোকেশন (সাধারণত):
```

C:\Program Files\Java\jdk-17

````

### 🔹 Environment Variable সেট:
1. `JAVA_HOME` সেট করো:
  - Variable name: `JAVA_HOME`
  - Variable value: `C:\Program Files\Java\jdk-17`

2. `Path` এ `%JAVA_HOME%\bin` যুক্ত করো:
  - System variables → Path → Edit → New:
    ```
    %JAVA_HOME%\bin
    ```

### 🔹 যাচাই:
```bash
java -version
````

✅ যদি version দেখায়, তাহলে Java ঠিকমতো সেট হয়েছে।

---

## 📦 Step 2: Android Studio + SDK + Emulator

### 🔹 Android Studio install করো:

- Download: [https://developer.android.com/studio](https://developer.android.com/studio)

### 🔹 Install এর সময় নিচের টিকগুলো ✅ দাও:

- Android SDK
- Android SDK Command-line Tools
- Android Virtual Device

### 🔹 Emulator তৈরি:

- Android Studio → Tools → AVD Manager → Create Virtual Device

---

## 🔧 Step 3: ANDROID_HOME সেট করো

### 🔹 SDK লোকেশন সাধারণত:

```
C:\Users\<YourUserName>\AppData\Local\Android\Sdk
```

### 🔹 Environment Variables:

1. `ANDROID_HOME` variable:

   - Variable name: `ANDROID_HOME`
   - Variable value: `C:\Users\anonn\AppData\Local\Android\Sdk`

2. `Path` variable এ নিচেরগুলো যোগ করো:

   ```
   %ANDROID_HOME%\platform-tools
   %ANDROID_HOME%\emulator
   %ANDROID_HOME%\tools
   %ANDROID_HOME%\tools\bin
   ```

---

## 🧪 Step 4: যাচাই

### 🔹 ADB যাচাই করো:

```bash
adb --version
```

✅ যদি version দেখায়: ADB ঠিকমতো কাজ করছে।

### 🔹 Emulator চালাও:

```bash
emulator -list-avds
emulator -avd <your_emulator_name>
```

### 🔹 USB ফোন কানেক্ট (বিকল্প):

- Developer mode চালাও → USB Debugging Enable করো
- ফোন কানেক্ট করে চালাও:

```bash
adb devices
```

---

## 🚀 Step 5: অ্যাপ রান করো

```bash
npx react-native run-android
```

✅ সফল হলে “Welcome to React Native” স্ক্রিন দেখাবে।

---

## ✅ Quick Checklist

| 📌 কাজগুলো                | স্ট্যাটাস |
| ------------------------- | --------- |
| Java JDK 17 Installed     | ✅        |
| JAVA_HOME এবং Path সেট    | ✅        |
| Android Studio Installed  | ✅        |
| Android SDK এবং AVD Ready | ✅        |
| ANDROID_HOME এবং Path সেট | ✅        |
| ADB/Emulator Working      | ✅        |
| App run হচ্ছে             | ✅        |

---

> 📝 Tip: পরিবেশ একবার ঠিকভাবে সেট করে ফেললে, পরবর্তী প্রজেক্টে এসব ঝামেলা আর করতে হবে না।

```

---

এই Markdown ফাইল তুমি `environment-setup.md` নামে প্রজেক্ট ফোল্ডারে রেখে দিতে পারো।

চাইলে আমি এটাকে PDF হিসেবেও রেডি করে দিতে পারি। বললেই হয়ে যাবে 💡
🗂️ `Make PDF` → টাইপ করলেই আমি বানিয়ে দেব!
```
