
---

# 🧵 sass.w — פרויקט חנות בגדים

פרויקט זה מדגים בנייה של אתר מלא לחנות בגדים תוך שימוש ב־**SASS** (או SCSS) בצורה מודרנית, מסודרת ונכונה.
המטרה היא ללמוד לעבוד עם SASS בארכיטקטורה אמיתית של פרויקט ולראות כיצד ארגון נכון של קבצים משפר את היעילות, הקריאות והתחזוקה של הקוד

 https://sass-w-clothing-store.more-ways.co.il/
 <img width="836" height="532" alt="image" src="https://github.com/user-attachments/assets/f509120f-2d07-4e52-a555-845f2ab62a9e" />
   <img width="851" height="547" alt="image" src="https://github.com/user-attachments/assets/a04d6be0-7c3b-4ddd-a242-62d6a4c209e6" />
.

---

## 🎯 מה לומדים בפרויקט

הפרויקט מדגים שליטה בכמה נושאים מרכזיים ב־SASS:

### 1. **Variables — משתנים**

* הגדרת צבעים במקום מרכזי
* הגדרת גדלי פונטים
* יצירת מערכת עיצוב קבועה
  באמצעות `map-get` נוכל לקרוא לצבעים וגדלים בכל חלק באתר בצורה קלה:

```scss
$colors: (
  primary: #333,
  secondary: #ffe,
  tertiary: #f2f0f1,
);
```

---

### 2. **Mixins — מיקסים**

הפרויקט משתמש בהרבה Mixins כדי לחסוך חזרה על קוד:

* `flexPosition()` — ליישור מהיר של Flexbox
* `navigation()` — לעיצוב תפריטים
* `footerList()` — לעיצוב רשימות תחת footer
* `response()` — מנגנון ההתאמה למסכים שונים (RWD)

לדוגמה:

```scss
@mixin flexPosition($justCont: center, $alignIte: center) {
  display: flex;
  justify-content: $justCont;
  align-items: $alignIte;
}
```

---

### 3. **Functions — פונקציות מותאמות אישית**

הפרויקט כולל פונקציות SASS אמיתיות:

* `color()` לקבלת צבעים מהמפה
* `size()` לקבלת גדלי פונטים מוגדרים

לדוגמה:

```scss
font-size: size(md);
background-color: color(primary);
```

---

### 4. **Nested Selectors — קינון**

במקום לכתוב סלקטורים ארוכים — הכל מאורגן בצורה היררכית:

```scss
.logo {
  &-img {
    width: 10rem;
  }
}
```

---

### 5. **ארכיטקטורת קבצים מקצועית של SCSS**

הפרויקט בנוי לפי שיטת 7–1 המקצועית:

```
scss/
 ├── abstracts/
 │     ├── _variables.scss
 │     ├── _mixins.scss
 │
 ├── base/
 │     └── _base.scss
 │
 ├── components/
 │     ├── _logo.scss
 │     ├── _dropdown.scss
 │     ├── _button.scss
 │     └── _heading.scss
 │
 ├── layout/
 │     ├── _header.scss
 │     ├── _navigation.scss
 │     ├── _slideshow.scss
 │     ├── _products.scss
 │     └── _footer.scss
 │
 └── main.scss
```

`main.scss` מייבא את כל חלקי הפרויקט:

```scss
@import "abstracts/variables";
@import "abstracts/mixins";
@import "base/base";

@import "layout/header";
@import "layout/navigation";
@import "layout/slideshow";
@import "layout/products";
@import "layout/footer";

@import "components/logo";
@import "components/heading";
@import "components/dropdown";
@import "components/button";
```

---

### 6. **Responsive Design — רספונסיביות עם breakpoints**

הפרויקט מלמד שימוש חכם ב־Mixins של Breakpoints:

```scss
@include response(md) {
  font-size: 56.25%;
}
```

---

### 7. **בניית CSS קומפילטיבי**

הפלט הסופי נמצא בתיקיית:

```
css/main.css
```

שנוצר אוטומטית מריצת:

```
sass scss/main.scss css/main.css --watch
```

---

## 🧩 מה כולל האתר?

הפרויקט מדגים אתר חנות בגדים עם חלקים מלאים:

* Header עם לוגו ותפריט
* ניווט עליון + תפריט Dropdown
* סליידר תמונות דינאמי
* אזור מוצרים נבחרים
* כפתור מעוצב עם אנימציית hover
* Footer עשיר עם טופס הרשמה ורשתות חברתיות

כל אחד מהם נמצא בקובץ SCSS ייעודי לפי הארכיטקטורה.

---

## 🎓 למי מיועד הפרויקט?

* תלמידים שלומדים SASS לראשונה
* מפתחים שרוצים להבין מבנה נכון של SCSS
* מי שרוצה ללמוד איך עוברים מ־CSS רגיל לקוד מודולרי, חכם ומרוכז

---

## 🚀 איך מריצים את הפרויקט?

1. התקן SASS גלובלית:

   ```bash
   npm install -g sass
   ```

2. הרץ watch לקומפילציה:

   ```bash
   sass scss/main.scss css/main.css --watch
   ```
  


3. פתח את `index.html` בדפדפן ✨

---

## 📷 תמונות וארגון נכסים

התיקייה `images/` כוללת:

* רקעים לסליידר
* תמונות מוצרים
* לוגו

כל התמונות מוטענות אל תוך מבנה ה־grid של האתר.

---

## 📝 סיכום

בפרויקט זה בנינו אתר חנות מלא תוך שימוש בכל היכולות החשובות של SASS:
✔ משתנים
✔ פונקציות
✔ mixins
✔ קינון
✔ ארכיטקטורת SCSS אמיתית
✔ עיצוב מודרני ורספונסיבי

זהו בסיס מושלם למעבר לפרויקטים גדולים יותר — כולל Next.js, React או בניית Design System.

---
ך

