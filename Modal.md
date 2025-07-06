# 📘 React Native `Modal` Component Props (বাংলায়)

`Modal` হলো একটি পপ-আপ উইন্ডো বা ডায়ালগ বক্স যা মূল ভিউয়ের উপরে অস্থায়ীভাবে প্রদর্শিত হয়। এটি ডায়ালগ, এলার্ট, বা অন্য কোনো ভিন্ন স্ক্রীন ইফেক্টের জন্য ব্যবহৃত হয়।

---

## ✅ গুরুত্বপূর্ণ Props তালিকা

| Props Name              | টাইপ                                                             | Default মান    | বাংলা ব্যাখ্যা                                                       |
| ----------------------- | ---------------------------------------------------------------- | -------------- | -------------------------------------------------------------------- |
| `visible`               | `boolean`                                                        | `false`        | মডালটি দেখানো হবে কিনা। true দিলে মডাল দেখাবে।                       |
| `animationType`         | `'none' \| 'slide' \| 'fade'`                                    | `'none'`       | মডাল প্রদর্শনের সময় অ্যানিমেশন টাইপ।                                 |
| `transparent`           | `boolean`                                                        | `false`        | true হলে মডাল ব্যাকগ্রাউন্ড স্বচ্ছ হয়, false হলে সাদা ব্যাকগ্রাউন্ড। |
| `onRequestClose`        | `function`                                                       | —              | Android-এ ব্যাক বাটন প্রেস করলে কল হয়। (মডাল বন্ধ করার জন্য)         |
| `hardwareAccelerated`   | `boolean`                                                        | `false`        | Android-এ হার্ডওয়্যার এক্সিলারেশন চালু করবে।                         |
| `presentationStyle`     | `'fullScreen' \| 'pageSheet' \| 'formSheet' \| 'overFullScreen'` | `'fullScreen'` | iOS এ মডাল প্রদর্শনের ধরন।                                           |
| `supportedOrientations` | `Array<string>`                                                  | —              | মডাল কোন কোন স্ক্রীন অরিয়েন্টেশনে সাপোর্ট করবে।                      |
| `onShow`                | `function`                                                       | —              | মডাল প্রদর্শিত হওয়ার পর কল হয়।                                       |
| `statusBarTranslucent`  | `boolean`                                                        | `false`        | Android এ স্ট্যাটাস বার ট্রান্সলুসেন্ট হবে কিনা।                     |

---

## 🧠 টিপস

- `visible` প্রপ দিয়ে মডাল দেখানো বা লুকানো নিয়ন্ত্রণ করুন।
- `animationType` দিয়ে সুন্দর অ্যানিমেশন যুক্ত করতে পারেন।
- `transparent` true করলে ব্যাকগ্রাউন্ডে মূল ভিউ দেখা যাবে।
- Android এ `onRequestClose` বাধ্যতামূলক, কারণ হার্ডওয়্যার ব্যাক বাটন প্রেস করার জন্য প্রয়োজন।

---

## 📦 সাধারণ ব্যবহারের উদাহরণ

```jsx
import React, { useState } from "react";
import { Modal, View, Text, Button, StyleSheet } from "react-native";

const MyModal = () => {
  const [modalVisible, setModalVisible] = useState(false);

  return (
    <View style={styles.container}>
      <Button title="মডাল খুলুন" onPress={() => setModalVisible(true)} />

      <Modal
        visible={modalVisible}
        animationType="slide"
        transparent={true}
        onRequestClose={() => setModalVisible(false)}
      >
        <View style={styles.modalBackground}>
          <View style={styles.modalContainer}>
            <Text style={styles.modalText}>এটি একটি মডাল উইন্ডো।</Text>
            <Button title="বন্ধ করুন" onPress={() => setModalVisible(false)} />
          </View>
        </View>
      </Modal>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
  },
  modalBackground: {
    flex: 1,
    backgroundColor: "rgba(0,0,0,0.5)",
    justifyContent: "center",
    alignItems: "center",
  },
  modalContainer: {
    width: 300,
    backgroundColor: "white",
    padding: 20,
    borderRadius: 8,
    elevation: 5,
  },
  modalText: {
    marginBottom: 15,
    fontSize: 18,
    textAlign: "center",
  },
});

export default MyModal;
```
