# 📘 `@react-native-picker/picker` কম্পোনেন্ট Props (বাংলায়)

> `@react-native-picker/picker` হলো React Native-এর অফিসিয়াল কমিউনিটি প্যাকেজ যা পুরাতন `Picker` কম্পোনেন্টের বিকল্প হিসেবে ব্যবহৃত হয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name          | টাইপ                                          | Default মান        | বাংলা ব্যাখ্যা                                     |
| ------------------- | --------------------------------------------- | ------------------ | -------------------------------------------------- |
| `selectedValue`     | `any`                                         | —                  | যেই আইটেম সিলেক্ট করা হয়েছে তার মান।               |
| `onValueChange`     | `(itemValue: any, itemIndex: number) => void` | —                  | আইটেম সিলেক্ট বা পরিবর্তন হলে কলব্যাক।             |
| `enabled`           | `boolean`                                     | `true`             | Picker সক্রিয় বা নিষ্ক্রিয় করার জন্য।              |
| `mode`              | `'dialog' \| 'dropdown' \| 'dropdown'`        | প্ল্যাটফর্ম ডিফল্ট | Picker এর প্রদর্শনের ধরন (Android এ বেশি কার্যকর)। |
| `prompt`            | `string`                                      | —                  | Android এ ডায়ালগের শিরোনাম বা প্রম্পট।             |
| `itemStyle`         | `TextStyle`                                   | —                  | Picker আইটেমের স্টাইল কাস্টমাইজ করার জন্য।         |
| `style`             | `ViewStyle`                                   | —                  | Picker এর মূল কন্টেইনার স্টাইল।                    |
| `dropdownIconColor` | `string`                                      | —                  | Android ড্রপডাউন আইকনের রং নির্ধারণ করে।           |
| `testID`            | `string`                                      | —                  | টেস্টিং এর জন্য আইডি।                              |

---

## 🧠 টিপস

- `selectedValue` এবং `onValueChange` দিয়ে Picker কে কন্ট্রোলড কম্পোনেন্ট বানানো হয়।
- Android এ `mode` প্রপ দিয়ে ডায়ালগ বা ড্রপডাউন হিসেবে Picker দেখানো যায়।
- কাস্টম স্টাইলের জন্য `itemStyle` ও `style` ব্যবহার করুন।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React, { useState } from "react";
import { View, Text, StyleSheet } from "react-native";
import { Picker } from "@react-native-picker/picker";

const MyPicker = () => {
  const [selectedLanguage, setSelectedLanguage] = useState("java");

  return (
    <View style={styles.container}>
      <Text>ভাষা নির্বাচন করুন:</Text>
      <Picker
        selectedValue={selectedLanguage}
        onValueChange={(itemValue, itemIndex) => setSelectedLanguage(itemValue)}
        mode="dropdown"
        style={styles.picker}
      >
        <Picker.Item label="Java" value="java" />
        <Picker.Item label="JavaScript" value="js" />
        <Picker.Item label="Python" value="python" />
      </Picker>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    margin: 20,
  },
  picker: {
    height: 50,
    width: "100%",
  },
});

export default MyPicker;
```
