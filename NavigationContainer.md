# 📘 React Native Navigation: `NavigationContainer` Component Props (বাংলায়)

`NavigationContainer` হলো React Navigation লাইব্রেরির মূল কম্পোনেন্ট, যা আপনার অ্যাপের নেভিগেশন স্ট্রাকচারকে র‍্যাপ করে রাখে। এটি নেভিগেশন স্টেট ও থিম ম্যানেজ করে।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name      | টাইপ                                       | Default মান  | বাংলা ব্যাখ্যা                                                                       |
| --------------- | ------------------------------------------ | ------------ | ------------------------------------------------------------------------------------ |
| `children`      | React.ReactNode                            | —            | আপনার নেভিগেশন স্ট্যাক বা নেভিগেটরস (Stack, Tab, Drawer ইত্যাদি) যেগুলো রেন্ডার হবে। |
| `independent`   | `boolean`                                  | `false`      | true দিলে এটি স্বতন্ত্র নেভিগেশন কন্টেইনার হিসেবে কাজ করবে (মাল্টি নেভিগেশন কেসে)।   |
| `onReady`       | `() => void`                               | —            | নেভিগেশন কন্টেইনার রেডি হলে কলব্যাক।                                                 |
| `onStateChange` | `(state) => void`                          | —            | নেভিগেশন স্টেট পরিবর্তিত হলে কল হয় (যেমন স্ক্রিন চেঞ্জ)।                             |
| `theme`         | `DefaultTheme \| DarkTheme \| CustomTheme` | DefaultTheme | নেভিগেশনের জন্য কাস্টম থিম বা ডিফল্ট থিম।                                            |
| `linking`       | `LinkingOptions`                           | —            | Deep linking সেটআপের জন্য।                                                           |
| `fallback`      | `React.ReactNode`                          | —            | নেভিগেশন লোড না হলে বা সময় নিলে দেখানোর স্পিনার বা UI।                               |

---

## 🧠 টিপস

- `NavigationContainer` আপনার অ্যাপের নেভিগেশন হায়ারার্কির মূল রুট। একবার শুধু ব্যবহার করুন।
- থিম কাস্টমাইজ করতে `theme` প্রপ ব্যবহার করুন।
- ডিপ লিংকিং প্রয়োজনে `linking` সেটআপ করুন।
- মাল্টিপল নেভিগেশন কন্টেইনার থাকলে `independent={true}` দিন।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React from "react";
import {
  NavigationContainer,
  DefaultTheme,
  DarkTheme,
} from "@react-navigation/native";
import { createStackNavigator } from "@react-navigation/stack";
import HomeScreen from "./HomeScreen";
import DetailsScreen from "./DetailsScreen";

const Stack = createStackNavigator();

const App = () => {
  return (
    <NavigationContainer
      theme={DefaultTheme}
      onReady={() => console.log("Navigation is ready")}
      onStateChange={(state) => console.log("New navigation state", state)}
    >
      <Stack.Navigator initialRouteName="Home">
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Details" component={DetailsScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
};

export default App;
```
