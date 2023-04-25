
# خطوات إنشاء GPG key 

## 1. تثبيت برنامج GPG

- في البداية سنقوم بتثبيت البرنامج حسب نظام التشغيل الخاص بك من خلال الرابط التالي: [اضغط هنا](https://www.gnupg.org/download/).

## 2. فتح برنامج Command Line Interface

## 3. إنشاء `gpg key`

يوجد أكثر من `GPG key algorithms` مثل:
- RSA 
- ElGamal 
- DSA
- ECDH

 
وفي المثال التالي سنقوم باستخدام `RSA Key Algorithm`.


```
$ gpg --full-generate-key
``` 

## 4. تحديد gpg key algorithm

-  سيطلب منك إختيار نوع `gpg key algorithm` سنقوم باختيار الخيار الأول 
    
    
```
  (1) RSA and RSA
  (2) DSA and Elgamal
  (3) DSA (sign only)
  (4) RSA (sign only)
  (9) ECC (sign and encrypt) *default*
  (10) ECC (sign only)
  (14) Existing key from card
  ```
  
  ## 5. تحديد gpg key size

- سيطلب منك تحديد حجم key أو اختيار الوضع الافتراضي ويجب أن يكون على الأقل `4096 bits` سنقوم باختيار `4096`

```
RSA keys may be between 1024 and 4096 bits long.
What keysize do you want? 
```

  ## 6. تحديد فترة صلاحية gpg key

- ثم سيطلب تحديد مدة صلاحية `gpg key` حسب سنة أو شهر أو اسبوع أو يوم , عند تحديد `0` فلن يكون هناك تاريخ لإنتهاء صلاحية `gpg key`  
- عند تحديد `1y` سيكون تاريخ صلاحيتة سنة.
- يرمز لحرف `n` عدد الأيام لإنتهاء صلاحية `gpg key`

```
Please specify how long the key should be valid.
         0 = key does not expire
      <n>  = key expires in n days
      <n>w = key expires in n weeks
      <n>m = key expires in n months
      <n>y = key expires in n years
```

  ## 7. إضافة user ID information

- ثم بعد ذلك سيطلب منك تحديد الاسم والبريد الالكتروني 

```
GnuPG needs to construct a user ID to identify your key.
- Real name:
- Email address:
- Comment:
```

## 8. إضافة الرقم السري passphrase

- سيطلب منك إدخال الرقم السري 
```
Type a secure passphrase.
```

- والخطوة الأخير وهي التأكيد لإنشاء `gpg key` أو تعديل البيانات الشخصية. عند اختيار `O` سيتم إنشاء `gpg key`

```
Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit?
```

-سيتم حفظ `gpg key` بداخل المجلد المخفي بأسم `gnupg.` بعد أن تم إنشاء `gpg key` تستطيع التحقق من خلال الامتداد الخاص بك

```
gpg: /Users/<Your Name>/.gnupg/trustdb.gpg: trustdb created
```

