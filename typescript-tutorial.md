
## 🎥 **مقدمة تايبسكريبت**

### ✅ **شنو هو تايبسكريبت؟**

تايبسكريبت هي لغة برمجة كتشبه جافاسكريبت بزاف، ولكن فيها إضافة مهمة:

📌 **الأنواع**.

يعني فـ تايبسكريبت قبل ما تستعمل متغيّر، كتحدد النوع ديالو: واش `string`, `number`, `boolean`, ولا شي حاجة أخرى.
وهكذا كتحمي راسك من بزاف ديال الأخطاء اللي ممكن توقع فـ JavaScript بلا ما تحس!

> 🧠 **مثال بسيط:**

```ts
let name: string = "Ahmed";
name = 123; // ❌ غادي يعطيك خطأ لأن 123 ماشي string
```

---

### 🤔 **علاش نستعمل تايبسكريبت؟**

1. ✅ **أمان في الكود:** الأخطاء كيبانوا قبل ما تشغّل البرنامج.
2. 👨‍💻 **تحسين تجربة المطوّر:** أي IDE بحال VS Code كيعطيك إقتراحات ذكية لأن تايبسكريبت "فاهم" نوع الكود ديالك.
3. 📦 **كود منظم وواضح:** خصوصاً ف المشاريع الكبيرة، الكود كيولي سهل يتقرا ويتطوّر.
4. 🚀 **دعم حديث لـ JavaScript:** تايبسكريبت كيدعم آخر الميزات وكيحوّل الكود لـ جافاسكريبت باش يخدم فايا بلاصة.

---

### 🧠 **مفاهيم أساسية في تايبسكريبت**

#### 1. ✅ الأنواع الأساسية (Primitive Types)

```ts
let username: string = "Omar";
let age: number = 30;
let isLoggedIn: boolean = true;
```

#### 2. ✅ المتغيرات القابلة لأكثر من نوع (Union Types)

```ts
let userId: string | number = "user_1";
userId = 100; // ✅ مسموح
```

#### 3. ✅ الأنواع اللي مافيهم والو (null, undefined)

```ts
let x: null = null;
let y: undefined = undefined;
```

---

### ⚔️ **الفرق بين interface و type**

#### 🔹 `interface` (واجهة)

كاتستعملها باش تحدد شكل object، خصوصاً فالـ OOP.

```ts
interface User {
  name: string;
  age: number;
}
```

تقدر دير ليها Scaling:

```ts
interface Admin extends User {
  role: string;
}
```

#### 🔸 `type` (نوع)

عندها نفس الدور تقريبا، ولكن فيها مرونة أكثر فـ التركيبات المعقدة:

```ts
type ID = string | number;

// ❌ هذا غير صحيح ولن يعمل:
interface Id = number | string;

type User = {
  name: string;
  age: number;
};

type Admin = User & {
  role: string;
};
```

🔑 **الخلاصة:**

* `interface` أفضل لتعريف الكائنات.
* `type` أفضل لتعريف أنواع مركبة ومعقدة.

---

### 🧱 **مفاهيم مهمة فـ البرمجة الكائنية (OOP)**

#### 🔧 `class` (كلاس)

```ts
class Person {
  name: string;
  constructor(name: string) {
    this.name = name;
  }

  greet() {
    console.log(`Hi, I'm ${this.name}`);
  }
}
```

#### 🧬 الوراثة (Inheritance)

```ts
class Animal {
  move() {
    console.log("Moving...");
  }
}

class Dog extends Animal {
  bark() {
    console.log("Woof!");
  }
}
```

#### 🔁 التعددية (Polymorphism)

```ts
class Shape {
  draw() {
    console.log("Drawing shape");
  }
}

class Circle extends Shape {
  draw() {
    console.log("Drawing circle");
  }
}

function render(shape: Shape) {
  shape.draw(); // النوع الحقيقي كيحدد شنو يتنفذ
}
```

---

### 🔐 **أنواع الوصول: public, private, protected**

```ts
class BankAccount {
  public name: string;
  private balance: number;

  constructor(name: string, balance: number) {
    this.name = name;
    this.balance = balance;
  }

  public getBalance() {
    return this.balance;
  }
}
```

* `public`: متاح للجميع.
* `private`: غير متاح إلا داخل نفس الكلاس.
* `protected`: متاح داخل الكلاس والأبناء ديالو.

---

### 🌐 **Generics - الأنواع العامة**

كتستعمل `Generics` باش تكتب دوال وكلاسات مرنة تستقبل أنواع مختلفة:

```ts
function identity<T>(value: T): T {
  return value;
}

identity<string>("hello");
identity<number>(42);
```

#### 📦 مثال عملي:

```ts
interface Box<T> {
  value: T;
}

let numberBox: Box<number> = { value: 10 };
let stringBox: Box<string> = { value: "hello" };
```

---

### 🎨 **العدادات (`enum`)**

```ts
enum Direction {
  Up,
  Down,
  Left,
  Right
}

let move: Direction = Direction.Left;
console.log(move); // 2
```

---

### 💬 **أنواع متقدمة: Literal, Tuple, any, unknown**

#### ✅ Literal

```ts
Named -> 'String literal union type'
let direction: "left" | "right";
direction = "left";
```

#### ✅ Tuple

```ts
let user: [string, number] = ["Ahmed", 25];
```

#### ❗ any (تفاداه إلا للضرورة)

```ts
let data: any = 5;
data = "hello"; // مسموح ولكن خطر
```

#### ✅ unknown (أكثر أماناً من any)

```ts
let value: unknown = "hello";

if (typeof value === "string") {
  console.log(value.toUpperCase());
}
```

---

### 🛠️ **أخطاء شائعة يجب تتفادها**

* ❌ استخدام `any` بدون سبب.
* ❌ تجاهل الأنواع في الباراميترات.
* ❌ عدم استخدام واجهات (`interface`) ف الكود المعقد.
---

### 🎯 **الخلاصة**

| الفائدة             | التفسير                               |
| ------------------- | ------------------------------------- |
| ✅ أمان الكود        | تايبسكريبت كيكشف الأخطاء قبل التشغيل  |
| 📘 توثيق أوتوماتيكي | الأنواع كتشكل توثيق للكود             |
| 🔄 صيانة أسهل       | أي مبرمج يقدر يفهم ويتابع المشروع     |
| 📊 أداء الفريق      | كل واحد يفهم المتغيرات والأنواع بسرعة |


---

### 📢 **ما تنساش:**

* 💬 قول لينا فالتعليقات: واش تايبسكريبت عجبك؟
* 👍 خلي لايك إذا فادك الفيديو.
* 🧑‍💻 تابع القناة باش يوصلك الجديد.

