# 📘 React Native `KeyboardAvoidingView` Component Props (বাংলায়)

`KeyboardAvoidingView` হলো একটি স্পেশাল ভিউ যা কীবোর্ড ওপেন হলে অটোমেটিক UI কে সামঞ্জস্য করে, যাতে ইনপুট ফিল্ড বা অন্যান্য গুরুত্বপূর্ণ এলিমেন্ট কীবোর্ডের নিচে চাপা না পড়ে।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name               | টাইপ                                               | Default মান             | বাংলা ব্যাখ্যা                                                                               |
| ------------------------ | -------------------------------------------------- | ----------------------- | -------------------------------------------------------------------------------------------- |
| `behavior`               | `'height' \| 'position' \| 'padding' \| undefined` | প্ল্যাটফর্ম ডিপেন্ডেন্ট | কীবোর্ড আসলে ভিউ কিভাবে অ্যাডজাস্ট করবে তা নির্ধারণ করে।                                     |
| `keyboardVerticalOffset` | `number`                                           | `0`                     | কীবোর্ডের উপরে ভিউ কতটা উপরে উঠবে (অফসেট)। বিশেষ করে হেডার বা নেভিগেশন বার থাকলে ব্যবহার হয়। |
| `enabled`                | `boolean`                                          | `true`                  | এই ভিউ কীবোর্ড এড়ানোর জন্য কাজ করবে কিনা।                                                   |
| `style`                  | `ViewStyle`                                        | —                       | ভিউর স্টাইল।                                                                                 |
| `contentContainerStyle`  | `ViewStyle`                                        | —                       | ভিউর কন্টেন্টের স্টাইল।                                                                      |

---

## 🧠 Behavior এর ব্যাখ্যা

- **`padding`**: কীবোর্ড ওপেন হলে ভিউর প্যাডিং উপরে বাড়ায় (সাধারণত সবচেয়ে কমপ্যাটিবল)
- **`position`**: ভিউকে পজিশন অনুযায়ী উপরে সরায় (কখনো কখনো সমস্যা হতে পারে)
- **`height`**: ভিউর হাইট কীবোর্ডের উচ্চতার সমান কমায় (কিছু ক্ষেত্রে কাজ করে)

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React, { useState } from "react";
import {
  KeyboardAvoidingView,
  TextInput,
  Button,
  Platform,
  StyleSheet,
  View,
  Text,
} from "react-native";

const MyKeyboardAvoidingView = () => {
  const [text, setText] = useState("");

  return (
    <KeyboardAvoidingView
      behavior={Platform.OS === "ios" ? "padding" : "height"}
      keyboardVerticalOffset={Platform.OS === "ios" ? 60 : 0}
      style={styles.container}
    >
      <View style={styles.inner}>
        <TextInput
          placeholder="কিছু লিখুন..."
          style={styles.textInput}
          value={text}
          onChangeText={setText}
        />
        <Button title="সাবমিট" onPress={() => alert("সাবমিট হয়েছে")} />
      </View>
    </KeyboardAvoidingView>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
  },
  inner: {
    flex: 1,
    justifyContent: "center",
    paddingHorizontal: 24,
  },
  textInput: {
    height: 40,
    borderColor: "gray",
    borderWidth: 1,
    marginBottom: 20,
    paddingHorizontal: 10,
  },
});

export default MyKeyboardAvoidingView;
```
