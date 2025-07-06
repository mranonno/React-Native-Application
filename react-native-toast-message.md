````markdown
# 📘 `react-native-toast-message` ডকুমেন্টেশন (বাংলায়)

[`react-native-toast-message`](https://github.com/calintamas/react-native-toast-message) হলো React Native-এর একটি highly customizable toast notification লাইব্রেরি। এটি ইউজারের জন্য ইনফরমেশন, ওয়ার্নিং, বা এরর দেখাতে ছোট পপ-আপ toast দেখায়।

---

## ✅ 📦 ইনস্টলেশন

```bash
npm install react-native-toast-message
```
````

### ➕ যদি আপনি Expo ব্যবহার করেন:

```bash
npx expo install react-native-toast-message
```

---

## ✅ 🔧 সেটআপ (App.js বা Entry ফাইলে)

```tsx
import React from "react";
import { NavigationContainer } from "@react-navigation/native";
import Toast from "react-native-toast-message";

const App = () => {
  return (
    <NavigationContainer>
      {/* আপনার অন্যান্য নেভিগেশন বা স্ক্রিন */}
      <Toast />
    </NavigationContainer>
  );
};

export default App;
```

---

## ✅ 🔔 Toast দেখানোর নিয়ম

```tsx
import Toast from "react-native-toast-message";

Toast.show({
  type: "success", // 'success' | 'error' | 'info'
  text1: "অভিনন্দন!",
  text2: "আপনার কাজটি সফলভাবে সম্পন্ন হয়েছে 👋",
  position: "top", // top / bottom
  visibilityTime: 3000,
});
```

---

## ✅ Props ব্যাখ্যা

| Props Name       | টাইপ                           | ব্যাখ্যা                               |
| ---------------- | ------------------------------ | -------------------------------------- |
| `type`           | `'success'` `'error'` `'info'` | কোন ধরনের toast হবে।                   |
| `text1`          | `string`                       | বড় লেখাটি। সাধারণত হেডিং।              |
| `text2`          | `string`                       | ছোট সাবটেক্সট।                         |
| `position`       | `'top'` `'bottom'`             | কোথায় toast দেখাবে।                    |
| `visibilityTime` | `number` (ms)                  | কত সময় toast থাকবে।                    |
| `autoHide`       | `boolean`                      | সময় শেষে স্বয়ংক্রিয়ভাবে হাইড হবে কিনা। |
| `topOffset`      | `number`                       | `position: top` হলে কত দূরে থাকবে।     |
| `bottomOffset`   | `number`                       | `position: bottom` হলে কত দূরে থাকবে।  |
| `onShow`         | `function`                     | Toast শো হলে কল হয়।                    |
| `onHide`         | `function`                     | Toast হাইড হলে কল হয়।                  |
| `onPress`        | `function`                     | ইউজার Toast-এ ক্লিক করলে কল হয়।        |

---

## ✅ কাস্টম Toast তৈরি

```tsx
// CustomToast.js
import React from "react";
import { View, Text } from "react-native";

const CustomToast = ({ text1, text2 }) => (
  <View style={{ padding: 15, backgroundColor: "black", borderRadius: 10 }}>
    <Text style={{ color: "white", fontWeight: "bold" }}>{text1}</Text>
    <Text style={{ color: "white" }}>{text2}</Text>
  </View>
);

export default CustomToast;
```

```tsx
// App.js
import Toast, { BaseToast, ErrorToast } from "react-native-toast-message";
import CustomToast from "./components/CustomToast";

<Toast
  config={{
    success: (props) => <CustomToast {...props} />,
    error: (props) => <CustomToast {...props} />,
    info: (props) => <CustomToast {...props} />,
  }}
/>;
```

---

## ✅ কিভাবে dismiss করবেন?

```tsx
Toast.hide();
```

---

## 🧠 টিপস

- ✅ সব স্ক্রিনে কাজ করতে চাইলে Toast `<Toast />` উপরের লেভেলে বসান (যেমন `NavigationContainer` এর নিচে)।
- ✅ আপনি চাইলে Toast কে custom করে আইকন, ব্যাকগ্রাউন্ড কালার, অ্যানিমেশনসহ অনেকভাবে স্টাইল করতে পারেন।
- ✅ Toast ইউজারের Action ফিডব্যাক দেখাতে বা OTP/Submit success/error show করতে দারুণ উপযোগী।

---

## ✅ উদাহরণ

```tsx
<Button
  title="Show Toast"
  onPress={() =>
    Toast.show({
      type: "success",
      text1: "লগইন সফল!",
      text2: "আপনি সফলভাবে লগইন করেছেন।",
    })
  }
/>
```

---

আপনি চাইলে custom animation, toast queueing, অথবা redux এর সাথে ইন্টিগ্রেশন সম্পর্কেও জানতে পারেন। জানালে markdown সহ বুঝিয়ে দিবো! 😊

```

```
