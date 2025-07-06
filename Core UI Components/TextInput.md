# 📘 React Native `TextInput` Component Props (বাংলায়)

`TextInput` হলো React Native-এ ইউজার ইনপুট নেওয়ার জন্য ব্যবহৃত একটি মৌলিক কম্পোনেন্ট। সাধারণত ফর্ম, লগইন, সার্চ বার, কমেন্ট বক্স ইত্যাদিতে এটি ব্যবহৃত হয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name              | টাইপ                                                | Default মান                                    | বাংলা ব্যাখ্যা                                                         |
| ----------------------- | --------------------------------------------------- | ---------------------------------------------- | ---------------------------------------------------------------------- |
| `value`                 | `string`                                            | `''`                                           | ইনপুট ফিল্ডে যেটা লেখা থাকবে, সেটাই এই প্রপের মাধ্যমে কন্ট্রোল করা হয়। |
| `onChangeText`          | `function`                                          | —                                              | ইউজার কিছু টাইপ করলেই এই ফাংশন কল হয়।                                  |
| `placeholder`           | `string`                                            | —                                              | ইনপুট খালি থাকলে এখানে যা দিবেন তা হালকা রঙে দেখায়।                    |
| `secureTextEntry`       | `boolean`                                           | `false`                                        | পাসওয়ার্ড ইনপুটের জন্য ব্যবহার হয়, ইনপুট হাইড করে দেয়।                 |
| `keyboardType`          | `string`                                            | `'default'`                                    | ইনপুট অনুযায়ী কীবোর্ড টাইপ দেখায় (numeric, email-address ইত্যাদি)।     |
| `multiline`             | `boolean`                                           | `false`                                        | একাধিক লাইনের ইনপুট নিতে চাইলে `true` দিন।                             |
| `numberOfLines`         | `number`                                            | `1`                                            | multiline ইনপুট হলে কত লাইনে টেক্সট দেখা যাবে তা নির্ধারণ করে।         |
| `editable`              | `boolean`                                           | `true`                                         | ইনপুট ফিল্ড সম্পাদনযোগ্য কিনা তা নিয়ন্ত্রণ করে।                        |
| `maxLength`             | `number`                                            | —                                              | ইনপুটে সর্বোচ্চ কত ক্যারেক্টার টাইপ করা যাবে।                          |
| `autoFocus`             | `boolean`                                           | `false`                                        | স্ক্রিন ওপেন হওয়ামাত্র ইনপুটে কার্সর/ফোকাস চলে আসবে।                   |
| `autoCapitalize`        | `'none'`, `'sentences'`, `'words'`, `'characters'`  | `'none'`                                       | স্বয়ংক্রিয়ভাবে অক্ষর ক্যাপিটালাইজ করার নিয়ম নির্ধারণ করে।              |
| `autoCorrect`           | `boolean`                                           | `true`                                         | বানান ঠিক করার জন্য অটো কারেকশন চালু থাকবে কিনা।                       |
| `returnKeyType`         | `string`                                            | `'done'`, `'go'`, `'next'`, `'search'` ইত্যাদি | কীবোর্ডের return বাটনের টেক্সট কী হবে।                                 |
| `onSubmitEditing`       | `function`                                          | —                                              | ইউজার return বাটন চাপলে এই ফাংশন কল হয়।                                |
| `onFocus`               | `function`                                          | —                                              | ইনপুটে ফোকাস দিলে কল হয়।                                               |
| `onBlur`                | `function`                                          | —                                              | ইনপুট থেকে ফোকাস হারালে কল হয়।                                         |
| `selectionColor`        | `string`                                            | —                                              | ইনপুট টেক্সট সিলেক্ট করলে হাইলাইটের কালার কী হবে।                      |
| `caretHidden`           | `boolean`                                           | `false`                                        | ইনপুট কার্সর দেখাবে না।                                                |
| `contextMenuHidden`     | `boolean`                                           | `false`                                        | লং প্রেসে copy/paste অপশন হাইড করতে চাইলে।                             |
| `selection`             | `{ start: number, end: number }`                    | —                                              | প্রোগ্রামেটিকভাবে কোন টেক্সট অংশ সিলেক্ট করা হবে তা নির্ধারণ করে।      |
| `defaultValue`          | `string`                                            | —                                              | কন্ট্রোলড না হলে শুরুর ভ্যালু।                                         |
| `textAlign`             | `'left'`, `'center'`, `'right'`                     | `'left'`                                       | ইনপুটের লেখা কোন দিকে থাকবে।                                           |
| `underlineColorAndroid` | `string`                                            | `#757575`                                      | Android-এ TextInput এর নিচের লাইন এর রঙ।                               |
| `blurOnSubmit`          | `boolean`                                           | `true`                                         | সাবমিট করার পর ইনপুট থেকে ফোকাস সরে যাবে কিনা।                         |
| `importantForAutofill`  | `'auto'`, `'yes'`, `'no'`, `'noExcludeDescendants'` | `'auto'`                                       | Android autofill behavior কনফিগার করতে।                                |
| `secureTextEntry`       | `boolean`                                           | `false`                                        | পাসওয়ার্ড ইনপুটের ক্ষেত্রে লেখাগুলো হাইড করে দেয়।                      |

---

## 🧠 টিপস

- `value` ও `onChangeText` একসাথে ব্যবহার করে `controlled component` বানানো হয়।
- `secureTextEntry` = `true` → পাসওয়ার্ড ইনপুট।
- ফর্ম ফিল্ডে `returnKeyType` ও `onSubmitEditing` দিয়ে “Next”/“Submit” নেভিগেশন হ্যান্ডেল করা যায়।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
<TextInput
  placeholder="আপনার নাম লিখুন"
  value={name}
  onChangeText={setName}
  style={{
    borderWidth: 1,
    borderColor: "gray",
    padding: 10,
    marginVertical: 10,
  }}
/>
```
