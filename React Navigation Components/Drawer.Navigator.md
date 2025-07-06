````markdown
# 📘 React Navigation: `Drawer.Navigator` ডকুমেন্টেশন (বাংলায়)

`Drawer.Navigator` হলো React Navigation এর Drawer Navigation কম্পোনেন্ট, যা সাইড থেকে স্লাইড করে আসা মেনু দ্বারা স্ক্রিন নেভিগেট করতে সাহায্য করে। সাধারণত বাম বা ডান পাশ থেকে Drawer খুলে বিভিন্ন স্ক্রিনে যাওয়া যায়।

---

## ✅ সাধারণ ব্যবহার

```js
import { createDrawerNavigator } from "@react-navigation/drawer";

const Drawer = createDrawerNavigator();

<Drawer.Navigator>
  <Drawer.Screen name="Home" component={HomeScreen} />
  <Drawer.Screen name="Profile" component={ProfileScreen} />
</Drawer.Navigator>;
```
````

---

## ✅ `Drawer.Navigator` Props

| Props Name         | টাইপ                                                | বাংলা ব্যাখ্যা                             |
| ------------------ | --------------------------------------------------- | ------------------------------------------ |
| `initialRouteName` | `string`                                            | প্রথম কোন স্ক্রিন দেখাবে তা নির্ধারণ করে।  |
| `screenOptions`    | `object` বা `({ route }) => object`                 | সব স্ক্রিনের জন্য ডিফল্ট অপশন সেট করে।     |
| `drawerContent`    | `({ navigation, state }) => JSX`                    | কাস্টম Drawer UI দেখাতে ব্যবহৃত হয়।        |
| `drawerType`       | `'front'` \| `'back'` \| `'slide'` \| `'permanent'` | Drawer এর animation টাইপ নির্ধারণ করে।     |
| `drawerPosition`   | `'left'` \| `'right'`                               | Drawer বাম না ডান পাশ থেকে খুলবে।          |
| `edgeWidth`        | `number`                                            | কতদূরে স্ক্রিন থেকে টেনে Drawer খুলবে।     |
| `hideStatusBar`    | `boolean`                                           | Drawer খোলা অবস্থায় StatusBar লুকাবে কিনা। |

---

## ✅ `screenOptions` এর গুরুত্বপূর্ণ অপশনসমূহ

| অপশন Name         | টাইপ                                | বাংলা ব্যাখ্যা                        |
| ----------------- | ----------------------------------- | ------------------------------------- |
| `headerShown`     | `boolean`                           | হেডার দেখাবে কিনা।                    |
| `drawerLabel`     | `string` \| `({ focused }) => JSX`  | Drawer এ টাইটেল কী হবে।               |
| `drawerIcon`      | `({ focused, size, color }) => JSX` | Drawer আইকন নির্ধারণ করে।             |
| `drawerItemStyle` | `object`                            | Drawer আইটেম স্টাইল কাস্টমাইজ করতে।   |
| `swipeEnabled`    | `boolean`                           | টেনে Drawer খুলবে কিনা।               |
| `gestureEnabled`  | `boolean`                           | gesture দিয়ে স্ক্রিন ব্যাক যাবে কিনা। |

---

## ✅ `Drawer.Screen` Props

| Props Name  | টাইপ            | বাংলা ব্যাখ্যা                                        |
| ----------- | --------------- | ----------------------------------------------------- |
| `name`      | `string`        | স্ক্রিনের নাম (navigate করার জন্য দরকার)।             |
| `component` | React Component | যেই স্ক্রিন কম্পোনেন্ট রেন্ডার হবে।                   |
| `options`   | `object`        | নির্দিষ্ট স্ক্রিনের drawer/হেডার অপশন কাস্টমাইজ করতে। |

---

## 📦 উদাহরণ সহ ব্যবহার

```js
import React from "react";
import { createDrawerNavigator } from "@react-navigation/drawer";
import { Ionicons } from "@expo/vector-icons";
import HomeScreen from "./screens/HomeScreen";
import ProfileScreen from "./screens/ProfileScreen";

const Drawer = createDrawerNavigator();

const MyDrawer = () => {
  return (
    <Drawer.Navigator
      initialRouteName="Home"
      screenOptions={({ route }) => ({
        headerShown: true,
        drawerActiveTintColor: "#6200ee",
        drawerInactiveTintColor: "gray",
        drawerLabelStyle: { fontSize: 16 },
        drawerIcon: ({ focused, color, size }) => {
          const iconName = route.name === "Home" ? "home" : "person";
          return <Ionicons name={iconName} size={size} color={color} />;
        },
      })}
    >
      <Drawer.Screen name="Home" component={HomeScreen} />
      <Drawer.Screen name="Profile" component={ProfileScreen} />
    </Drawer.Navigator>
  );
};

export default MyDrawer;
```

---

## 🧠 টিপস

- ✅ Drawer কাস্টমাইজ করতে `drawerContent` ব্যবহার করুন যেখানে আপনি আপনার নিজস্ব UI দিতে পারেন।
- ✅ Drawer এর animation নিয়ন্ত্রণ করতে `drawerType: 'slide'`, `'front'` ইত্যাদি দিন।
- ✅ Expo ব্যবহার করলে `Ionicons` সহ অন্যান্য আইকন সহজে পাওয়া যায়।
- ✅ ডান পাশে Drawer চাইলে `drawerPosition: 'right'` দিন।

---

## ✅ Drawer খুলতে/বন্ধ করতে Navigation API

```js
navigation.openDrawer(); // Drawer খুলবে
navigation.closeDrawer(); // Drawer বন্ধ হবে
navigation.toggleDrawer(); // টগল করবে (খুলে থাকলে বন্ধ, বন্ধ থাকলে খুলবে)
```

---

আপনি চাইলে Material Top Tabs, Material Bottom Tabs, বা Custom Drawer UI সম্পর্কেও Markdown ডকুমেন্টেশন পেতে পারেন। জানাতে ভুলবেন না! 😊

```

```
