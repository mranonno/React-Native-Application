# 📘 React Native `Button` Component Props (বাংলায়)

`Button` হলো React Native-এর একটি সহজ, প্রি-বিল্ট UI বাটন কম্পোনেন্ট। এটি দ্রুত বাটন তৈরি করতে ব্যবহৃত হয়, কিন্তু কাস্টমাইজেশনে সীমাবদ্ধ।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name            | টাইপ       | Default মান        | বাংলা ব্যাখ্যা                                                    |
| --------------------- | ---------- | ------------------ | ----------------------------------------------------------------- |
| `title`               | `string`   | —                  | বাটনে প্রদর্শিত টেক্সট।                                           |
| `onPress`             | `function` | —                  | বাটন প্রেস করার সময় কল হয়।                                        |
| `color`               | `string`   | প্ল্যাটফর্ম ডিফল্ট | বাটনের টেক্সট বা ব্যাকগ্রাউন্ড রঙ (প্ল্যাটফর্ম অনুসারে পরিবর্তন)। |
| `disabled`            | `boolean`  | `false`            | true দিলে বাটন নিষ্ক্রিয় হয় (প্রেস করা যায় না)।                   |
| `accessibilityLabel`  | `string`   | —                  | স্ক্রিন রিডার এর জন্য বাটনের বর্ণনা।                              |
| `testID`              | `string`   | —                  | টেস্টিং এর জন্য বাটনের আইডি।                                      |
| `hasTVPreferredFocus` | `boolean`  | `false`            | TV প্ল্যাটফর্মে ডিফল্ট ফোকাস পেতে।                                |
| `touchSoundDisabled`  | `boolean`  | `false`            | প্রেসের সময় সাউন্ড বন্ধ করতে।                                     |

---

## 🧠 টিপস

- `Button` কাস্টমাইজেশনের জন্য সীমিত; উন্নত ডিজাইনের জন্য `TouchableOpacity` বা `Pressable` ব্যবহার করুন।
- `color` প্রপ দিয়ে প্ল্যাটফর্ম অনুযায়ী বাটনের রং পরিবর্তন করুন।
- iOS-এ `color` টেক্সটের রং পরিবর্তন করে, Android এ বাটনের ব্যাকগ্রাউন্ড রং।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React from "react";
import { View, Button, StyleSheet } from "react-native";

const MyButton = () => {
  const onPressHandler = () => alert("বাটন প্রেস করা হলো!");

  return (
    <View style={styles.container}>
      <Button title="ক্লিক করুন" onPress={onPressHandler} color="#1E90FF" />
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    margin: 20,
  },
});

export default MyButton;
```
