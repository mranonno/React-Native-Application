# 📘 React Native `View` Component Props (বাংলায়)

`View` হল React Native-এর সবচেয়ে মৌলিক কম্পোনেন্ট, যেটা একটি কনটেইনার হিসেবে কাজ করে। এর ভেতরে আপনি অন্যান্য UI কম্পোনেন্ট রাখতে পারেন এবং CSS-এর মত style প্রপস দিয়ে এটি সাজাতে পারেন।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name                       | টাইপ                                                   | Default মান | বাংলা ব্যাখ্যা                                                                            |
| -------------------------------- | ------------------------------------------------------ | ----------- | ----------------------------------------------------------------------------------------- |
| `style`                          | `ViewStyle` / `array`                                  | `undefined` | CSS-এর মত করে `View` কে সাজানোর জন্য ব্যবহৃত হয় (flex, backgroundColor, padding ইত্যাদি)। |
| `children`                       | `ReactNode`                                            | —           | `View` এর ভিতরে যা রেন্ডার করতে চান তা এখানে দেন (Text, Button, Image ইত্যাদি)।           |
| `onLayout`                       | `function`                                             | —           | `View` যখন রেন্ডার হয়ে যায়, তখন তার dimension (width, height, x, y) জানতে এই ফাংশন কল হয়। |
| `accessible`                     | `boolean`                                              | `true`      | এটি true হলে screen reader দ্বারা এই view access করা যাবে।                                |
| `accessibilityLabel`             | `string`                                               | —           | screen reader-এর জন্য alternative label, যা visually দেখা যায় না।                         |
| `accessibilityHint`              | `string`                                               | —           | screen reader কীভাবে কাজ করবে সেই context দেয়।                                            |
| `accessibilityRole`              | `"button"`, `"header"` ইত্যাদি                         | —           | এটি জানায়, view-এর ভূমিকা কী (বাটন, হেডার ইত্যাদি)।                                       |
| `pointerEvents`                  | `'auto'`, `'none'`, `'box-only'`, `'box-none'`         | `'auto'`    | View কিভাবে touch ইভেন্ট নেবে তা নির্ধারণ করে।                                            |
| `importantForAccessibility`      | `'auto'`, `'yes'`, `'no'`, `'no-hide-descendants'`     | `'auto'`    | এই ভিউটি অ্যাক্সেসিবল হবে কিনা তা কনফিগার করে।                                            |
| `testID`                         | `string`                                               | —           | টেস্টিং করার সময় view-কে identify করতে ব্যবহৃত হয়।                                        |
| `nativeID`                       | `string`                                               | —           | Native কোডের সঙ্গে যোগাযোগ করার জন্য ID।                                                  |
| `hitSlop`                        | `object` (top, bottom, left, right)                    | —           | View-এর স্পর্শযোগ্য এলাকা বড় করার জন্য ব্যবহৃত হয়।                                        |
| `removeClippedSubviews`          | `boolean`                                              | `false`     | যেসব সাবভিউ স্ক্রিনের বাইরে থাকে, সেগুলো অপটিমাইজ করার জন্য রিমুভ করে।                    |
| `collapsable`                    | `boolean`                                              | `true`      | View যদি কোনো কারণে নেস্টেড না হয়, তাহলে সেটি রেন্ডার না করতেও পারে।                      |
| `renderToHardwareTextureAndroid` | `boolean`                                              | `false`     | Android এ পারফরম্যান্স বাড়াতে এই prop ব্যবহার হয়।                                         |
| `needsOffscreenAlphaCompositing` | `boolean`                                              | `false`     | যদি opacity ব্যবহার করেন, তবে এটি true দিলে পারফরম্যান্স ভালো হয় (Android)।               |
| `shouldRasterizeIOS`             | `boolean`                                              | `false`     | iOS এ পারফরম্যান্স ইম্প্রুভ করতে র্যাস্টারাইজ করতে ব্যবহার হয়।                            |
| `accessibilityState`             | `object` (disabled, selected, checked, busy, expanded) | —           | অ্যাক্সেসিবিলিটির জন্য ভিউ-এর বর্তমান অবস্থা বোঝাতে ব্যবহৃত হয়।                           |
| `accessibilityLiveRegion`        | `'none'`, `'polite'`, `'assertive'`                    | `'none'`    | Android screen reader-এ কিভাবে আপডেট শোনাবে।                                              |
| `accessibilityElementsHidden`    | `boolean`                                              | `false`     | view ও তার children screen reader থেকে হাইড করতে।                                         |
| `focusable`                      | `boolean`                                              | —           | ইউজার কীবোর্ড বা screen reader দিয়ে focus করতে পারবে কিনা।                                |
| `styleDirection`                 | `'ltr'` বা `'rtl'`                                     | `'ltr'`     | ডিরেকশন: Left-to-Right (ltr) বা Right-to-Left (rtl)।                                      |
| `transform`                      | `array` of transforms                                  | —           | স্কেল, ঘুরানো, ঘর সরানো ইত্যাদি করার জন্য।                                                |

---

## 💡 টিপস

- ✅ `style` হলো সবচেয়ে গুরুত্বপূর্ণ prop, কারণ এটিই layout ও UI সাজায়।
- ✅ `onLayout` ব্যবহার করে আপনি height/width dynamically measure করতে পারেন।
- ✅ `pointerEvents`, `hitSlop` – gesture control এর জন্য খুব কাজের।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
<View
  style={{ padding: 20, backgroundColor: "lightblue" }}
  onLayout={(event) => {
    console.log(event.nativeEvent.layout);
  }}
>
  <Text>Hello View</Text>
</View>
```
