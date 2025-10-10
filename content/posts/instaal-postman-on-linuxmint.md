---
title: "تثبيت Postman في توزيعة لينكس منت"
date: 2025-10-11
tags: ["Go", "تعلم", "Postman","api"]
description: "في المقالة شرح و تجربة تثبيت برنامج postman على توزيعة لينكس منت  "
images: ["/images/postman.png"]
cover: "/images/postman.png"
pinned: true
---

# شرح تثبيت Postman في توزيعة لينيكس منت
[Postman](https://www.postman.com/) يعد من بين أفضل التطبيقات المساعدة في بناء الواجهات البرمجية (APIs) و إختبارها و سنتطرق في هذا المنشور إلى تجربتي في تثبيته على توزيعة منت دون سناب.

## 1.تحميل البرنامج عبر الطرفية (terminal):
نفذ هذا الكود في الطرفية للحصول على آخر إصدار من بوستمان
```
wget https://dl.pstmn.io/download/latest/linux64 -O postman.tar.gz
```


## 2. فك ضغط الملفات:
دائما عبر الطرفية نقوم بفك ضغط الملف الذي قمنا بتحميله

```
$ sudo tar -xzf postman.tar.gz -C /opt
```

> نفذ الأمر بالصلاحيات العليا كون الملف سيوضع في otp/

## 3. أنشئ رابط رمزي:
```
$ sudo ln -s /opt/Postman/Postman /usr/bin/postman
```

## 4. قم بحذف الملف الذي تم تحميله سابقا
```
$ rm postman.tar.gz
```

##  5. أنشئ إختصارا للبرنامج 
```
$ sudo vim /usr/share/applications/postman.desktop
```

>إستعمل محرر النصوص vim أو أي برنامج تفضله من أجل كتابة الكود التالي:

```
[Desktop Entry]
Type=Application
Name=Postman
Icon=/opt/Postman/app/resources/app/assets/icon.png
Exec="/opt/Postman/Postman"
Comment=Postman Desktop App
Categories=Development;Code;

```