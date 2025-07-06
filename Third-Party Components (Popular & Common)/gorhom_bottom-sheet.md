````markdown
# 📘 `@gorhom/bottom-sheet` ডকুমেন্টেশন (বাংলায়)

[`@gorhom/bottom-sheet`](https://github.com/gorhom/react-native-bottom-sheet) হলো React Native-এর একটি অত্যন্ত জনপ্রিয় ও শক্তিশালী **Bottom Sheet** লাইব্রেরি, যা gesture এবং animation সহকারে কার্যকরী modal-like UI প্রদান করে।

---

## ✅ বেসিক ব্যবহার

```tsx
import React, { useRef, useMemo } from "react";
import { View, Text } from "react-native";
import BottomSheet from "@gorhom/bottom-sheet";

const MyBottomSheet = () => {
  const sheetRef = useRef<BottomSheet>(null);

  const snapPoints = useMemo(() => ["25%", "50%", "90%"], []);

  return (
    <BottomSheet ref={sheetRef} index={1} snapPoints={snapPoints}>
      <View>
        <Text>এইখানে আপনার কনটেন্ট</Text>
      </View>
    </BottomSheet>
  );
};
```
````

---

## ✅ BottomSheet Props তালিকা (বাংলা ব্যাখ্যা সহ)

| Props Name             | টাইপ                                                  | বাংলা ব্যাখ্যা                                            |
| ---------------------- | ----------------------------------------------------- | --------------------------------------------------------- |
| `index`                | `number`                                              | শুরুর সময় কোন snap point থাকবে (0 = প্রথম snap point)।    |
| `snapPoints`           | `string[]` বা `number[]`                              | Bottom Sheet কতদূর পর্যন্ত উঠবে/নামবে তা নির্ধারণ করে।    |
| `ref`                  | `React.RefObject`                                     | শিট কন্ট্রোল করার জন্য ref প্রয়োজন হয়।                    |
| `enablePanDownToClose` | `boolean`                                             | নিচে টেনে Bottom Sheet বন্ধ করা যাবে কিনা।                |
| `enableOverDrag`       | `boolean`                                             | টানা শেষে অতিরিক্ত টানতে পারবে কিনা।                      |
| `animateOnMount`       | `boolean`                                             | কম্পোনেন্ট লোড হলে Bottom Sheet অ্যানিমেশন সহ খুলবে কিনা। |
| `containerStyle`       | `ViewStyle`                                           | পুরো Bottom Sheet container এর কাস্টম স্টাইল।             |
| `backgroundStyle`      | `ViewStyle`                                           | শীটের ব্যাকগ্রাউন্ড এর স্টাইল।                            |
| `handleStyle`          | `ViewStyle`                                           | শীটের উপরের হ্যান্ডেল এর স্টাইল।                          |
| `handleIndicatorStyle` | `ViewStyle`                                           | হ্যান্ডেল এর ভেতরের ছোট ইন্ডিকেটর বার-এর স্টাইল।          |
| `keyboardBehavior`     | `'interactive' \| 'extend' \| 'fillParent' \| 'none'` | Keyboard ওপেন হলে শীট কিভাবে আচরণ করবে।                   |
| `onChange`             | `(index: number) => void`                             | snap point চেঞ্জ হলে কল হয়।                               |
| `onAnimate`            | `(fromIndex: number, toIndex: number) => void`        | অ্যানিমেশন শুরু হলে কল হয়।                                |
| `detached`             | `boolean`                                             | শীট কি ভিন্নভাবে রেন্ডার হবে কিনা।                        |

---

## ✅ Gesture + ScrollProps

| Props Name                    | টাইপ                              | বাংলা ব্যাখ্যা                                       |
| ----------------------------- | --------------------------------- | ---------------------------------------------------- |
| `enableContentPanningGesture` | `boolean`                         | কনটেন্ট gesture দিয়ে প্যান করতে পারবে কিনা।          |
| `enableHandlePanningGesture`  | `boolean`                         | handle gesture দিয়ে টানা যাবে কিনা।                  |
| `android_keyboardInputMode`   | `'adjustResize'` \| `'adjustPan'` | Android এ কীবোর্ড ওপেন হলে স্ক্রিন কিভাবে আচরণ করবে। |
| `keyboardBlurBehavior`        | `'none'` \| `'restore'`           | কীবোর্ড dismiss হলে শীট restore হবে কিনা।            |
| `enableDismissOnClose`        | `boolean`                         | শীট বন্ধ হলে কম্পোনেন্ট আনমাউন্ট হবে কিনা।           |

---

## ✅ Sheet Ref Methods

| Method Name      | ব্যাখ্যা                             |
| ---------------- | ------------------------------------ |
| `expand()`       | সর্বোচ্চ snap point এ শীট নিয়ে যায়।  |
| `collapse()`     | সর্বনিম্ন snap point এ নিয়ে আসে।     |
| `close()`        | Bottom Sheet সম্পূর্ণভাবে বন্ধ করে।  |
| `snapToIndex(i)` | নির্দিষ্ট index এর snap point এ নেয়। |

```tsx
// উদাহরণ:
sheetRef.current?.snapToIndex(2);
```

---

## 🧠 টিপস

- ✅ Bottom Sheet এর height কন্ট্রোল করতে `snapPoints` ব্যবহার করুন: যেমন `['25%', '50%', '100%']`
- ✅ `enablePanDownToClose={true}` দিলে ইউজার সহজে নিচে টেনে শীট বন্ধ করতে পারে।
- ✅ Input ফোকাস করলে কীবোর্ড-সংক্রান্ত সমস্যা এড়াতে `keyboardBehavior="extend"` ব্যবহার করতে পারেন।
- ✅ Dark mode বা custom theme প্রয়োগ করতে `backgroundStyle`, `handleStyle`, ইত্যাদি customize করুন।

---

## 📦 ইনস্টলেশন

```bash
npm install @gorhom/bottom-sheet react-native-reanimated react-native-gesture-handler
```

👉 `react-native-reanimated` এবং `react-native-gesture-handler` সঠিকভাবে কনফিগার করা থাকতে হবে (especially for Expo bare workflow)।

---

আর BottomSheet-এর advance use cases বা custom ScrollView support চাইলে বললেই দিবো! 😊

```

```
