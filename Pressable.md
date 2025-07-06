# 📘 React Native `Pressable` Component Props (বাংলায়)

`Pressable` হলো একটি বেসিক টাচ-ইন্টারঅ্যাকটিভ কম্পোনেন্ট, যা প্রেস (ট্যাপ) ইভেন্ট হ্যান্ডল করার জন্য ব্যবহৃত হয়। এটি বিভিন্ন প্রেস স্টেট অনুযায়ী স্টাইল ও আচরণ কাস্টমাইজ করতে দেয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name             | টাইপ                                                                            | Default মান | বাংলা ব্যাখ্যা                                                               |
| ---------------------- | ------------------------------------------------------------------------------- | ----------- | ---------------------------------------------------------------------------- |
| `onPress`              | `function`                                                                      | —           | ইউজার যখন কম্পোনেন্টে ট্যাপ করবে তখন কল হয়।                                  |
| `onPressIn`            | `function`                                                                      | —           | টাচ শুরু হলে কল হয় (টাচ ডাউন মুহূর্তে)।                                      |
| `onPressOut`           | `function`                                                                      | —           | টাচ ছাড়লে কল হয় (টাচ আপ মুহূর্তে)।                                          |
| `onLongPress`          | `function`                                                                      | —           | দীর্ঘক্ষণ প্রেস করলে কল হয়।                                                  |
| `delayLongPress`       | `number` (মিলিসেকেন্ড)                                                          | 500         | কতক্ষণ প্রেস রাখলে `onLongPress` ট্রিগার হবে।                                |
| `pressRetentionOffset` | `{top: number, left: number, right: number, bottom: number}`                    | —           | প্রেস শুরু হওয়ার এরিয়া বর্ধিত বা সংকুচিত করতে ব্যবহৃত।                       |
| `disabled`             | `boolean`                                                                       | `false`     | true দিলে প্রেস ইভেন্ট বন্ধ থাকবে।                                           |
| `android_disableSound` | `boolean`                                                                       | `false`     | Android এ প্রেসের সময় সাউন্ড বন্ধ করে।                                       |
| `android_ripple`       | `{color?: string, borderless?: boolean, radius?: number, foreground?: boolean}` | —           | Android এ ripple effect কাস্টমাইজ করতে ব্যবহৃত।                              |
| `style`                | `ViewStyle` বা `function`                                                       | —           | কম্পোনেন্টের স্টাইল, ফাংশন দিলে প্রেস স্টেট অনুসারে স্টাইল পরিবর্তন করা যায়। |

---

## 🧠 টিপস

- `style` প্রপ হিসেবে ফাংশন দিলে প্রেস স্টেট অনুযায়ী (`pressed`) স্টাইল পরিবর্তন করা যায়:

```jsx
style={({ pressed }) => [
  {
    backgroundColor: pressed ? 'gray' : 'white',
  },
  styles.button,
]}
```
