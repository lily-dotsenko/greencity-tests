# Test Cases – GreenCity Events Page

---
## TC-01: Перевірка роботи пошуку подій за назвою (Eco Meetup 2026)

**Title:** Verify search functionality is case-insensitive and returns correct results  
**Priority:** High  
**Preconditions:**  
- Користувач знаходиться на сторінці https://www.greencity.cx.ua/#/greenCity/events  
- У списку подій присутня подія "Eco Meetup 2026"  

| Step | Action | Data | Expected Result |
|:---:|---|---|---|
| 1 | Знайти поле пошуку на сторінці | - | Поле пошуку доступне для введення |
| 2 | Ввести частину назви події (з малої літери) | eco | Введений текст відображається у полі |
| 3 | Виконати пошук | Enter або кнопка пошуку | Відображається подія "Eco Meetup 2026" у результатах |
| 4 | Очистити поле та ввести назву з великої літери | Eco | Результат повинен бути таким самим |
| 5 | Ввести повну назву події | Eco Meetup 2026 | Відображається відповідна подія |
| 6 | Перевірити результати пошуку | - | Результати відповідають введеному запиту незалежно від регістру |

**Actual Result:**  
- При введенні "eco", "Eco" або повної назви "Eco Meetup 2026" результати не відображаються  
- Система показує:  
  "0 Items found"  
  "We didn't find any results matching to this search"  

**Expected Result:**  
- Пошук повинен бути нечутливим до регістру (case-insensitive)  
- При введенні "eco", "Eco" або повної назви повинна відображатися подія "Eco Meetup 2026"  

**Status:** Failed (Search functionality bug)  

---

## TC-02: Перевірка відображення списку подій

**Title:** Verify that event cards are displayed correctly  
**Preconditions:**  
- Користувач відкрив сторінку https://www.greencity.cx.ua/#/greenCity/events  

| Step | Action | Data | Expected Result |
|:---:|---|---|---|
| 1 | Відкрити сторінку подій | URL | Сторінка успішно завантажується |
| 2 | Дочекатися завантаження контенту | - | Відображається список подій |
| 3 | Перевірити картки подій | - | Кожна картка містить основну інформацію |
| 4 | Перевірити наявність ключових полів | Title, Date, Location | Дані відображаються коректно |

---

## TC-03: Перевірка відображення деталей події "Community Cleanup Saturday"

**Title:** Verify event details and image display for a specific event  
**Priority:** High  
**Preconditions:**  
- Користувач відкрив сторінку https://www.greencity.cx.ua/#/greenCity/events  
- У списку подій присутня подія "Community Cleanup Saturday"  

| Step | Action | Data | Expected Result |
|:---:|---|---|---|
| 1 | Знайти подію "Community Cleanup Saturday" | Event name | Подія відображається у списку |
| 2 | Натиснути кнопку "More" або картку події | Click | Відкривається сторінка з деталями події |
| 3 | Перевірити блок зображення | - | Зображення події повинно відображатися |
| 4 | Перевірити альтернативний текст зображення | - | Якщо зображення не завантажилось, відображається коректний alt-text |
| 5 | Перевірити текстовий контент | - | Відображається опис події та інша інформація |

**Actual Result:**  
- Зображення не відображається  
- Відображається лише текстовий опис зображення (alt text: "event")  

**Expected Result:**  
- Зображення події повинно коректно завантажуватись і відображатись разом з описом  
- Alt-text відображається лише у випадку помилки завантаження зображення  

**Status:** Failed (UI bug / image loading issue)  