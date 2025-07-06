# 📘 React Native `ActivityIndicator` Component Props (বাংলায়)

`ActivityIndicator` হলো একটি লোডিং স্পিনার বা ঘুরানো আইকন, যা অ্যাপ্লিকেশন লোডিং, ডেটা ফেচিং ইত্যাদি সময় ইউজারকে লোড হচ্ছে বুঝাতে ব্যবহার করা হয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name         | টাইপ                           | Default মান                                          | বাংলা ব্যাখ্যা                                    |
| ------------------ | ------------------------------ | ---------------------------------------------------- | ------------------------------------------------- |
| `animating`        | `boolean`                      | `true`                                               | স্পিনার চলবে কিনা (true হলে চলবে)।                |
| `color`            | `string`                       | প্ল্যাটফর্ম ডিফল্ট (Android: `#1976D2`, iOS: `gray`) | স্পিনারের রং।                                     |
| `size`             | `'small' \| 'large' \| number` | `'small'` (বা platform অনুযায়ী)                      | স্পিনারের আকার, ছোট বা বড় অথবা নির্দিষ্ট পিক্সেল। |
| `hidesWhenStopped` | `boolean` (iOS only)           | `true`                                               | `animating` false হলে স্পিনার লুকাবে কিনা। (iOS)  |

---

## 🧠 টিপস

- `animating` প্রপ দিয়ে স্পিনার চালু/বন্ধ করুন।
- `color` দিয়ে স্পিনারের রং পরিবর্তন করা যায়।
- `size` প্রপ এ `'small'` বা `'large'` দিতে পারেন, অথবা সংখ্যায় পিক্সেল সাইজ দিতে পারেন।
- Android এ `hidesWhenStopped` প্রপ কাজ করে না।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React, { useState, useEffect } from "react";
import { View, ActivityIndicator, StyleSheet, Text } from "react-native";

const LoadingExample = () => {
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    const timer = setTimeout(() => setLoading(false), 3000);
    return () => clearTimeout(timer);
  }, []);

  return (
    <View style={styles.container}>
      {loading ? (
        <ActivityIndicator size="large" color="#1E90FF" animating={loading} />
      ) : (
        <Text>লোডিং সম্পন্ন হয়েছে!</Text>
      )}
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
  },
});

export default LoadingExample;
```
