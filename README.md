# Tahlilgaran Desktop
# آموزش قدم‌به‌قدم نصب نرم‌افزار ویندوزی (تحلیل‌گران) روی لینوکس با Bottles و Wine

این آموزش روی اوبونتو تست شده، اما روی بیشتر توزیع‌های معروف لینوکس مثل Fedora، Arch و… هم قابل اجراست، مخصوصاً اگر Flatpak روی سیستم فعال باشه.
پیش‌نیازها: نصب ابزارهای لازم
1. نصب Flatpak و اتصال به Flathub

برای اوبونتو و مشابه‌ها:

```
sudo apt update
sudo apt install flatpak gnome-software-plugin-flatpak -y
```

بعدش مخزن Flathub رو اضافه کنین:

flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

در توزیع‌های دیگه (مانند Fedora یا Arch) معمولاً Flatpak به صورت پیش‌فرض نصبه، فقط مطمئن شین Flathub فعاله.
2. نصب Bottles، Wine و Winetricks از Flathub

میتونی یا از Software Center لینوکس (مرکز نرم‌افزار) اینارو نصب کنی یا از ترمینال، که برای همه توزیع‌ها جواب می‌ده:

```
flatpak install flathub com.usebottles.bottles
flatpak install flathub org.winehq.Wine
flatpak install flathub org.winehq.Winetricks
```

ساخت محیط مخصوص نرم‌افزار با Bottles

Bottles رو باز کن.

روی Create a new Bottle کلیک کن.

نوع Bottle رو بزن Custom (دلخواه و انعطاف‌پذیرترین حالت).

یک اسم مناسب براش انتخاب کن، مثلاً: TDictionary.

منتظر بمون تا ساخت کامل شه.

نصب پیش‌نیازهای نرم‌افزار داخل Bottle

وارد Bottle ساخته‌شده شو، به بخش Dependencies یا Installers برو و این دوتا رو نصب کن:

✅ dotnet48 — برای اجرای نرم‌افزارهای مبتنی بر دات‌نت مثل دیکشنری تحلیل‌گران.
✅ memo — به تجربه تو، برای اجرای صحیح نرم‌افزار تحلیل‌گران نیازه.
نصب نرم‌افزار تحلیل‌گران داخل Bottle

فایل نصب (Setup.exe یا مشابهش) رو داخل Bottle اجرا کنین.
راحت‌ترین روش:
داخل ترمینال اینو بزنین (مسیر فایل رو دقیق بزنین):

```
flatpak run com.usebottles.bottles-cli run -b TDictionary wine "/path/to/file/Setup.exe"
```

مراحل نصب رو مثل ویندوز انجام بده.

اجرای نرم‌افزار

بعد از نصب، می‌تونی از داخل خود Bottles یا با دستور زیر نرم‌افزار رو اجرا کنین:

```
flatpak run com.usebottles.bottles-cli run -b TDictionary wine "C:\\Program Files (x86)\\TahlilGaran\\TDictionary\\Bin\\TDictionary.exe"
```

نکته: مسیر بالا نمونه است، بسته به محل نصب واقعی نرم‌افزار ممکنه فرق کنه.
نکته مهم در پایان

همه‌چیز به‌خوبی نصب شد و نرم‌افزار اجرا می‌شه، اما:

🚫 هنوز موفق نشدم نرم‌افزار رو به اینترنت وصل کنم، در نتیجه بخش فایل‌های صوتی آنلاینش (مثل تلفظ جملات) کار نمی‌کنه.
اگه کسی روشی برای حل این مشکل داره، ممنون می‌شم اطلاع بده.
✅ جمع‌بندی سریع:

✔ Bottles رو نصب کن
✔ یک Bottle سفارشی بساز
✔ dotnet48 و memo رو نصب کن
✔ نرم‌افزار تحلیل‌گران رو داخلش نصب کن
✔ اجراش کن و لذت ببر!
✔ در حال حاضر، مشکل اینترنت نرم‌افزار هنوز باقیه
