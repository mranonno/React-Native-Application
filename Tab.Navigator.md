````markdown
# 📘 React Navigation: `Tab.Navigator` ডকুমেন্টেশন (বাংলায়)

`Tab.Navigator` হলো React Navigation এর Bottom Tab Navigation সিস্টেম, যা সাধারণত অ্যাপের নিচে ট্যাব আকারে বিভিন্ন স্ক্রিনে যেতে ব্যবহৃত হয় (যেমন: Home, Profile, Settings ইত্যাদি)।

---

## ✅ সাধারণ ব্যবহার

```js
import { createBottomTabNavigator } from "@react-navigation/bottom-tabs";

const Tab = createBottomTabNavigator();

<Tab.Navigator>
  <Tab.Screen name="Home" component={HomeScreen} />
  <Tab.Screen name="Settings" component={SettingsScreen} />
</Tab.Navigator>;
```
````

---

## ✅ `Tab.Navigator` Props

| Props Name         | টাইপ                                         | বাংলা ব্যাখ্যা                                            |
| ------------------ | -------------------------------------------- | --------------------------------------------------------- |
| `initialRouteName` | `string`                                     | কোন স্ক্রিন প্রথমে দেখাবে তা নির্ধারণ করে।                |
| `screenOptions`    | `object` অথবা `({ route }) => object`        | সব স্ক্রিনের জন্য ডিফল্ট অপশন নির্ধারণ করে।               |
| `tabBarOptions` 🔴 | (deprecated, use `screenOptions.tabBar`)     | পুরানো API (v5 এ ছিল) — এখন `screenOptions` ব্যবহার করুন। |
| `backBehavior`     | `'initialRoute'` \| `'order'` \| `'history'` | ব্যাক বাটন প্রেস করলে কোন স্ক্রিনে যাবে তা নিয়ন্ত্রণ করে। |

---

## ✅ `screenOptions` এর সাধারণ অপশনসমূহ

| অপশন                      | টাইপ                                 | বাংলা ব্যাখ্যা                              |
| ------------------------- | ------------------------------------ | ------------------------------------------- |
| `tabBarLabel`             | `string` অথবা `({ focused }) => JSX` | ট্যাবের নিচে দেখানো টেক্সট।                 |
| `tabBarIcon`              | `({ focused, color, size }) => JSX`  | ট্যাব আইকন (Ionicons, FontAwesome ইত্যাদি)। |
| `tabBarActiveTintColor`   | `string`                             | অ্যাকটিভ ট্যাবের রঙ।                        |
| `tabBarInactiveTintColor` | `string`                             | ইনঅ্যাকটিভ ট্যাবের রঙ।                      |
| `tabBarStyle`             | `object`                             | ট্যাব বারের স্টাইল।                         |
| `headerShown`             | `boolean`                            | হেডার দেখাবে কিনা।                          |

---

## ✅ `Tab.Screen` Props

| Props Name  | টাইপ            | বাংলা ব্যাখ্যা                                       |
| ----------- | --------------- | ---------------------------------------------------- |
| `name`      | `string`        | স্ক্রিনের নাম (navigate করার জন্য দরকার)।            |
| `component` | React Component | যেই স্ক্রিন কম্পোনেন্ট রেন্ডার হবে।                  |
| `options`   | `object`        | নির্দিষ্ট স্ক্রিনের জন্য ট্যাব/হেডার কাস্টমাইজ করতে। |

---

## 📦 উদাহরণ সহ ব্যবহার

```js
import React from "react";
import { createBottomTabNavigator } from "@react-navigation/bottom-tabs";
import { Ionicons } from "@expo/vector-icons";
import HomeScreen from "./screens/HomeScreen";
import SettingsScreen from "./screens/SettingsScreen";

const Tab = createBottomTabNavigator();

const MyTabs = () => {
  return (
    <Tab.Navigator
      initialRouteName="Home"
      screenOptions={({ route }) => ({
        tabBarIcon: ({ focused, color, size }) => {
          let iconName = route.name === "Home" ? "home" : "settings";
          return <Ionicons name={iconName} size={size} color={color} />;
        },
        tabBarActiveTintColor: "#6200ee",
        tabBarInactiveTintColor: "gray",
        headerShown: false,
      })}
    >
      <Tab.Screen name="Home" component={HomeScreen} />
      <Tab.Screen name="Settings" component={SettingsScreen} />
    </Tab.Navigator>
  );
};

export default MyTabs;
```

---

## 🧠 টিপস

- `tabBarIcon` ব্যবহার করলে স্ক্রিনের জন্য আলাদা আইকন দেখাতে পারবেন।
- `tabBarStyle` দিয়ে ব্যাকগ্রাউন্ড কালার, হাইট, বর্ডার ইত্যাদি কাস্টমাইজ করা যায়।
- যদি `headerShown: false` না দেন, তাহলে প্রতিটি স্ক্রিনের উপর হেডার দেখাবে।
- Expo ব্যবহার করলে `@expo/vector-icons` থেকে আইকন নিতে পারেন, নয়তো `react-native-vector-icons` ইন্সটল করতে হবে।

---

## ✅ ব্যাক বাটন Behavior

| Value          | Behavior                                                       |
| -------------- | -------------------------------------------------------------- |
| `initialRoute` | সবসময় initial route-এ ফিরে যাবে।                               |
| `order`        | স্ক্রিন ডিক্লারেশনের ক্রম অনুসারে ফিরে যাবে।                   |
| `history`      | ইউজার যেভাবে স্ক্রিন পরিবর্তন করেছে, সেই হিস্টোরি অনুসরণ করবে। |

---

আপনি চাইলে Drawer.Navigator বা Material Top Tabs এর ডকুমেন্টেশনও Markdown ফরম্যাটে পেতে পারেন! শুধু বলুন কোনটা লাগবে 😊

```

```
