# 📘 React Native `TouchableOpacity` Component Props (বাংলায়)

`TouchableOpacity` হলো একটি টাচেবল কম্পোনেন্ট যা প্রেস করলে নিজেকে স্বচ্ছ (opacity) করে দেয়। এটি বোতাম বা যেকোনো টাচ ইন্টারঅ্যাকশন এর জন্য ব্যবহৃত হয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name             | টাইপ                           | Default মান | বাংলা ব্যাখ্যা                                                       |
| ---------------------- | ------------------------------ | ----------- | -------------------------------------------------------------------- |
| `activeOpacity`        | `number`                       | `0.2`       | প্রেস করলে opacity কত হবে (0 থেকে 1 এর মধ্যে)। কম মান মানে বেশি ফেড। |
| `onPress`              | `function`                     | —           | প্রেস করার সময় কল হয়।                                                |
| `onPressIn`            | `function`                     | —           | টাচ শুরু হলে কল হয় (টাচ ডাউন)।                                       |
| `onPressOut`           | `function`                     | —           | টাচ ছাড়লে কল হয় (টাচ আপ)।                                           |
| `onLongPress`          | `function`                     | —           | দীর্ঘক্ষণ প্রেস করলে কল হয়।                                          |
| `delayPressIn`         | `number` (মিলিসেকেন্ড)         | `0`         | টাচ শুরু হওয়ার আগে কতক্ষণ অপেক্ষা করবে।                              |
| `delayPressOut`        | `number` (মিলিসেকেন্ড)         | `100`       | টাচ ছাড়ার পরে কতক্ষণ অপেক্ষা করবে।                                  |
| `delayLongPress`       | `number` (মিলিসেকেন্ড)         | `500`       | দীর্ঘ প্রেস কতক্ষণ পর ট্রিগার হবে।                                   |
| `disabled`             | `boolean`                      | `false`     | `true` হলে প্রেস ইভেন্ট বন্ধ থাকবে।                                  |
| `style`                | `ViewStyle` বা `array`         | —           | কম্পোনেন্টের স্টাইল।                                                 |
| `hitSlop`              | `{ top, bottom, left, right }` | —           | প্রেস করার এরিয়া বাড়াতে বা কমাতে।                                    |
| `pressRetentionOffset` | `{ top, bottom, left, right }` | —           | প্রেস শুরু হওয়া এলাকা বাড়ানো/কমানো।                                  |
| `accessible`           | `boolean`                      | `true`      | অ্যাক্সেসিবিলিটি সক্রিয়/বন্ধ।                                        |
| `accessibilityLabel`   | `string`                       | —           | স্ক্রিন রিডার জন্য টেক্সট।                                           |
| `testID`               | `string`                       | —           | টেস্টিং এর জন্য আইডি।                                                |

---

## 🧠 টিপস

- `activeOpacity` কমালে প্রেস করলে বেশি ফেইড efek্ট হবে।
- `onPressIn`, `onPressOut` দিয়ে প্রেসের বিভিন্ন স্টেজ হ্যান্ডল করতে পারবেন।
- `hitSlop` দিয়ে টাচ এরিয়া বড় করা যায়, যা ছোট বাটনের জন্য দরকার হতে পারে।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React from "react";
import { TouchableOpacity, Text, StyleSheet } from "react-native";

const MyButton = () => {
  return (
    <TouchableOpacity
      activeOpacity={0.6}
      onPress={() => alert("টাচ করা হয়েছে!")}
      style={styles.button}
      hitSlop={{ top: 10, bottom: 10, left: 10, right: 10 }}
    >
      <Text style={styles.text}>ট্যাপ করুন</Text>
    </TouchableOpacity>
  );
};

const styles = StyleSheet.create({
  button: {
    backgroundColor: "#1E90FF",
    padding: 15,
    borderRadius: 8,
    alignItems: "center",
  },
  text: {
    color: "white",
    fontWeight: "bold",
  },
});

export default MyButton;
```
