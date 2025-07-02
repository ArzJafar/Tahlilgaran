## Tahlilgaran Desktop

## آموزش قدم‌به‌قدم نصب نرم‌افزار ویندوزی (تحلیل‌گران) روی لینوکس با Bottles و Wine

من این آموزش رو روی ابونتو دسکتاپ تست کردم ولی روی بیشتر توزیع های معروف لینوکس مثل Arch, Fedora و… هم قابل اجراست.

####   
پیش‌نیازها: نصب ابزارهای لازم

1.  ##### نصب Flatpak و اتصال به Flathub
    

برای اوبونتو و مشابه‌ها:

```plaintext
sudo apt update
sudo apt install flatpak gnome-software-plugin-flatpak -y
```

بعدش مخزن Flathub رو اضافه کنین:

```plaintext
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

در توزیع‌های دیگه (مانند Fedora یا Arch) معمولاً Flatpak به صورت پیش‌فرض نصبه، فقط مطمئن شین Flathub فعاله.

#####   
2\. نصب Bottles، Wine و Winetricks از Flathub یا منبع دیگه

میتونی یا از Software Center لینوکس (مرکز نرم‌افزار) اینارو نصب کنی یا از ترمینال، که برای همه توزیع‌ها جواب می‌ده:

```plaintext
flatpak install flathub com.usebottles.bottles
flatpak install flathub org.winehq.Wine
flatpak install flathub org.winehq.Winetricks
```

**نکته: من از این راه رفتم ولی شما از هر راهی برین اوکیه. نکته اصلی اینه که wine رو نصب کنین و بعد Bottles. حالا از هر جا اینارو نصب کنین مهم نیست خیلی. :)**

حالا که Bottles, Wine رو دارین میریم مرحله بعد:

#### ساخت محیط مخصوص نرم‌افزار با Bottles

1.  محیط Bottles رو باز کنید.
2.  روی Create a new Bottle کلیک کنین.
3.  نوع Bottle رو بزنین Custom (دلخواه و انعطاف‌پذیرترین حالت).
4.  من نوع Runner رو Soda v.9 گذاشتم.
5.  یک اسم مناسب براش انتخاب کنین، مثلاً: TDictionary.
6.  منتظر بمونین تا ساخت کامل شه.

#### نصب پیش‌نیازهای نرم‌افزار داخل Bottle

به بخش Bottle برین و وارد بخش Dependencies  برین و دوتای زیر رو نصب کنین

*   dotnet48
*   memo

####   
نصب نرم‌افزار تحلیل‌گران داخل Bottle

داخل Bottle گزینه Run Executable… رو بزنین و فایل نصبی دیکشنری رو انتخاب کنین. (Setup.exe)

مراحل نصب رو مثل ویندوز انجام بدین تا تموم شه.

#### اجرای نرم‌افزار

بعد از نصب میتونین با کلیک روی سه نقطه نرم افزار رو به Library تون اد کنین.

بعد از نصب، می‌تونین از داخل خود Bottles یا با دستور زیر نرم‌افزار رو اجرا کنین:

```plaintext
flatpak run com.usebottles.bottles-cli run -b TDictionary wine "C:\\Program Files (x86)\\TahlilGaran\\TDictionary\\Bin\\TDictionary.exe"
```

نکته: مسیر بالا نمونه است، بسته به محل نصب واقعی نرم‌افزار ممکنه فرق کنه.

##### نکته آخر و درخواست کمک

همه‌چیز به‌خوبی نصب شد و نرم‌افزار اجرا می‌شه، اما:

هنوز موفق نشدم نرم‌افزار رو به اینترنت وصل کنم، در نتیجه بخش فایل‌های صوتی آنلاینش (مثل تلفظ جملات) کار نمی‌کنه.  
اگه کسی روشی برای حل این مشکل داره، ممنون می‌شم اطلاع بده.
