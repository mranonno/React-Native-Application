# 📘 React Native `TouchableHighlight` Component Props (বাংলায়)

`TouchableHighlight` হলো একটি টাচেবল কম্পোনেন্ট, যা প্রেস করলে ভিজুয়াল ফিডব্যাক হিসেবে ব্যাকগ্রাউন্ড রং পরিবর্তন করে। এটি মূলত প্রেস ইফেক্টের জন্য ব্যবহার হয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name             | টাইপ                           | Default মান | বাংলা ব্যাখ্যা                                           |
| ---------------------- | ------------------------------ | ----------- | -------------------------------------------------------- |
| `activeOpacity`        | `number`                       | `0.85`      | প্রেস করলে কনটেন্টের opacity কত হবে (0 থেকে 1 এর মধ্যে)। |
| `underlayColor`        | `string`                       | —           | প্রেসের সময় ব্যাকগ্রাউন্ডে যে রং দেখাবে।                 |
| `onPress`              | `function`                     | —           | প্রেস করার সময় কল হয়।                                    |
| `onPressIn`            | `function`                     | —           | টাচ শুরু হলে কল হয়।                                      |
| `onPressOut`           | `function`                     | —           | টাচ ছাড়লে কল হয়।                                        |
| `onLongPress`          | `function`                     | —           | দীর্ঘক্ষণ প্রেস করলে কল হয়।                              |
| `delayPressIn`         | `number` (মিলিসেকেন্ড)         | `0`         | প্রেস শুরু হওয়ার আগে অপেক্ষার সময়।                       |
| `delayPressOut`        | `number` (মিলিসেকেন্ড)         | `100`       | প্রেস শেষ হওয়ার পরে অপেক্ষার সময়।                        |
| `delayLongPress`       | `number` (মিলিসেকেন্ড)         | `500`       | দীর্ঘ প্রেস কতক্ষণ পর ট্রিগার হবে।                       |
| `disabled`             | `boolean`                      | `false`     | প্রেস ইভেন্ট বন্ধ করতে।                                  |
| `style`                | `ViewStyle` বা `array`         | —           | কম্পোনেন্টের স্টাইল।                                     |
| `hitSlop`              | `{ top, bottom, left, right }` | —           | প্রেস করার এরিয়া বাড়াতে বা কমাতে।                        |
| `pressRetentionOffset` | `{ top, bottom, left, right }` | —           | প্রেস শুরু হওয়া এলাকা বাড়ানো/কমানো।                      |
| `accessible`           | `boolean`                      | `true`      | অ্যাক্সেসিবিলিটি সক্রিয়/বন্ধ।                            |
| `accessibilityLabel`   | `string`                       | —           | স্ক্রিন রিডারের জন্য টেক্সট।                             |
| `testID`               | `string`                       | —           | টেস্টিং এর জন্য আইডি।                                    |

---

## 🧠 টিপস

- `underlayColor` দিয়ে প্রেসের সময় ব্যাকগ্রাউন্ড রং পরিবর্তন করা হয়, যা প্রেস ফিডব্যাক হিসেবে ব্যবহার হয়।
- `activeOpacity` দিয়ে প্রেসের সময় opacity নিয়ন্ত্রণ করা যায়।
- অন্য টাচেবল কম্পোনেন্টের তুলনায় `TouchableHighlight` প্রেস ইফেক্টে বেশি কাস্টমাইজেবল।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React from "react";
import { TouchableHighlight, Text, StyleSheet } from "react-native";

const MyButton = () => {
  return (
    <TouchableHighlight
      underlayColor="#DDDDDD"
      activeOpacity={0.6}
      onPress={() => alert("Button Pressed!")}
      style={styles.button}
      hitSlop={{ top: 10, bottom: 10, left: 10, right: 10 }}
    >
      <Text style={styles.text}>ট্যাপ করুন</Text>
    </TouchableHighlight>
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
