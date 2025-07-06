# 📘 React Native `Alert` API (বাংলায়)

`Alert` হলো React Native এর একটি API যা মোবাইলে পপ-আপ ডায়ালগ তৈরি করতে ব্যবহৃত হয়। সাধারণত ব্যবহার করা হয় ইউজারকে বার্তা দেখানোর জন্য, নিশ্চিতকরণ বা সতর্কবার্তা দেয়ার জন্য।

---

## ✅ গুরুত্বপূর্ণ মেথড ও অপশনসমূহ

### 1. `Alert.alert(title, message?, buttons?, options?, type?)`

| প্যারামিটার | টাইপ                                                                 | বাংলা ব্যাখ্যা                                            |
| ----------- | -------------------------------------------------------------------- | --------------------------------------------------------- |
| `title`     | `string`                                                             | অ্যালার্টের শিরোনাম।                                      |
| `message`   | `string` (ঐচ্ছিক)                                                    | অ্যালার্টে দেখানো বিস্তারিত বার্তা।                       |
| `buttons`   | `Array<{text: string, onPress?: function, style?: string}>` (ঐচ্ছিক) | বাটনের লিস্ট, যেমন OK, Cancel।                            |
| `options`   | `{ cancelable?: boolean, onDismiss?: function }` (ঐচ্ছিক)            | অতিরিক্ত অপশন যেমন ক্যানসেল করা যাবে কি না।               |
| `type`      | `string` (iOS শুধুমাত্র)                                             | অ্যাপলের বিশেষ টাইপ যেমন 'default', 'plain-text' ইত্যাদি। |

---

## ✅ Buttons এর প্রপার্টিজ (বাটন অবজেক্ট)

| প্রপার্টি | টাইপ                                     | বাংলা ব্যাখ্যা                                      |
| --------- | ---------------------------------------- | --------------------------------------------------- |
| `text`    | `string`                                 | বাটনের লেবেল টেক্সট।                                |
| `onPress` | `function`                               | বাটন প্রেস করলে কলব্যাক।                            |
| `style`   | `'default' \| 'cancel' \| 'destructive'` | বাটনের স্টাইল (iOS ও Android এ ভিন্ন ভিন্ন ইফেক্ট)। |

---

## 🧠 টিপস

- `cancelable: true` দিলে ইউজার ডায়ালগের বাইরে ট্যাপ করলে অ্যালার্ট বন্ধ হবে।
- `buttons` এ `style: 'cancel'` থাকা বাটনটি অটোমেটিক বোল্ড বা আলাদা হয়।
- Android এ বাটনের স্টাইল কিছুটা সীমিত।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import { Alert, Button, View } from "react-native";
import React from "react";

const MyAlert = () => {
  const showAlert = () => {
    Alert.alert(
      "সতর্কবার্তা",
      "আপনি কি সত্যিই এই কাজটি করতে চান?",
      [
        {
          text: "না",
          onPress: () => console.log("না চাপা হয়েছে"),
          style: "cancel",
        },
        { text: "হ্যাঁ", onPress: () => console.log("হ্যাঁ চাপা হয়েছে") },
      ],
      { cancelable: false }
    );
  };

  return (
    <View style={{ marginTop: 50 }}>
      <Button title="অ্যালার্ট দেখাও" onPress={showAlert} />
    </View>
  );
};

export default MyAlert;
```
