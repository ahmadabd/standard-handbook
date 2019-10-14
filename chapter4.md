# فصل چهارم: اصول کامنت گذاری

### کامنت گذاری در برنامه‌نویسی اصولی دارد که در اینجا به آن می‌پردازیم.

---------------

## Comment:

کامنت به توضیحاتی گفته می‌شود که در مورد کد یا قسمتی از کد توضیحاتی را بیان می‌کند اما هنگام اجرای برنامه اجرا نمی‌شوند.

خطوطی که کامنت می‌شوند توسط سیستم اجرا نشده و تاثیری در خروجی برنامه و یا زمان اجرای برنامه ندارند.

> برای مطالعه بیشتر روی کامنت‌ها به این [لینک](https://www.cs.utah.edu/~germain/PPS/Topics/commenting.html) مراجعه کنید.

--------------------------------

## اهمیت کامنت گذاری:

برنامه‌نویسانی که زمان زیادی را روی یک پروژه صرف می‌کنند اهمیت آن را به خوبی درک می‌کنند.

برنامه با بزرگ شدن پیچیده‌تر می‌شود, گاهی اوقات نیاز است برنامه‌نویس به کد‌های گذشته خود باز‌گردد, یا ممکن است برنامه‌نویسان جدید به پروژه اضافه شوند که برای همکاری و هماهنگی با دیگر اعضای تیم نیاز به بررسی کد هستند,‌ در اینجاست که کامنت‌ها به برنامه‌نویس در فهم بیشتر کد کمک می‌کنند.

ایجاد کامنت برای متغیرها, توابع, فایل‌ها و هر جای پر اهمیت دیگر پروژه باعث نجات برنامه‌نویسان از سردرگمی می‌شود.

--------------------------------

##### در زبان‌های برنامه‌نویسی از علایم مختلفی برای کامنت‌گذاری استفاده می‌شود:

- در python از #
- از // برای کامنت‌کردن یک خط و از /**/ برای کامنت‌کردن بیش از یک خط در زبان‌های java, c#, c++, c, css, ... استفاده می‌شود
- در متلب از %
- *...*

## انواع روش های Comment گذاری:

### ۱. Inline Commenting:

**Inline Comment** شامل توضیحاتی در یک خط مجزا می‌باشد, مثلا دلیل ایجاد یک متغیر یا دلیل وجود یک شرط در برنامه.

*python*:

```python
# counts number of apples
aplCount = 0

# contains sum of fruits
sums = 0
```



*javaScript*:

```javascript
// counts number of apples
aplCount = 0

// contains sum of fruits
sums = 0
```



*C*:

```c
// counts number of apples
int aplCount = 0

// contains sum of fruits
int sums = 0
```



*javaScript*:

```javascript
if(callAjax($params)) { // successfully run callAjax with user parameters
 ... code 
}
```



*python*:

```python
if id not in featureSet: # check existance of 'id' in 'featureSet'
    return False
```



### ۲. Descriptive Blocks:

وقتی در برنامه نیاز به گذاشتن کامنت بزرگتر از یک خط دارید از **Descriptive Blocks** استفاده کنید.



*javaScript*:

```javascript
/**
  * @desc opens a modal window to display a message
  * @param string $msg - the message to be displayed
  * @return bool - success or failure
*/
function modalPopup($msg) {
	...
}
```



*python*:

```python
## this function get datas of api
## api is contains json code
## 'address' contains api url
def apiData(address):
    
    codes = requests.get(address)  
    jsonResult = json.loads(codes.content)
    
    return jsonResult
```



### ۳. Group/Class Comments:

در ابتدای هر کد کامنتی شامل توضیحات و مستندات برنامه قرار می‌گیرد.

**از قبیل**:

- هدف طراحی برنامه یا کتابخانه مورد نظر
- نام و آدرس ایمیل برنامه‌نویس
- **requirements** ها که شامل دیگر فایل‌ها و کتابخانه‌هایی هستند که این برنامه برای اجرا شدن به آنها نیاز دارد.

*java*:

```java
/** 
  * @desc this class will hold functions for user interaction
  * examples include user_pass(), user_username(), user_age(), user_regdate()
  * @author Ahmad Abdollahzade ahmadabdollahzade74@gmail.com
  * @required settings.php
*/

abstract class myWebClass { }
```



*python*:

```python
## @desc this class will hold functions for user interaction
## examples include user_pass(), user_username(), user_age(), user_regdate()
## @author Jake Rocheleau jakerocheleau@gmail.com
## @required settings.php

class getInfo:
    ...
```



### ۴. نحوه کامنت گذاری در کدهای **html** و  **css**:

در **css** از // و /**/  برای کامنت‌گذاری استفاده می‌کنیم.

*css*:

```css
//@keyframes foo {
  from, to { width: 500px; }
  50% { width: 400px; }
}
@keyframes bar {
  from, to { height: 500px; }
  50% { height: 400px; }
}
```

```css
// Do some stuff.
.foo { animation: bar 1s infinite; }
/* Whoops, the .foo block is commented out! */
```



همچنین در html از--!> در ابتدا و از<-- در انتهای خط برای کامنت کردن بک خط یا مجموعه‌ای از خطوط استفاده می‌شود.

*html*:

```html
<!-- You will not be able to see this text. -->

You can even comment out things in <!-- the middle of --> a sentence.

<!--
Or you can
comment out
a large number of lines.
-->

```



-------------------

> برای دیدن مثال‌های بیشتر به این [لینک](https://www.hongkiat.com/blog/source-code-comment-styling-tips/) مراجعه کنید.