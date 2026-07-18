# إدارة المصفوفات في JavaScript الحديثة: إعادة الهيكلة (Array Destructuring)

**الدرس من دورة Jonas Schmedtmann - The Complete JavaScript Course 2025**

---

## ما هي إعادة الهيكلة (Destructuring)؟

**إعادة الهيكلة** هي ميزة حديثة في JavaScript (ES6) تسمح باستخراج قيم من مصفوفة أو كائن وتخزينها في متغيرات منفصلة بطريقة أنيقة ومختصرة.

بدلاً من الوصول إلى العناصر بالطريقة التقليدية باستخدام الفهرس، يمكننا "تفكيك" المصفوفة في سطر واحد.

---

## 1. المثال الأساسي

```js
const arr = [2, 3, 4];

// الطريقة التقليدية (قديمة)
const a = arr[0];
const b = arr[1];
const c = arr[2];

// باستخدام Destructuring (الطريقة الحديثة)
const [x, y, z] = arr;

console.log(x, y, z); // 2 3 4
ملاحظة: المصفوفة الأصلية لا تتغير أبداً.

2. تخطي العناصر
يمكنك تخطي أي عنصر بترك فاصلة فارغة:
JavaScriptconst [main, , secondary] = restaurant.categories;
// main = "Italian"
// secondary = "Vegetarian"

3. تبديل قيم المتغيرات (Variable Swapping)
أجمل استخدامات Destructuring:
JavaScript// الطريقة القديمة (تحتاج متغير مؤقت)
let temp = main;
main = secondary;
secondary = temp;

// الطريقة الحديثة (Destructuring)
[main, secondary] = [secondary, main];

4. إرجاع قيم متعددة من دالة
JavaScriptorder(starterIndex, mainIndex) {
    return [this.starters[starterIndex], this.mainMenu[mainIndex]];
}

// الاستخدام
const [starter, mainCourse] = restaurant.order(2, 0);
console.log(starter, mainCourse); // "Garlic Bread" "Pizza"

5. إعادة الهيكلة المتداخلة (Nested Destructuring)
JavaScriptconst nested = [2, 4, [5, 6]];

// استخراج المصفوفة الداخلية
const [i, , j] = nested;

// استخراج القيم بشكل كامل
const [a, , [b, c]] = nested; // a=2, b=5, c=6

6. القيم الافتراضية (Default Values)
مفيدة جداً عند التعامل مع بيانات غير مضمونة (مثل API):
JavaScriptconst [p = 1, q = 1, r = 1] = [8, 9];

console.log(p, q, r); // 8 9 1

لماذا نستخدم Array Destructuring؟

كود أنظف وأكثر اختصاراً
أكثر وضوحاً وقراءة
يُستخدم بكثرة في المكتبات الحديثة والإطارات (React, Vue, Node.js)
يدعم القيم الافتراضية، التبديل السريع، والقيم المتداخلة


الدرس القادم:
Object Destructuring + Spread Operator + Rest Pattern
