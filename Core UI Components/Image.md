# 📘 React Native `Image` Component Props (বাংলায়)

`Image` কম্পোনেন্ট দিয়ে অ্যাপ্লিকেশনে ছবি (স্থানীয় বা নেটওয়ার্ক থেকে) দেখানো হয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name                    | টাইপ                                       | Default মান | বাংলা ব্যাখ্যা                                            |
| ----------------------------- | ------------------------------------------ | ----------- | --------------------------------------------------------- | ---------- | ---------- | --------- | ------------------------------------------------ |
| `source`                      | `{ uri: string }` বা স্থানীয় ইমেজ অবজেক্ট | —           | ছবি লোড করার উৎস (লোকাল বা ইউআরএল)।                       |
| `resizeMode`                  | `'cover'`                                  | `'contain'` | `'stretch'`                                               | `'repeat'` | `'center'` | `'cover'` | ছবির আকার কিভাবে অ্যাডজাস্ট হবে তা নির্ধারণ করে। |
| `style`                       | `ImageStyle` বা array                      | —           | ছবির স্টাইল (সাইজ, বর্ডার, রাউন্ড ইত্যাদি)।               |
| `onLoad`                      | `function`                                 | —           | ছবি সফলভাবে লোড হলে কল হয়।                                |
| `onError`                     | `function`                                 | —           | ছবি লোডে সমস্যা হলে কল হয়।                                |
| `blurRadius`                  | `number`                                   | 0           | ছবির ব্লার এফেক্টের মাত্রা।                               |
| `defaultSource`               | ImageResource                              | —           | Android এ লোড হওয়ার আগে প্রদর্শিত ছবি। (iOS এ deprecated) |
| `loadingIndicatorSource`      | ImageResource                              | —           | Android এ লোডিং স্পিনার এর জায়গায় প্রদর্শিত ছবি।          |
| `progressiveRenderingEnabled` | `boolean`                                  | false       | Android এ প্রোগ্রেসিভ রেন্ডারিং সক্রিয় করে।               |
| `fadeDuration`                | `number` (মিলিসেকেন্ড)                     | 300         | ছবি ফেইড ইন হওয়ার সময়কাল (Android)।                     |
| `accessible`                  | `boolean`                                  | true        | অ্যাক্সেসিবিলিটি সক্রিয়/বন্ধ।                             |
| `accessibilityLabel`          | `string`                                   | —           | স্ক্রিন রিডার এর জন্য ছবির বর্ণনা।                        |
| `testID`                      | `string`                                   | —           | টেস্টিংয়ের জন্য আইডি।                                     |

---

## 🧠 টিপস

- `resizeMode` এর মান দিয়ে ছবির কভারেজ নিয়ন্ত্রণ করুন; সাধারণত `'cover'` বা `'contain'` ব্যবহৃত হয়।
- নেটওয়ার্ক থেকে ছবি লোড করলে `onLoad` ও `onError` দিয়ে স্টেট ম্যানেজ করুন।
- বড় ছবি ব্লার করতে `blurRadius` ব্যবহার করতে পারেন।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
<Image
  source={{ uri: "https://example.com/image.png" }}
  style={{ width: 200, height: 150, borderRadius: 10 }}
  resizeMode="cover"
/>
```
