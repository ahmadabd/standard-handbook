# فصل چهارم: اصول comment گذاری

### Comment گذاری در برنامه نویسی اصولی دارد که در اینجا به آن میپردازیم.

---------------

## Comment:

کامنت توضیحاتی هستند که در جاهای مختلف کد قرار میگیره و در مورد خود برنامه یا یک متغیر یا تابع و یا فایل خاصی از برنامه توضیحاتی را می دهند.

خطوطی که کامنت میشوند توسط سیستم اجرا نشده و تاثیری در خروجی برنامه و یا زمان اجرای برنامه ندارند.

> برای مطالعه بیشتر روی کامنت ها به این [لینک](https://www.cs.utah.edu/~germain/PPS/Topics/commenting.html) مراجعه کنید.

--------------------------------

## اهمیت Comment گذاری:

برنامه نویسانی که زمان زیادی را روی یک پروژه صرف میکنند اهمیت کامنت گذاری را خیلی خوب میدانند.

برنامه با بزرگ و بزرگ شدن خود پیچیده تر میشود, گاهی اوقات نیاز است برنامه نویس به کد های گذشته خود باز گردند, یا برنامه نویسان جدید به پروژه اضافه میشوند,‌ در اینجاست که اهمیت کامنت مشخص میشود.

ایجاد کامنت برای متغیرها, توابع, فایلها و هر جای پر اهمیت دیگر پروژه باعث نجات برنامه نویش از سردرگمی میشود.

--------------------------------

##### در زبان های برنامه نویسی از علایم مختلفی برای کامنت گذاری استفاده میشه:

- در python از #
- از // برای کامنت کردن یک خط و از /**/ برای کامنت کردن بیش از یک خط در زبانهای java, c#, c++, c, css, ... استفاده میشود
- در متلب از %
- *...*

## انواع روش های Comment گذاری:

### ۱. Inline Commenting:

**Inline Comment** توضیحاتی در خصوص  یکی از خطهای برنامه میدهد, مثلا دلیل ایجاد یک متغیر یا دلیل وجود یک شرط در برنامه.

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

وقتی در برنامه نیاز به گذاشتن کامنت بزرگتر از یک خط دارید از **Descriptive Blocks** استفاده میکنید.



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

در بالای فایل برنامه یا در بالای هر کتابخانه ای که برای برنامه خود مینویسید قرار میگیرد که شامل مستنداتی شامل برنامه یا أن فایل میشود,

**از قبیل**:

- هدف طراحی برنامه یا کتابخانه مورد نظر
- نام وآدرس ایمیل برنامه نویس
- **requirements** ها که شامل دیگر فایل ها و کتابخانه هایی هستند که این برنامه برای اجرا شدن به آنها نیاز دارد.

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

در **css** از // و /**/  برای کامنت گذاری استفاده میکنیم.

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



همچنین در html از--!> در ابتدا و از<-- در انتهای خط برای کامنت کردن بک خط یا مجموعه ای از خطوط استفاده میشود.

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

> برای دیدن مثالهای بیشتر به این [لینک](https://www.hongkiat.com/blog/source-code-comment-styling-tips/) مراجعه کنید.