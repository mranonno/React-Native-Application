# 📘 React Native `CheckBox` Component Props (কমিউনিটি প্যাকেজ থেকে)

> React Native এর নিজস্ব CheckBox কম্পোনেন্ট নেই, তাই সাধারণত [`@react-native-community/checkbox`](https://github.com/react-native-checkbox/react-native-checkbox) প্যাকেজ ব্যবহার করা হয়। নিচে এই কম্পোনেন্টের গুরুত্বপূর্ণ Props গুলো বাংলায় দেওয়া হলো।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name          | টাইপ                                | Default মান | বাংলা ব্যাখ্যা                                                        |
| ------------------- | ----------------------------------- | ----------- | --------------------------------------------------------------------- |
| `value`             | `boolean`                           | —           | চেকবক্সের বর্তমান অবস্থা (true হলে চেকড)।                             |
| `onValueChange`     | `(newValue: boolean) => void`       | —           | চেকবক্সের অবস্থা পরিবর্তন হলে কলব্যাক।                                |
| `disabled`          | `boolean`                           | `false`     | true দিলে চেকবক্স নিষ্ক্রিয় হবে এবং ইউজার ইন্টারঅ্যাকশন বন্ধ থাকবে।   |
| `tintColors`        | `{ true?: string, false?: string }` | —           | চেকবক্সের বর্ডার ও চেক মার্কের রং (true বা false অবস্থার জন্য আলাদা)। |
| `onCheckColor`      | `string`                            | —           | চেক মার্কের রং (Android/iOS পৃথকভাবে কাস্টমাইজ করতে)।                 |
| `onFillColor`       | `string`                            | —           | চেকবক্স চেকড থাকলে এর ব্যাকগ্রাউন্ড কালার।                            |
| `onTintColor`       | `string`                            | —           | চেকবক্স চেকড অবস্থায় বর্ডারের রং।                                     |
| `boxType`           | `string`                            | —           | (iOS) চেকবক্সের আকৃতি (square, circle)।                               |
| `animationDuration` | `number`                            | —           | চেক/আনচেক করার অ্যানিমেশন সময় (মিলিসেকেন্ড)।                          |

---

## 🧠 টিপস

- `value` ও `onValueChange` দিয়ে চেকবক্সকে কন্ট্রোলড কম্পোনেন্ট বানান।
- `tintColors` দিয়ে সহজেই ON/OFF অবস্থার রং আলাদা করা যায়।
- Android এবং iOS এ কিছু প্রপ আলাদা কাজ করে, তাই প্ল্যাটফর্ম ভিত্তিক কাস্টমাইজেশন দরকার হতে পারে।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React, { useState } from "react";
import { View, Text, StyleSheet } from "react-native";
import CheckBox from "@react-native-community/checkbox";

const MyCheckBox = () => {
  const [isChecked, setIsChecked] = useState(false);

  return (
    <View style={styles.container}>
      <CheckBox
        value={isChecked}
        onValueChange={setIsChecked}
        tintColors={{ true: "#4CAF50", false: "#777" }}
        disabled={false}
      />
      <Text style={styles.label}>{isChecked ? "Checked" : "Unchecked"}</Text>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flexDirection: "row",
    alignItems: "center",
    padding: 10,
  },
  label: {
    marginLeft: 8,
    fontSize: 16,
  },
});

export default MyCheckBox;
```
