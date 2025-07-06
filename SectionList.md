# 📘 React Native `SectionList` Component Props (বাংলায়)

`SectionList` হলো React Native-এর একটি লিস্ট কম্পোনেন্ট, যা সেকশনভিত্তিক ডেটা দেখাতে ব্যবহৃত হয়। যেমন গ্রুপেড বা ক্যাটাগরাইজড লিস্ট, যেখানে প্রত্যেক সেকশনের জন্য হেডার ও আইটেম আলাদা থাকে।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name                    | টাইপ                                  | Default মান | বাংলা ব্যাখ্যা                                                                          |
| ----------------------------- | ------------------------------------- | ----------- | --------------------------------------------------------------------------------------- |
| `sections`                    | `Array<{title: string, data: Array}>` | —           | সেকশন এবং সেকশনের আইটেমগুলোর ডেটা অ্যারে। প্রত্যেক সেকশনে `title` এবং `data` থাকতে হবে। |
| `renderItem`                  | `function`                            | —           | প্রত্যেক আইটেম কিভাবে রেন্ডার হবে তা নির্ধারণ করে।                                      |
| `renderSectionHeader`         | `function`                            | —           | প্রত্যেক সেকশনের হেডার কিভাবে রেন্ডার হবে তা নির্ধারণ করে।                              |
| `keyExtractor`                | `(item, index) => string`             | —           | প্রতিটি আইটেমের জন্য ইউনিক key প্রদান করে।                                              |
| `ListEmptyComponent`          | `React.Component` বা `function`       | —           | যদি ডেটা না থাকে, তাহলে এটি দেখানো হয়।                                                  |
| `ListHeaderComponent`         | `React.Component` বা `function`       | —           | লিস্টের উপরে একটি কম্পোনেন্ট দেখাতে ব্যবহৃত হয়।                                         |
| `ListFooterComponent`         | `React.Component` বা `function`       | —           | লিস্টের নিচে একটি কম্পোনেন্ট দেখাতে ব্যবহৃত হয়।                                         |
| `stickySectionHeadersEnabled` | `boolean`                             | `true`      | সেকশন হেডার স্ক্রল করে স্ক্রিনের উপরে আটকে থাকবে কিনা।                                  |
| `onEndReached`                | `function`                            | —           | লিস্টের শেষে পৌঁছালে কল হয় (pagination এর জন্য)।                                        |
| `onEndReachedThreshold`       | `number`                              | 0.1         | কতদূর আগেই `onEndReached` কল হবে তা নির্ধারণ করে।                                       |
| `refreshing`                  | `boolean`                             | `false`     | রিফ্রেশ হচ্ছে কিনা, pull-to-refresh এর জন্য।                                            |
| `onRefresh`                   | `function`                            | —           | ইউজার লিস্ট টেনে রিফ্রেশ করলে কল হয়।                                                    |
| `horizontal`                  | `boolean`                             | `false`     | অনুভূমিক লিস্ট দেখাতে হলে `true` দিন।                                                   |
| `extraData`                   | `any`                                 | —           | লিস্টকে রি-রেন্ডার করানোর জন্য অন্য state বা props।                                     |
| `initialNumToRender`          | `number`                              | 10          | প্রথমে কত আইটেম রেন্ডার হবে।                                                            |
| `maxToRenderPerBatch`         | `number`                              | 10          | প্রতি ব্যাচে কত আইটেম রেন্ডার হবে।                                                      |
| `windowSize`                  | `number`                              | 21          | কত আইটেম একসাথে রেন্ডার করবে (স্ক্রিনের চারপাশে)।                                       |

---

## 🧠 টিপস

- `SectionList` ডেটা সেকশন হিসেবে দেখানোর জন্য আদর্শ, যেখানে প্রত্যেক সেকশনের আলাদা হেডার থাকে।
- `stickySectionHeadersEnabled` দিয়ে হেডার আটকে রাখা যায়, যা ইউজার এক্সপেরিয়েন্স ভালো করে।
- পারফরম্যান্স বাড়ানোর জন্য `getItemLayout` প্রপ ব্যবহার করা যেতে পারে, বিশেষ করে বড় লিস্টে।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React from "react";
import { SectionList, Text, View, StyleSheet } from "react-native";

const sections = [
  { title: "ফল", data: ["আপেল", "কলা", "আম"] },
  { title: "সবজি", data: ["টমেটো", "আলু", "গাজর"] },
];

const MySectionList = () => {
  return (
    <SectionList
      sections={sections}
      keyExtractor={(item, index) => item + index}
      renderItem={({ item }) => (
        <View style={styles.item}>
          <Text>{item}</Text>
        </View>
      )}
      renderSectionHeader={({ section: { title } }) => (
        <View style={styles.header}>
          <Text style={styles.headerText}>{title}</Text>
        </View>
      )}
      stickySectionHeadersEnabled={true}
    />
  );
};

const styles = StyleSheet.create({
  header: {
    backgroundColor: "#ddd",
    padding: 8,
  },
  headerText: {
    fontWeight: "bold",
    fontSize: 18,
  },
  item: {
    padding: 10,
    borderBottomWidth: 1,
    borderBottomColor: "#ccc",
  },
});

export default MySectionList;
```
