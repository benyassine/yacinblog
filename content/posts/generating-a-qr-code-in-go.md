---
title: "توليد رمز الإستجابة السريعة QR Code في لغة Go"
date: 2025-09-19
tags: ["Go", "تعلم", "مقدمة عن Go","qrcode"]
pinned: false
---

توليد QR Code في للغة Go في غاية البساطة بفضل توفر العديد من المكتبات المجانية ومفتوحة المصدر مثل:github.com/skip2/go-qrcode
وسنتطرق في هاذا المقال إلى طريقة إستعمال المكتبة لتوليد QR code الخاص بنا.

# 1. تثبيت المكتبة:
أولا يجب عليك جلب المكتبة عبر كتابة السطر التالي في سطر الأوامر 
```
go get -u github.com/skip2/go-qrcode
```
# 2.كتابة برنامج Go
الآن نحتاج إلى كتابة برنامج بسيط إعتمادا على المكتبة التي قمنا بتثبيتها سابقة يحتوي على النص المراد تحويله إلى QR Code 

```
package main

import (
    "github.com/skip2/go-qrcode"
    "log"
)

func main() {
    err := qrcode.WriteFile("https://example.com", qrcode.Medium, 256, "qrcode.png")
    if err != nil {
        log.Fatal(err)
    }
}
```
يقوم البرنامج السابق بتوليد صورة PNG ويحفظها في القرص الصلب بإسم   qrcode.png

تستطيع أيضا توليد سلسلة بايتات -_-   و إعادة إستخدامها وعرضها في صفحة ويب مثلا أو تمكين المستخدم من تحميلها عبر الكود التالي :

```
  var png []byte
  png, err := qrcode.Encode("https://example.org", qrcode.Medium, 256)
```
أو المزيد من التخصيص مثل التحكم في الألوان عبر إستخذام الوظائف المتاحة في الكتبة المستعملة 

```
  err := qrcode.WriteColorFile("https://example.org", qrcode.Medium, 256, color.Black, color.White, "qr.png")
```
# الخلاصة
بخطوات بسيطة توفر لك مكتبة go-qrcode الكثير من الحلول أثناء توليد رموز الإستجابة السريعة 

و يمكنك زيارة المستودع و الإطلاع على الكود و التوثيق للتعرف أكثر على المكتبة 
[go-qrcode](https://github.com/skip2/go-qrcode)
