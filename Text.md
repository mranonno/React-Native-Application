# 📘 React Native `Text` Component Props (বাংলায়)

`Text` কম্পোনেন্ট মূলত টেক্সট দেখানোর জন্য ব্যবহৃত হয় — যেমন শিরোনাম, বর্ণনা, প্যারাগ্রাফ, বা বোতামের লেবেল ইত্যাদি।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name              | টাইপ                                      | Default মান     | বাংলা ব্যাখ্যা                                                                         |
| ----------------------- | ----------------------------------------- | --------------- | -------------------------------------------------------------------------------------- |
| `children`              | `string` বা `ReactNode`                   | —               | `Text` এর ভিতরে যা লেখা হবে। এটি সাধারণত প্লেইন টেক্সট বা `Text` এর ভিতরে অন্য `Text`। |
| `style`                 | `TextStyle`                               | `undefined`     | ফন্ট সাইজ, কালার, ওজন, মার্জিন, প্যাডিং ইত্যাদি দিতে ব্যবহৃত হয়।                       |
| `numberOfLines`         | `number`                                  | `undefined`     | কত লাইনের পর টেক্সট কাটা যাবে তা নির্ধারণ করে (ellipsis `...` দেখায়)।                  |
| `ellipsizeMode`         | `'head'`, `'middle'`, `'tail'`, `'clip'`  | `'tail'`        | টেক্সট কাটার সময় কোন দিকে `...` দেখাবে।                                                |
| `selectable`            | `boolean`                                 | `false`         | ইউজার কি টেক্সট কপি করতে পারবে কিনা।                                                   |
| `onPress`               | `function`                                | —               | টেক্সটে ট্যাপ করলে যা হবে।                                                             |
| `onLongPress`           | `function`                                | —               | টেক্সটে দীর্ঘক্ষণ প্রেস করলে যা হবে।                                                   |
| `adjustsFontSizeToFit`  | `boolean`                                 | `false`         | টেক্সট যদি container-এর বাইরে যায়, তাহলে ছোট ফন্টে ফিট করাবে।                          |
| `minimumFontScale`      | `number`                                  | `undefined`     | ফন্ট সাইজ ছোট হতে পারে এমন সর্বনিম্ন স্কেল মান।                                        |
| `suppressHighlighting`  | `boolean`                                 | `false`         | ট্যাপ করার সময় হাইলাইট বন্ধ রাখে (iOS)।                                                |
| `textBreakStrategy`     | `'simple'`, `'highQuality'`, `'balanced'` | `'highQuality'` | Android-এ লাইনের ব্রেকিং স্ট্র্যাটেজি।                                                 |
| `maxFontSizeMultiplier` | `number`                                  | `undefined`     | accessibility setting অনুযায়ী সর্বোচ্চ ফন্ট স্কেল সীমা নির্ধারণ করে।                   |
| `allowFontScaling`      | `boolean`                                 | `true`          | Accessibility অনুযায়ী ফন্ট স্কেল করবে কিনা।                                            |
| `lineBreakMode`         | `'head'`, `'middle'`, `'tail'`, `'clip'`  | `'tail'` (iOS)  | টেক্সট কাটা যাবে কীভাবে (iOS only)।                                                    |
| `testID`                | `string`                                  | —               | UI testing এ এই `Text` কে টার্গেট করার জন্য।                                           |
| `nativeID`              | `string`                                  | —               | Native code এর সঙ্গে communicate করতে ID।                                              |
| `accessible`            | `boolean`                                 | `true`          | screen reader এর accessibility চালু বা বন্ধ করতে।                                      |
| `accessibilityLabel`    | `string`                                  | —               | visually দেখা যায় না, কেবল screen reader এর জন্য alternate টেক্সট।                     |
| `accessibilityHint`     | `string`                                  | —               | screen reader এর মাধ্যমে টেক্সটের কার্যকারিতা বোঝানোর জন্য।                            |
| `accessibilityRole`     | `'text'`, `'header'`, `'link'` ইত্যাদি    | —               | টেক্সটের ভূমিকা নির্ধারণ করে।                                                          |

---

## 🧠 টিপস

- `numberOfLines` ও `ellipsizeMode` একসাথে ব্যবহার করে UI সুন্দর রাখা যায়।
- যদি টেক্সট কোনো লিংক বা প্রেসেবল হয়, `onPress` ও `suppressHighlighting` দিয়ে কাস্টমাইজ করা যায়।
- ফন্ট responsive রাখতে `adjustsFontSizeToFit` ও `minimumFontScale` খুব দরকারি।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
<Text
  numberOfLines={2}
  ellipsizeMode="tail"
  selectable
  style={{
    fontSize: 18,
    color: "darkblue",
    fontWeight: "bold",
  }}
>
  এই টেক্সটটি দুই লাইনের বেশি হলে কেটে যাবে...
</Text>
```
