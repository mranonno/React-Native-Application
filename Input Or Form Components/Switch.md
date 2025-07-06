# 📘 React Native `Switch` Component Props (বাংলায়)

`Switch` হলো একটি টগল বাটন (ON/OFF) যা ইউজারকে দুটি অবস্থার মধ্যে নির্বাচন করার সুযোগ দেয়। সাধারণত সেটিংস বা অপশন চেঞ্জ করার জন্য ব্যবহৃত হয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name            | টাইপ                                | Default মান                | বাংলা ব্যাখ্যা                                         |
| --------------------- | ----------------------------------- | -------------------------- | ------------------------------------------------------ |
| `value`               | `boolean`                           | —                          | Switch এর বর্তমান অবস্থা (ON হলে true, OFF হলে false)। |
| `onValueChange`       | `(value: boolean) => void`          | —                          | Switch এর অবস্থা পরিবর্তন হলে কলব্যাক।                 |
| `disabled`            | `boolean`                           | `false`                    | true দিলে Switch নিষ্ক্রিয় থাকে এবং টগল করা যায় না।    |
| `trackColor`          | `{ false?: string, true?: string }` | —                          | Switch এর ট্র্যাকের রং (অফ ও অন অবস্থার জন্য আলাদা)।   |
| `thumbColor`          | `string`                            | প্ল্যাটফর্ম অনুযায়ী ডিফল্ট | Switch এর থাম্ব বা বাটনের রং।                          |
| `ios_backgroundColor` | `string`                            | —                          | iOS এ Switch এর ব্যাকগ্রাউন্ড রং (off অবস্থার জন্য)।   |
| `onChange`            | `function`                          | —                          | Switch এর অবস্থা পরিবর্তনের সময় ইভেন্ট।                |
| `onTintColor`         | `string` (deprecated)               | —                          | পুরানো প্রপ, এখন ব্যবহার নয়।                           |

---

## 🧠 টিপস

- `value` ও `onValueChange` ব্যবহার করে Switch কে কন্ট্রোলড কম্পোনেন্ট বানান।
- `trackColor` দিয়ে Switch এর ব্যাকগ্রাউন্ডের ON/OFF রং আলাদা করে দিন।
- iOS এ `ios_backgroundColor` ব্যবহার করে অফ অবস্থার ব্যাকগ্রাউন্ড সেট করতে পারেন।
- `disabled` true করলে Switch প্রেস করা যাবে না।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React, { useState } from "react";
import { View, Switch, Text, StyleSheet } from "react-native";

const MySwitch = () => {
  const [isEnabled, setIsEnabled] = useState(false);

  const toggleSwitch = (value) => {
    setIsEnabled(value);
  };

  return (
    <View style={styles.container}>
      <Text>Switch is {isEnabled ? "ON" : "OFF"}</Text>
      <Switch
        value={isEnabled}
        onValueChange={toggleSwitch}
        trackColor={{ false: "#767577", true: "#81b0ff" }}
        thumbColor={isEnabled ? "#f5dd4b" : "#f4f3f4"}
        ios_backgroundColor="#3e3e3e"
        disabled={false}
      />
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    alignItems: "center",
    justifyContent: "center",
    flex: 1,
  },
});

export default MySwitch;
```
