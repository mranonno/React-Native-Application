অবশ্যই, নিচে আমি আবারো সম্পূর্ণ **`Stack.Navigator`** ডকুমেন্টেশনটা **Markdown ফরম্যাটে**, **Tips সহ** দিয়ে দিলাম যাতে আপনি কপি-পেস্ট করে রেফারেন্স হিসেবে রাখতে পারেন। 😊

---

````markdown
# 📘 React Navigation: `Stack.Navigator` ডকুমেন্টেশন (বাংলায়)

`Stack.Navigator` হলো React Navigation লাইব্রেরির Stack-based navigator, যা স্ক্রিনগুলোকে Stack আকারে ম্যানেজ করে। এটি ব্রাউজারের "পিছনে যাওয়া"-র মত কাজ করে: আপনি এক স্ক্রিন থেকে আরেকটিতে যাওয়ার পর পূর্বের স্ক্রিন ব্যাক করে ফিরে পেতে পারেন।

---

## ✅ সাধারণ ব্যবহার

```js
import { createStackNavigator } from "@react-navigation/stack";

const Stack = createStackNavigator();

<Stack.Navigator initialRouteName="Home" screenOptions={{ headerShown: false }}>
  <Stack.Screen name="Home" component={HomeScreen} />
  <Stack.Screen name="Profile" component={ProfileScreen} />
</Stack.Navigator>;
```
````

---

## ✅ `Stack.Navigator` এর Props

| Props Name         | টাইপ                                  | বাংলা ব্যাখ্যা                                  |
| ------------------ | ------------------------------------- | ----------------------------------------------- |
| `initialRouteName` | `string`                              | প্রথম কোন স্ক্রিন দেখাবে তা নির্ধারণ করে।       |
| `screenOptions`    | `object` অথবা `({ route }) => object` | সকল স্ক্রিনের জন্য ডিফল্ট অপশন নির্ধারণ করে।    |
| `id`               | `string`                              | একই অ্যাপে একাধিক Stack থাকলে আলাদা ID দিতে হয়। |

---

## ✅ `screenOptions` এর ভিতরের অপশনসমূহ

| অপশন Name                 | টাইপ                                      | বাংলা ব্যাখ্যা                                      |
| ------------------------- | ----------------------------------------- | --------------------------------------------------- |
| `headerShown`             | `boolean`                                 | হেডার দেখাবে কিনা।                                  |
| `title`                   | `string`                                  | স্ক্রিনের হেডারে প্রদর্শিত টাইটেল।                  |
| `gestureEnabled`          | `boolean`                                 | gesture দিয়ে স্ক্রিন ব্যাক যাবে কিনা।               |
| `animationEnabled`        | `boolean`                                 | স্ক্রিন পরিবর্তনের সময় অ্যানিমেশন হবে কিনা।         |
| `presentation`            | `'card' \| 'modal' \| 'transparentModal'` | স্ক্রিন কীভাবে দেখাবে (iOS modal effect ইত্যাদি)।   |
| `cardStyle`               | `object`                                  | প্রতিটি স্ক্রিনের ব্যাকগ্রাউন্ড ও স্টাইল নির্ধারণে। |
| `animationTypeForReplace` | `'push' \| 'pop'`                         | স্ক্রিন রিপ্লেস করার সময় কেমন অ্যানিমেশন হবে।       |

---

## ✅ `Stack.Screen` Props

| Props Name  | টাইপ                                | বাংলা ব্যাখ্যা                   |
| ----------- | ----------------------------------- | -------------------------------- |
| `name`      | `string`                            | স্ক্রিনের ইউনিক নাম।             |
| `component` | React Component                     | যেই কম্পোনেন্ট রেন্ডার হবে।      |
| `options`   | `object` বা `({ route }) => object` | নির্দিষ্ট স্ক্রিনের কাস্টম অপশন। |

---

## 📦 সম্পূর্ণ উদাহরণ

```js
import React from "react";
import { createStackNavigator } from "@react-navigation/stack";
import HomeScreen from "./screens/HomeScreen";
import DetailsScreen from "./screens/DetailsScreen";

const Stack = createStackNavigator();

const MyStack = () => {
  return (
    <Stack.Navigator
      initialRouteName="Home"
      screenOptions={{
        headerStyle: { backgroundColor: "#6200ee" },
        headerTintColor: "#fff",
        headerTitleStyle: { fontWeight: "bold" },
        gestureEnabled: true,
      }}
    >
      <Stack.Screen
        name="Home"
        component={HomeScreen}
        options={{ title: "হোম স্ক্রিন" }}
      />
      <Stack.Screen
        name="Details"
        component={DetailsScreen}
        options={{ title: "ডিটেইলস স্ক্রিন" }}
      />
    </Stack.Navigator>
  );
};

export default MyStack;
```

---

## 🧠 টিপস

- ✅ শুধু প্রথম স্ক্রিন দেখাতে `initialRouteName` ব্যবহার করুন।
- ✅ সকল স্ক্রিনের হেডার ডিজেবল করতে `screenOptions={{ headerShown: false }}` দিন।
- ✅ gesture ব্যাক বা অ্যানিমেশন কন্ট্রোল করতে `gestureEnabled` এবং `animationEnabled` ব্যবহার করুন।
- ✅ প্রতিটি স্ক্রিনের আলাদা title, header style, অথবা option দরকার হলে `options={{ ... }}` দিন `Stack.Screen` এ।

---

## ✅ Extra Tip (Screen থেকে অন্য স্ক্রিনে যাওয়ার নিয়ম):

```js
navigation.navigate("Details"); // Stack.Screen name দিয়ে
```

---

আপনি চাইলে `Tab.Navigator`, `Drawer.Navigator`, কিংবা `BottomTab.Navigator` এর জন্যও এভাবে Markdown ফরম্যাটে ডকুমেন্টেশন বানিয়ে দিতে পারি। জানাতে ভুলবেন না!

```

```
