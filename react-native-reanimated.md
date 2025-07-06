````markdown
# 🔁 `react-native-reanimated` ডকুমেন্টেশন (বাংলায়)

[`react-native-reanimated`](https://docs.swmansion.com/react-native-reanimated/) হলো React Native-এর জন্য একটি উচ্চ-পারফরম্যান্স অ্যানিমেশন লাইব্রেরি, যা Gesture, Shared Values, Worklets এবং Native Thread-এর মাধ্যমে Smooth এবং Fluid UI তৈরি করতে সাহায্য করে।

---

## ✅ ইনস্টলেশন

### 👉 Expo (Preinstalled in SDK 46+)

```bash
npx expo install react-native-reanimated
```
````

### 👉 Bare React Native:

```bash
npm install react-native-reanimated
npx pod-install
```

📌 **`babel.config.js`** ফাইলে এই প্লাগিনটি যুক্ত করুন:

```js
module.exports = {
  presets: ["babel-preset-expo"],
  plugins: ["react-native-reanimated/plugin"], // সর্বশেষ লাইনে রাখুন
};
```

---

## ✅ প্রধান Feature সমূহ

| Feature                       | ব্যাখ্যা                                                 |
| ----------------------------- | -------------------------------------------------------- |
| `useSharedValue()`            | অ্যানিমেশন বা gesture-এর জন্য শেয়ার করা মান সংরক্ষণ করে। |
| `useAnimatedStyle()`          | স্টাইল অ্যানিমেট করতে ব্যবহৃত হয়।                        |
| `useAnimatedGestureHandler()` | Gesture এর রেসপন্সে মান পরিবর্তন করে।                    |
| `withTiming()`                | টাইমিং ফাংশন দিয়ে অ্যানিমেশন রান করে।                    |
| `withSpring()`                | স্প্রিং ফিজিক্স দিয়ে অ্যানিমেশন করে।                     |
| `withDelay()`                 | নির্দিষ্ট সময় দেরি করে অ্যানিমেশন চালায়।                 |
| `runOnJS()`                   | Worklet থেকে JavaScript ফাংশন কল করতে ব্যবহৃত হয়।        |

---

## ✅ Animated View ব্যবহার

```tsx
import Animated, {
  useSharedValue,
  useAnimatedStyle,
  withSpring,
} from "react-native-reanimated";

const ReanimatedBox = () => {
  const offset = useSharedValue(0);

  const animatedStyle = useAnimatedStyle(() => {
    return {
      transform: [{ translateX: withSpring(offset.value * 100) }],
    };
  });

  return (
    <Animated.View
      style={[
        { width: 100, height: 100, backgroundColor: "blue" },
        animatedStyle,
      ]}
      onTouchStart={() => {
        offset.value = Math.random();
      }}
    />
  );
};
```

---

## ✅ Hooks ও APIs ব্যাখ্যা

### 🔹 `useSharedValue(initialValue)`

একটি reactive variable তৈরি করে যা native thread-এ থাকে।

```js
const opacity = useSharedValue(1);
```

---

### 🔹 `useAnimatedStyle(() => {...})`

Animated View-এর স্টাইল রিটার্ন করে।

```js
const style = useAnimatedStyle(() => ({
  opacity: opacity.value,
}));
```

---

### 🔹 `withTiming(value, config)`

Smooth টাইমিং অ্যানিমেশন।

```js
opacity.value = withTiming(0, { duration: 500 });
```

---

### 🔹 `withSpring(value, config)`

Spring effect দিয়ে bounce/elastic type অ্যানিমেশন।

```js
offset.value = withSpring(100, { damping: 10 });
```

---

### 🔹 `runOnJS(fn)`

Worklet context থেকে JS function কল করার জন্য।

```js
const gestureHandler = useAnimatedGestureHandler({
  onEnd: () => {
    runOnJS(console.log)("Gesture finished");
  },
});
```

---

## ✅ Common Use Cases

| Use Case            | ব্যবহার                    |
| ------------------- | -------------------------- |
| Drawer animation    | Left-right slide           |
| Swipeable list item | Delete/Edit gesture        |
| Bottom sheet slide  | Snap/drag করে ওপরে নিচে    |
| Custom loader       | Progress bar/Spinning ring |
| On-scroll effect    | Scroll করলে হেডার ছোট হয়   |

---

## 🧠 টিপস

- ✅ আপনার animated logic সবসময় worklet context-এ থাকবে (`useAnimatedStyle`, `useAnimatedGestureHandler` ইত্যাদি)।
- ✅ Gesture + Animation একসাথে করতে হলে `react-native-gesture-handler` আবশ্যক।
- ✅ Complex UI performance bottleneck এড়াতে Reanimated use করুন (native thread এ রান হয়)।
- ✅ সঠিকভাবে ইনস্টল না করলে Runtime error দেখাবে। babel config ও reanimated/plugin না দিলে অ্যানিমেশন কাজ করবে না।

---

## 📚 ডকুমেন্টেশন ও রেফারেন্স

- 🔗 [Official Docs](https://docs.swmansion.com/react-native-reanimated/)
- 🔗 [Reanimated Examples (Expo)](https://github.com/software-mansion/react-native-reanimated/tree/main/example)
- 🔗 [Animations Cheat Sheet](https://docs.swmansion.com/react-native-reanimated/docs/fundamentals/animations/)

---

আপনি চাইলে আমি নিচের বিষয়ের markdown ডকুমেন্টেশনও দিতে পারি:

- ✅ `useAnimatedScrollHandler`
- ✅ `withSequence`, `withRepeat`
- ✅ `Layout Animations`
- ✅ `Shared Transitions`
- ✅ Custom Hooks (Ex: `useFadeIn`, `useTranslateY`)

```

```
