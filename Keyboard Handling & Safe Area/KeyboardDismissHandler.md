````markdown
# 📘 KeyboardDismissHandler (Custom Wrapper/Logic) React Native-এ

`KeyboardDismissHandler` হলো একটি কাস্টম কম্পোনেন্ট বা লজিক যা ইউজারের স্ক্রীনে কোথাও ট্যাপ করলে কীবোর্ড অটোমেটিকভাবে লুকিয়ে দেয়। React Native এ ডিফল্ট কোনো কম্পোনেন্ট নেই যা এটা করে, তাই সাধারণত `TouchableWithoutFeedback` বা `Pressable` এর সাহায্যে বানানো হয়।

---

## ✅ সাধারণ Props (যদি Wrapper হিসেবে তৈরি করেন)

| Props Name  | টাইপ       | বাংলা ব্যাখ্যা                                              |
| ----------- | ---------- | ----------------------------------------------------------- |
| `children`  | React Node | ভিতরের UI এলিমেন্ট যা কীবোর্ড ডিসমিস এলাকা হিসেবে কাজ করবে। |
| `onDismiss` | Function   | কীবোর্ড ডিসমিস হওয়ার সময় কলব্যাক। (ঐচ্ছিক)                  |
| `style`     | ViewStyle  | বাইরের ভিউয়ের স্টাইল। (ঐচ্ছিক)                              |

---

## 🧠 কাস্টম KeyboardDismissHandler তৈরি করার উদাহরণ

```jsx
import React from "react";
import {
  Keyboard,
  TouchableWithoutFeedback,
  View,
  StyleSheet,
} from "react-native";

const KeyboardDismissHandler = ({ children, onDismiss, style }) => {
  const dismissKeyboard = () => {
    Keyboard.dismiss();
    if (onDismiss) {
      onDismiss();
    }
  };

  return (
    <TouchableWithoutFeedback onPress={dismissKeyboard} accessible={false}>
      <View style={[styles.container, style]}>{children}</View>
    </TouchableWithoutFeedback>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
  },
});

export default KeyboardDismissHandler;
```
````

---

## 📦 ব্যবহার উদাহরণ

```jsx
import React, { useState } from "react";
import { TextInput, Text, StyleSheet } from "react-native";
import KeyboardDismissHandler from "./KeyboardDismissHandler";

const ExampleScreen = () => {
  const [text, setText] = useState("");

  return (
    <KeyboardDismissHandler>
      <TextInput
        style={styles.input}
        placeholder="কিছু লিখুন"
        value={text}
        onChangeText={setText}
      />
      <Text>আপনি লিখেছেন: {text}</Text>
    </KeyboardDismissHandler>
  );
};

const styles = StyleSheet.create({
  input: {
    height: 40,
    borderColor: "gray",
    borderWidth: 1,
    margin: 20,
    paddingHorizontal: 10,
  },
});

export default ExampleScreen;
```

---

## 📝 টিপস

- `TouchableWithoutFeedback` এর `accessible={false}` দেয়া জরুরি যাতে এটি অ্যাক্সেসিবিলিটিতে সমস্যা না করে।
- `Keyboard.dismiss()` কল করার মাধ্যমে কীবোর্ড লুকানো হয়।
- এই Wrapper দিয়ে যেকোনো স্ক্রীনে সহজেই কীবোর্ড ডিসমিস লজিক প্রয়োগ করা যায়।

---

আরো কাস্টম কম্পোনেন্ট বা React Native বিষয় Markdown এ চান? বলুন, তৈরী করে দিবো! 😊

```

```
