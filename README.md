<div dir="rtl">

![Design Patterns For Humans](https://cloud.githubusercontent.com/assets/11269635/23065273/1b7e5938-f515-11e6-8dd3-d0d58de6bb9a.png)
***

<h3 dir="rtl" align="center">
🎉 توضیح ساده دیزاین پترن ها ! 🎉
</h3>

<p dir="rtl" align="center">
فهمیدن دیزاین پترن ها از اون موضوع هاست که ذهن رو به چالش میکشه.
 اینجا سعی می‌کنم با مثال های ساده از دنیای واقعی و دنیای کد ، اونو راحت وارد ذهنتون کنم
</p>


***
منبع اصلی این ریپازیتوری    [این](https://github.com/3lf/design-patterns-for-humans) ریپازیتوری هست. که ما این رو با زبان دارت بازنویسی کردیم.

در ترجمه، تعاریف و مثال ها از منابع مختلف فارسی و انگلیسی استفاده شده تا بهترین نتیجه حاصل بشه :)
***

<div dir="rtl" align="center">

🚀 مقدمه
=================

</div>


 دیزاین پترن ها یک سری دستور العمل برای مقابله با یک سری مشکلات رایج هستند.

اونا یک سری کلاس، پکیج یا کتابخونه نیستند که با اضافه کردنشون به پروژه‌تون جادو کنن. در عوض یک سری راه حل بهتون میدن که
در شرایط خاص به مشکل نخورین.


<br>

> پس دیزاین پترن ها راه حلی برای مشکلات رایج هستن

<br>

**ویکی‌پدیا** دیزاین پترن‌ها رو اینطوری توصیف میکنه:

> در مهندسی نرم‌افزار، الگوی طراحی یک راه‌حل عمومی قابل تکرار برای مشکلات متداول در زمینه طراحی نرم‌افزار است. الگوی طراحی، یک طراحی تمام‌شده نیست که به صورت مستقیم بتواند تبدیل به کد منبع یا ماشین شود؛ بلکه، یک توضیح یا قالب برای حل یک مسئله در شرایط مختلف است. الگوها در واقع بهترین روش ممکن هستند که یک برنامه‌نویس می‌تواند در هنگام طراحی یک برنامه برای حل مشکلاتش از آن‌ها استفاده کند.


<br>
<div dir="rtl" align="right">

⚠ هشدار
-----------------

</div>

- الگو های طراحی برای همه مشکلات راه حل ندارن.
- سعی نکنین حتما توی پروژه هاتون از اونا استفاده کنین و یادتون باشه دیزاین پترن ها راه حلی برای مشکلات هستن، نه راه حلی
  برای پیدا کردن مشکلات، پس خیلی درگیر پیدا کردن دلیل برای استفاده ازشون نباشین.
- اگه از اونا جای درست استفاده کنین، شما پروژه رو از مشکلات نجات دادین درغیر اینصورت قراره فاجعه به بار بیاد.

<br>
<br>

***

<br>

<div align="center">

# Creational Design Patterns

</div>



به زبون ساده:
>  الگو های طراحی سازنده، به مشکلات مربوط به ساخت ابجکت ها می‌پردازن

ویکی پدیا:
<div dir="ltr">

> In software engineering, creational design patterns are design patterns that deal with object creation mechanisms, trying to create objects in a manner

</div>

<br>

<div align="center">

## 🏠 Simple Factory

</div>

یک مثال از دنیای واقعی:
> فرض کنید درحال ساخت یک خونه هستین و توی بخش های مختلف به درب نیاز دارین، خب اگه برای هر کدومش بخواین لباس نجاری بپوشین و درگیر ساختنش بشین، قراره کلی هرج و مرج تجربه کنین. به همین دلیل مردم ترجیح میدن برای حل این مشکل اونو از یک کارخونه تهیه کنن.


به زبون ساده:
> این دیزاین پترن برای کاربر اون چیزی که نیاز داره رو میسازه بدون اینکه درگیر منطق پشتش بشه.

ویکی پدیا:
<div dir="ltr">

> In object-oriented programming (OOP), a factory is an object for creating other objects – formally a factory is a function or method that returns objects of a varying prototype or class from some method call, which is assumed to be "new".

</div>

**مثال برنامه نویسی**

توی این مثال میخوایم از اون مثال ساخت درب استفاده کنیم

پس اول ما اینترفیس مربوط به درب رو میسازیم و در ادامه یک نمونه پیاده‌سازی براش پیاده‌سازی میکنیم:

<div dir="ltr">

```dart
abstract class Door{
  double getWidth();
  double getHeight();
}

class WoodenDoor implements Door{

  final double _width;
  final double _height;

  WoodenDoor(this._width, this._height);

  @override
  double getHeight() {
    return _height;
  }

  @override
  double getWidth() {
    return _width;
  }

}
```

</div>

و حالا یک کلاس factory برای ساخت درب میسازیم:
<div dir="ltr">

```dart
class DoorFactory{
  static Door makeDoor({required double width,required double height }){
    return WoodenDoor(width, height);
  }
}

```

</div>

حالا بیاین ببینیم چطوری می‌تونیم ازشون استفاده کنیم:

<div dir="ltr">

```dart
void main() {
  final door = DoorFactory.makeDoor(width: 100, height: 200);
  print(door.getWidth()); // print 100
  print(door.getHeight());// print 200
}
```

</div>
