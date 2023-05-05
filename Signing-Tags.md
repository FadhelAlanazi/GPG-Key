## التوقيع باستخدام Tags

- في المثال التالي لدينا مشروع يتكون من 3 commits وسنقوم بإنشاء tag بأسم `v1.0` مع إضافة التوقيع على tag.

![](https://raw.githubusercontent.com/FadhelAlanazi/GPG-Key/main/Signing-Tags.png)

#### في البداية نحتاج الى استخدام private key لعمل التوقيع على Tags أو Commits ، ومن خلال GPG key ID سنقوم بتنفيذ الخطوات التالية:

- سنقوم بكتابة الامر التالي في command line لإستخراج GPG key ID
```
gpg --list-secret-keys --keyid-format=short
```

1. ثم بعد ذلك سنقوم بأخذ GPG key ID المكون من 8 خانات **XXXXXXXX** كما في الصورة الموضحة أدناه.


![](https://raw.githubusercontent.com/FadhelAlanazi/GPG-Key/main/Privatekey.png)

**ملاحظة:** في حال عدم ظهور GPG key ID حسب الصورة أعلاه يجب الرجوع الى خطوات إنشاء GPG Key

2. ثم سنقوم بكتابة الأمر التالي في Command Line ونضع GPG key ID في نفس الامر:

```
git config --global user.signingkey <GPG key ID> 
```


- **الان أصبحنا جاهزين لعمل التوقيع في المشروع**. 

3. **كيفية إنشاء Tag بأسم `v1.0` مع إضافة التوقيع عليها** 

```
git tag -s v1.0 -m "signed my tag v1.0"
```
4. سيطلب منك إدخال الرقم السري passphrase الذي تم إنشاؤه في `gpg key`



- تم الانتهاء من إنشاء Tag بأسم `v1.0` مع إضافة التوقيع. 

----


##  التحقق من Signed Tags

- نستطيع التحقق من التوقيع على `tag v1.0` عن طريق كتابة الامر التالي:

```
git tag -v v1.0
```

- ستظهر رسالة التحقق من التوقيع على `tag v1.0` كما في الشكل التالي:

```
signed tag v1.0
gpg: Signature made Mon Apr 24 07:03:06 2023 +03
gpg:                using RSA key 
gpg: Good signature from "FadhelAlanazi <your email>" [ultimate]
```
- **تم الانتهاء من التحقق من التوقيع على `tag v1.0`**.
