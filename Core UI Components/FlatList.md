তুমি আগেই FlatList-এর জন্য ডকুমেন্টেশন বানিয়ে দিয়েছো, তবুও এখানে আবার পুরো **FlatList Props ডকুমেন্টেশন (বাংলায়)** দেওয়া হলো সুন্দরভাবে Markdown ফরম্যাটে, যেন এক জায়গায় পাই:

```markdown
# 📋 React Native FlatList Props ডকুমেন্টেশন (বাংলায়)

`FlatList` একটি উচ্চ পারফর্মেন্স সম্পন্ন লিস্ট কম্পোনেন্ট, যেটি React Native-এ বড় ডেটার লিস্ট রেন্ডার করতে ব্যবহৃত হয়।

---

## ✅ মূল Props তালিকা

| Props Name                         | বাংলা ব্যাখ্যা                                                               |
| ---------------------------------- | ---------------------------------------------------------------------------- |
| **data**                           | আপনি যে ডেটাগুলো দেখাতে চান তা একটি অ্যারে হিসেবে পাঠাতে হয়।                 |
| **renderItem**                     | প্রত্যেক আইটেম কিভাবে দেখাবে, সেটি এই ফাংশনের মাধ্যমে নির্ধারণ হয়।           |
| **keyExtractor**                   | প্রত্যেক আইটেমের জন্য ইউনিক key তৈরি করতে ব্যবহৃত হয়।                        |
| **horizontal**                     | এটি `true` দিলে লিস্ট অনুভূমিকভাবে (left-to-right) দেখাবে।                   |
| **inverted**                       | `true` দিলে আইটেমগুলো উল্টো ক্রমে রেন্ডার হবে।                               |
| **initialNumToRender**             | শুরুতে কতগুলো আইটেম রেন্ডার করবে তা নির্ধারণ করে।                            |
| **onEndReached**                   | লিস্টের নিচে পৌঁছালে এটি কল হয়। Pagination বা লোড-মোর ডেটার জন্য ব্যবহৃত হয়। |
| **onEndReachedThreshold**          | কতদূরে থাকলে `onEndReached` কল হবে (0.1 = 10%)।                              |
| **ListHeaderComponent**            | লিস্টের উপরে একটি হেডার কম্পোনেন্ট দেখাতে চাইলে ব্যবহার করা হয়।              |
| **ListFooterComponent**            | লিস্টের নিচে একটি ফুটার কম্পোনেন্ট দেখাতে চাইলে ব্যবহার হয়।                  |
| **ListEmptyComponent**             | যখন `data` খালি থাকে, তখন এই কম্পোনেন্টটি দেখায়।                             |
| **ItemSeparatorComponent**         | আইটেমগুলোর মাঝে একটি বিভাজক (divider) দেখাতে ব্যবহৃত হয়।                     |
| **showsVerticalScrollIndicator**   | স্ক্রল করার সময় স্ক্রলবার দেখাবে কিনা (`true/false`)।                        |
| **showsHorizontalScrollIndicator** | অনুভূমিক স্ক্রলবার দেখাবে কিনা।                                              |
| **contentContainerStyle**          | লিস্টের কন্টেইনার স্টাইল দিতে হলে এটি ব্যবহার করুন।                          |
| **numColumns**                     | একাধিক কলামে (Grid আকারে) আইটেম দেখাতে চাইলে এর মান 2, 3 ইত্যাদি দিন।        |
| **refreshing**                     | pull-to-refresh-এর সময় `true` করে দিলে loading spinner দেখাবে।               |
| **onRefresh**                      | ইউজার যখন লিস্ট টেনে রিফ্রেশ করে, তখন এটি কল হয়।                             |
| **getItemLayout**                  | পারফরম্যান্স বাড়ানোর জন্য প্রতিটি আইটেমের মাপ আগে থেকেই নির্ধারণ করতে দেয়।   |
| **windowSize**                     | স্ক্রিনের চারপাশে কতগুলো আইটেম রেন্ডার হবে, তা নির্ধারণ করে।                 |
| **maxToRenderPerBatch**            | প্রতিবার কতগুলো আইটেম একসাথে রেন্ডার করবে।                                   |
| **updateCellsBatchingPeriod**      | নতুন আইটেম কত সময় পর পর রেন্ডার হবে (ms)।                                    |

---

## ✅ অতিরিক্ত পারফরম্যান্স Props

| Props Name                 | বাংলা ব্যাখ্যা                                                                   |
| -------------------------- | -------------------------------------------------------------------------------- |
| **initialScrollIndex**     | লিস্ট লোড হওয়ার পর কোন ইনডেক্স থেকে স্ক্রল শুরু করবে।                           |
| **viewabilityConfig**      | কোন আইটেম স্ক্রিনে দৃশ্যমান হয়েছে তা নির্ধারণ করতে ব্যবহৃত হয়।                   |
| **onViewableItemsChanged** | দৃশ্যমান আইটেম পরিবর্তনের সময় একটি কলব্যাক ফাংশন চালায়।                         |
| **removeClippedSubviews**  | ভিউ-এর বাইরের অবজেক্টগুলো DOM থেকে সরিয়ে দিয়ে পারফরম্যান্স বাড়ায় (Android only)। |
| **legacyImplementation**   | পুরাতন ScrollView ভিত্তিক ইমপ্লিমেন্টেশন ব্যবহার করতে হলে `true` দিন।            |
| **extraData**              | লিস্টকে forcefully রি-রেন্ডার করাতে ব্যবহৃত হয় যখন অন্য state পরিবর্তিত হয়।      |

---

## ✅ Scroll & Gesture Props

| Props Name                | বাংলা ব্যাখ্যা                                               |
| ------------------------- | ------------------------------------------------------------ |
| **scrollEnabled**         | স্ক্রলিং চালু বা বন্ধ করতে (`true/false`)।                   |
| **pagingEnabled**         | প্রতি পেজে স্ক্রল করে থামানোর জন্য (Snap Effect)।            |
| **snapToInterval**        | নির্দিষ্ট দূরত্বে স্ক্রল থামাতে (Carousel effect এর জন্য)।   |
| **snapToAlignment**       | স্ক্রল থামার পজিশন নির্ধারণ করে (start, center, end)।        |
| **decelerationRate**      | স্ক্রলিং-এর গতি নিয়ন্ত্রণ করে (‘fast’, ‘normal’, বা সংখ্যা)। |
| **scrollEventThrottle**   | কত ফ্রিকোয়েন্সিতে `onScroll` ইভেন্ট কল হবে (ms)।             |
| **onScroll**              | স্ক্রল করার সময় প্রতিবার কল হয় (অ্যানিমেশন ইত্যাদির জন্য)।   |
| **onScrollBeginDrag**     | ইউজার স্ক্রল শুরু করলে কল হয়।                                |
| **onScrollEndDrag**       | স্ক্রল শেষ হলে কল হয়।                                        |
| **onMomentumScrollBegin** | ইনর্শিয়া স্ক্রল শুরু হলে কল হয়।                              |
| **onMomentumScrollEnd**   | ইনর্শিয়া স্ক্রল শেষ হলে কল হয়।                               |

---

## ✅ Keyboard & Focus Props

| Props Name                    | বাংলা ব্যাখ্যা                                                                    |
| ----------------------------- | --------------------------------------------------------------------------------- |
| **keyboardDismissMode**       | স্ক্রল করলে কীবোর্ড dismiss হবে কিনা (‘none’, ‘on-drag’, ‘interactive’)।          |
| **keyboardShouldPersistTaps** | কীবোর্ড থাকলে ইউজার ট্যাপ করলে সেটা বন্ধ হবে কিনা (‘always’, ‘never’, ‘handled’)। |
| **scrollToOverflowEnabled**   | কীবোর্ড ওপেন থাকা অবস্থায় TextInput scroll করবে কিনা।                             |

---

## ✅ iOS & Android Specific Props

| Props Name                         | বাংলা ব্যাখ্যা                                                                         |
| ---------------------------------- | -------------------------------------------------------------------------------------- |
| **bounces**                        | iOS-এ overscroll করলে bounce effect হবে কিনা।                                          |
| **scrollIndicatorInsets**          | iOS-এ স্ক্রল ইন্ডিকেটরের পজিশন কাস্টমাইজ করতে।                                         |
| **nestedScrollEnabled**            | ScrollView-এর ভিতরে `FlatList` থাকলে এটি `true` দিতে হয় (Android)।                     |
| **maintainVisibleContentPosition** | স্ক্রলে কিছু content উপরে বা নিচে visible রাখতে সাহায্য করে (চ্যাট অ্যাপের জন্য ভালো)। |

---

## 🧠 টিপস:

- ✅ Pagination বা infinite scroll করতে চাইলে `onEndReached` + `onEndReachedThreshold` ব্যবহার করুন।
- ✅ Multiple column layout চাইলে `numColumns={2}` ব্যবহার করুন।
- ✅ বড় লিস্টে performance ভালো রাখতে `getItemLayout`, `initialNumToRender`, `windowSize` ব্যবহার করা ভালো।

---

**এই ডকুমেন্টটি কপি করে Markdown ফরম্যাটে VSCode/Obsidian/Notion/Docs এ সংরক্ষণ করে রাখতে পারেন।**  
FlatList-এর বাইরে SectionList, ScrollView, TextInput সহ বাকি component গুলোর ডকুমেন্টেশনও চাইলে দিবো 😊
```
