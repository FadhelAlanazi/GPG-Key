## التوقيع باستخدام Tags

#### في البداية نحتاج الى استخدام private key لعمل التوقيع، ومن خلال GPG Key سنقوم باستخراج private key عن طريق الخطوات التالية:

- سنقوم بكتابة الامر التالي في command line لإستخراج private key
```
gpg --list-secret-keys --keyid-format=short
```

1. ثم بعد ذلك سنقوم بأخذ private key المكون من 8 خانات كما في الصورة الموضحة أدناه في أول السطر.


![](https://github.com/FadhelAlanazi/GPG-Key/blob/main/private-key.png)

**ملاحظة:** في حال عدم ظهور private key حسب الصورة أعلاه يجب الرجوع الى خطوات إنشاء GPG Key

2. ثم سنقوم بكتابة الأمر التالي في Command Line ونضع private key في نفس الامر:

![](https://github.com/FadhelAlanazi/GPG-Key/blob/main/SigningKey.png)


- الان أصبحنا جاهزين لعمل التوقيع باستخدام private key في المشروع. 
- اذ كان لدينا مشروع يتكون من 3 commits نستطيع إنشاء tag مع إضافة التوقيع  لصاحب المشروع على أي commit.

3. **كيفية إنشاء Tag بأسم `v1.0` مع إضافة التوقيع عليها** 

```
git tag -s v1.0 -m "signed my tag v1.0"
```
4. سيطلب منك إدخال الرقم السري passphrase الذي تم إنشاؤه في `gpg key`


![](https://github.com/FadhelAlanazi/GPG-Key/blob/main/Signing-Tags.png)

- تم الانتهاء من إنشاء Tag بأسم `v1.0` مع إضافة اسم الموقع عليها و الرسالة الخاصة بالتوقيع. 

----


## التحقق من Signer tags

- نستطيع التحقق من الشخص الذي قام بالتوقيع على Tags عن طريق كتابة الامر التالي:

```
git tag -v v1.0
```

- ستظهر رسالة التحقق من صاحب التوقيع على `tag v1.0` كما في الشكل التالي:


![](https://github.com/FadhelAlanazi/GPG-Key/blob/main/Verifying-Signer-tags.png)

- تم الانتهاء من التحقق من صاحب التوقيع على `tag v1.0`.

**ملاحظة: عند القيام بالتحقق من صاحب التوقيع على Tags أو commits  يجب الحصول على public key الخاص بالموقع ليتم التحقق منه**
