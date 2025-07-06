# 📘 React Native `SafeAreaView` Component Props (বাংলায়)

`SafeAreaView` হলো একটি ভিউ যা iOS ডিভাইসের নট, স্ট্যাটাস বার, হোম ইন্ডিকেটর ইত্যাদি এলাকা বাদ দিয়ে কন্টেন্ট প্রদর্শন করে, যাতে UI কোনো গুরুত্বপূর্ণ অংশ কেটে না যায়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name | টাইপ                                                                      | Default মান                       | বাংলা ব্যাখ্যা                                                |
| ---------- | ------------------------------------------------------------------------- | --------------------------------- | ------------------------------------------------------------- |
| `style`    | `ViewStyle`                                                               | —                                 | কম্পোনেন্টের স্টাইল।                                          |
| `edges`    | `Array<'top' \| 'bottom' \| 'left' \| 'right'>` (React Native 0.50+ থেকে) | সব দিক (top, bottom, left, right) | কোন দিকগুলো safe area হিসাবে বিবেচনা করা হবে তা নির্ধারণ করে। |

---

## 🧠 টিপস

- iOS 11+ ডিভাইসের জন্য Safe Area automatically কন্টেন্টকে নিরাপদ জায়গায় রাখে।
- Android এ সাধারণত SafeAreaView ডিফল্টভাবে কাজ করে না, তবে অনেক কেসে StatusBar, notch area-র জন্য সাহায্য করে।
- `edges` দিয়ে আপনি স্পেসিফিক দিকগুলো বেছে নিতে পারেন।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React from "react";
import { SafeAreaView, View, Text, StyleSheet } from "react-native";

const MySafeAreaView = () => {
  return (
    <SafeAreaView style={styles.container} edges={["top", "left", "right"]}>
      <View style={styles.content}>
        <Text>সেফ এরিয়া ভিউ ব্যবহার করা হয়েছে।</Text>
      </View>
    </SafeAreaView>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "#f5f5f5",
  },
  content: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
  },
});

export default MySafeAreaView;
```
