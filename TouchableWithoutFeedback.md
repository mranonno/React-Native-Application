# 📘 React Native `TouchableWithoutFeedback` Component Props (বাংলায়)

`TouchableWithoutFeedback` হলো একটি টাচেবল কম্পোনেন্ট যা প্রেস করলে কোনো ভিজুয়াল ফিডব্যাক (যেমন opacity বা ripple) দেয় না। এটি সাধারণত অন্য ভিউর উপর প্রেস হ্যান্ডল করতে বা কীবোর্ড বন্ধ করার জন্য ব্যবহার করা হয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name           | টাইপ                   | Default মান | বাংলা ব্যাখ্যা                     |
| -------------------- | ---------------------- | ----------- | ---------------------------------- |
| `onPress`            | `function`             | —           | প্রেস করার সময় কল হয়।              |
| `onPressIn`          | `function`             | —           | টাচ শুরু হলে কল হয়।                |
| `onPressOut`         | `function`             | —           | টাচ ছাড়লে কল হয়।                  |
| `onLongPress`        | `function`             | —           | দীর্ঘ প্রেস হলে কল হয়।             |
| `delayPressIn`       | `number` (মিলিসেকেন্ড) | `0`         | প্রেস শুরু হওয়ার আগে অপেক্ষার সময়। |
| `delayPressOut`      | `number` (মিলিসেকেন্ড) | `100`       | প্রেস শেষ হওয়ার পরে অপেক্ষার সময়।  |
| `delayLongPress`     | `number` (মিলিসেকেন্ড) | `500`       | দীর্ঘ প্রেস কতক্ষণ পর ট্রিগার হবে। |
| `disabled`           | `boolean`              | `false`     | প্রেস ইভেন্ট বন্ধ করতে।            |
| `accessible`         | `boolean`              | `true`      | অ্যাক্সেসিবিলিটি সক্রিয়/বন্ধ।      |
| `accessibilityLabel` | `string`               | —           | স্ক্রিন রিডারের জন্য টেক্সট।       |
| `testID`             | `string`               | —           | টেস্টিং এর জন্য আইডি।              |

---

## 🧠 টিপস

- `TouchableWithoutFeedback` প্রেস করলে কোনো ভিজুয়াল পরিবর্তন হয় না, তাই UI-তে কোনও পরিবর্তন বা ইফেক্টের প্রয়োজন হলে অন্য Touchable কম্পোনেন্ট ব্যবহার করুন।
- সাধারণত কীবোর্ড বন্ধ করার জন্য স্ক্রীনের অন্য জায়গায় প্রেস হ্যান্ডল করতে ব্যবহার হয়।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ (কীবোর্ড বন্ধ করার জন্য)

```jsx
import React from "react";
import {
  Keyboard,
  TouchableWithoutFeedback,
  View,
  TextInput,
  StyleSheet,
} from "react-native";

const DismissKeyboardExample = () => {
  return (
    <TouchableWithoutFeedback onPress={Keyboard.dismiss}>
      <View style={styles.container}>
        <TextInput style={styles.input} placeholder="এখানে লিখুন" />
      </View>
    </TouchableWithoutFeedback>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    padding: 20,
  },
  input: {
    borderWidth: 1,
    borderColor: "#999",
    padding: 10,
    borderRadius: 5,
  },
});

export default DismissKeyboardExample;
```
