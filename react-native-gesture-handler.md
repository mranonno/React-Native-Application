````markdown
# ✋ `react-native-gesture-handler` ডকুমেন্টেশন (বাংলায়)

[`react-native-gesture-handler`](https://docs.swmansion.com/react-native-gesture-handler/) হলো React Native এর gesture (touch, swipe, drag, pinch ইত্যাদি) হ্যান্ডল করার জন্য একটি শক্তিশালী লাইব্রেরি। এটি ScrollView, Drawer, Bottom Sheet, Slidable Cards ইত্যাদিতে gesture-based interaction সহজ করে তোলে।

---

## ✅ ইনস্টলেশন

### 👉 Expo ব্যবহারকারীদের জন্য:

```bash
npx expo install react-native-gesture-handler
```
````

### 👉 Bare React Native ব্যবহারকারীদের জন্য:

```bash
npm install react-native-gesture-handler
npx pod-install
```

**🛑 iOS এর জন্য `App.tsx` বা `index.js` এ এই লাইনটা উপরের দিকে রাখতে হয়:**

```js
import "react-native-gesture-handler";
```

---

## ✅ GestureHandlerRootView

Gesture কাজ করার জন্য `App` কে `GestureHandlerRootView` দিয়ে র‍্যাপ করতে হয়:

```tsx
import { GestureHandlerRootView } from "react-native-gesture-handler";

const App = () => (
  <GestureHandlerRootView style={{ flex: 1 }}>
    {/* Your Navigation or App Content */}
  </GestureHandlerRootView>
);
```

---

## ✅ Component Overview

| Component Name            | কাজ                                       |
| ------------------------- | ----------------------------------------- |
| `TapGestureHandler`       | ট্যাপ gesture ধরতে ব্যবহৃত হয়।            |
| `LongPressGestureHandler` | লং-প্রেস gesture ধরতে ব্যবহৃত হয়।         |
| `PanGestureHandler`       | ড্র্যাগ বা প্যান gesture ধরতে ব্যবহৃত হয়। |
| `FlingGestureHandler`     | দ্রুত swipe gesture ধরতে ব্যবহৃত হয়।      |
| `PinchGestureHandler`     | Zoom-in/Zoom-out gesture ধরতে ব্যবহৃত হয়। |
| `RotationGestureHandler`  | Gesture ঘোরানোর জন্য।                     |

---

## ✅ Example: `PanGestureHandler`

```tsx
import { PanGestureHandler } from "react-native-gesture-handler";
import Animated, {
  useSharedValue,
  useAnimatedStyle,
  useAnimatedGestureHandler,
} from "react-native-reanimated";

const DraggableBox = () => {
  const translateX = useSharedValue(0);
  const translateY = useSharedValue(0);

  const gestureHandler = useAnimatedGestureHandler({
    onActive: (event) => {
      translateX.value = event.translationX;
      translateY.value = event.translationY;
    },
  });

  const animatedStyle = useAnimatedStyle(() => ({
    transform: [
      { translateX: translateX.value },
      { translateY: translateY.value },
    ],
  }));

  return (
    <PanGestureHandler onGestureEvent={gestureHandler}>
      <Animated.View
        style={[
          { width: 100, height: 100, backgroundColor: "blue" },
          animatedStyle,
        ]}
      />
    </PanGestureHandler>
  );
};
```

---

## ✅ Common Props (Gesture Handlers)

| Props Name                         | টাইপ       | ব্যাখ্যা                                |
| ---------------------------------- | ---------- | --------------------------------------- |
| `onGestureEvent`                   | `function` | gesture চলাকালীন কল হয়।                 |
| `onHandlerStateChange`             | `function` | gesture এর স্টেট বদলালে কল হয়।          |
| `enabled`                          | `boolean`  | gesture একটিভ হবে কিনা।                 |
| `minPointers`                      | `number`   | gesture শুরু করতে কতটা আঙুল দরকার।      |
| `maxPointers`                      | `number`   | gesture চলাকালীন সর্বোচ্চ কত আঙুল চলবে। |
| `waitFor` / `simultaneousHandlers` | `ref`      | gesture coordination এর জন্য।           |

---

## 🧠 টিপস

- ✅ `react-native-reanimated` এর সাথে ব্যবহার করলে আপনি smooth ও পারফর্ম্যান্ট gesture animation পেতে পারেন।
- ✅ `DrawerNavigator`, `BottomSheet`, `Swipe-to-Delete`, এবং `Pull-to-Refresh` এর জন্য gesture-handler প্রয়োজনীয়।
- ✅ Expo ব্যবহার করলে এটি প্রি-ইনস্টল করা থাকে, তবে still `GestureHandlerRootView` দেওয়া বাধ্যতামূলক।

---

## ⚠️ সতর্কতা

- iOS এ gesture কাজ না করলে: `index.js` এ `import 'react-native-gesture-handler';` উপরের লাইনে আছে কিনা চেক করুন।
- Android এ nested scroll/gesture issue এ `nestedScrollEnabled`, `simultaneousHandlers` ব্যবহার করুন।

---

## 📚 আরও জানতে

- 🔗 [Official Docs](https://docs.swmansion.com/react-native-gesture-handler/)
- 🔗 [Reanimated + GestureHandler Guide](https://docs.swmansion.com/react-native-reanimated/docs/fundamentals/gestures/)

---

আপনি চাইলে আমি আলাদা করে `PanGestureHandler`, `TapGestureHandler`, বা `PinchGestureHandler` এর উপরে বিশদ markdown সহ উদাহরণ দিয়ে দিতে পারি। শুধু বলুন, কে লাগবে 😊

```

```
