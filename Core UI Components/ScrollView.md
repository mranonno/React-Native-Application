# 📘 React Native `ScrollView` Component Props (বাংলায়)

`ScrollView` হলো এমন একটি কনটেইনার যা এর ভেতরের উপাদানগুলো স্ক্রল করা যায়। এটি সাধারণত ছোট বা মাঝারি সাইজের কন্টেন্টের জন্য ব্যবহার হয়, যেখানে সব আইটেম একসাথে রেন্ডার করা হয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name                       | টাইপ                                                                | Default মান      | বাংলা ব্যাখ্যা                                                                |
| -------------------------------- | ------------------------------------------------------------------- | ---------------- | ----------------------------------------------------------------------------- |
| `contentContainerStyle`          | `StyleProp<ViewStyle>`                                              | —                | ScrollView এর ভেতরের কন্টেন্টের জন্য স্টাইল। (যেমন প্যাডিং, মার্জিন ইত্যাদি)  |
| `horizontal`                     | `boolean`                                                           | `false`          | true দিলে অনুভূমিক স্ক্রল হয়, না হলে উলম্ব স্ক্রল।                            |
| `showsVerticalScrollIndicator`   | `boolean`                                                           | `true`           | উলম্ব স্ক্রলবার দেখাবে কিনা।                                                  |
| `showsHorizontalScrollIndicator` | `boolean`                                                           | `true`           | অনুভূমিক স্ক্রলবার দেখাবে কিনা।                                               |
| `onScroll`                       | `function`                                                          | —                | স্ক্রল হওয়ার সময় কল হয়, স্ক্রল ইভেন্ট হ্যান্ডল করতে।                          |
| `scrollEventThrottle`            | `number` (মিলিসেকেন্ড)                                              | 16               | কত ফ্রিকোয়েন্সিতে onScroll ইভেন্ট কল হবে। (কম মান হলে বেশি ফ্রিকোয়েন্সি)      |
| `refreshControl`                 | `ReactElement`                                                      | —                | pull-to-refresh ফাংশনালিটি যুক্ত করতে ব্যবহার হয়।                             |
| `pagingEnabled`                  | `boolean`                                                           | `false`          | true দিলে একবারে পুরো পেজ স্ক্রল হয় (Snap Effect)।                            |
| `keyboardShouldPersistTaps`      | `'never'`, `'always'`, `'handled'`                                  | `'never'`        | কীবোর্ড ওপেন থাকলে ট্যাপ করলে কীবোর্ড বন্ধ হবে কীভাবে।                        |
| `scrollEnabled`                  | `boolean`                                                           | `true`           | স্ক্রল চালু বা বন্ধ করতে।                                                     |
| `decelerationRate`               | `'normal'`, `'fast'` অথবা `number`                                  | `'normal'`       | স্ক্রলিংয়ের গতি নিয়ন্ত্রণ করে।                                                |
| `snapToInterval`                 | `number`                                                            | —                | নির্দিষ্ট পয়েন্টে স্ক্রল থামাতে ব্যবহার হয় (carousel এর জন্য)।                |
| `snapToAlignment`                | `'start'`, `'center'`, `'end'`                                      | `'start'`        | স্ক্রল থামার এলাইনমেন্ট কন্ট্রোল করে।                                         |
| `contentOffset`                  | `{ x: number, y: number }`                                          | `{ x: 0, y: 0 }` | লোড হওয়ার সময় স্ক্রল কোথায় থাকবে।                                             |
| `keyboardDismissMode`            | `'none'`, `'interactive'`, `'on-drag'`                              | `'none'`         | স্ক্রল করলে কীবোর্ড কীভাবে ডিসমিস হবে।                                        |
| `nestedScrollEnabled`            | `boolean`                                                           | `false`          | Android এ nested scroll সক্ষম করতে।                                           |
| `maintainVisibleContentPosition` | `{ minIndexForVisible: number, autoscrollToTopThreshold?: number }` | —                | নতুন কন্টেন্ট যোগ হলে বর্তমান ভিউ বজায় রাখতে সাহায্য করে (যেমন চ্যাট অ্যাপে)। |

---

## 🧠 টিপস

- বড় ডেটার লিস্ট হলে `ScrollView` না দিয়ে `FlatList` বা `SectionList` ব্যবহার করুন, কারণ `ScrollView` সব আইটেম একসাথে রেন্ডার করে যা পারফরম্যান্স সমস্যা হতে পারে।
- pull-to-refresh ফিচারের জন্য `refreshControl` প্রপ ব্যবহার করতে পারেন।
- `pagingEnabled` দিয়ে পেজের মতো স্ক্রলিং করতে পারেন।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React from "react";
import { ScrollView, Text, StyleSheet } from "react-native";

const MyScrollView = () => {
  return (
    <ScrollView
      contentContainerStyle={styles.contentContainer}
      showsVerticalScrollIndicator={false}
      keyboardShouldPersistTaps="handled"
      keyboardDismissMode="on-drag"
    >
      {[...Array(20)].map((_, i) => (
        <Text key={i} style={styles.item}>
          আইটেম {i + 1}
        </Text>
      ))}
    </ScrollView>
  );
};

const styles = StyleSheet.create({
  contentContainer: {
    padding: 20,
  },
  item: {
    fontSize: 18,
    marginVertical: 10,
  },
});

export default MyScrollView;
```
