---
id: 5ccfad82bb2dc6c965a848e5
title: Отримання JSON fetch-методом JavaScript
challengeType: 6
forumTopicId: 301501
dashedName: get-json-with-the-javascript-fetch-method
---

# --description--

Щоб зробити запит зовнішніх даних використовуйте метод `fetch()`. Він еквівалентний методу `XMLHttpRequest`, проте синтаксис вважається простішим.

Ось код для створення запиту GET для `/json/cats.json`

```js

fetch('/json/cats.json')
  .then(response => response.json())
  .then(data => {
    document.getElementById('message').innerHTML = JSON.stringify(data);
  })

```

Зверніть увагу на кожен фрагмент коду.

Запит надсилає саме перший рядок. Так `fetch(URL)` робить запит `GET` на конкретну URL-адресу. Так створюється Promise.

Після створення Promise та успішного запиту, методом `then` код адаптується та перетворюється у формат JSON.

Метод `then` також створює Promise, що так само проходить обробку наступним `then` методом. Аргумент у другому `then` і є об'єктом JSON, який вам потрібен!

Тепер цим методом обирається елемент, який отримає дані за допомогою `document.getElementById()`. Далі код HTML елемента змінюється через додавання рядка з об'єктом JSON, поверненим за запитом.

# --instructions--

Щоб створити та надіслати запит `GET` до freeCodeCamp Cat Photo API, оновіть код. Використайте цього разу метод `fetch` замість `XMLHttpRequest`.

# --hints--

Щоб надіслати запит `GET`, використовуйте метод `fetch`.

```js
assert(code.match(/fetch\s*\(\s*('|")\/json\/cats\.json\1\s*\)/g));
```

Щоб конвертувати вхідні дані в JSON, використовуйте метод `then`.

```js
assert(
  code.match(
    /\.then\s*\(\s*\(?(?<var>\w+)\)?\s*=>\s*\k<var>\s*\.json\s*\(\s*\)\s*\)/g
  )
);
```

Щоб обробити конвертовані дані JSON методом `then`, використайте `then` у коді двічі.

```js
assert(__helpers.removeWhiteSpace(code).match(/\.then\(\(?\w+\)?=>{[^}]*}\)/g));
```

Щоб змінити внутрішній HTML на рядок з даними JSON, використовуйте у коді елемент з id `message`.

```js
assert(
  __helpers.removeWhiteSpace(code).match(
    /document\.getElementById\(('|")message\1\)\.innerHTML=JSON\.stringify\(?\w+\)/g
  )
);
```

# --seed--

## --seed-contents--

```html
<script>
  document.addEventListener('DOMContentLoaded',function(){
    document.getElementById('getMessage').onclick= () => {
      // Add your code below this line


      // Add your code above this line
    };
  });
</script>
<style>
  body {
    text-align: center;
    font-family: "Helvetica", sans-serif;
  }
  h1 {
    font-size: 2em;
    font-weight: bold;
  }
  .box {
    border-radius: 5px;
    background-color: #eee;
    padding: 20px 5px;
  }
  button {
    color: white;
    background-color: #4791d0;
    border-radius: 5px;
    border: 1px solid #4791d0;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    background-color: #0F5897;
    border: 1px solid #0F5897;
  }
</style>
<h1>Cat Photo Finder</h1>
<p id="message" class="box">
  The message will go here
</p>
<p>
  <button id="getMessage">
    Get Message
  </button>
</p>
```

# --solutions--

```html
<script>
  document.addEventListener('DOMContentLoaded',function(){
    document.getElementById('getMessage').onclick= () => {
      fetch('/json/cats.json')
        .then(response => response.json())
        .then(data => {
          document.getElementById('message').innerHTML=JSON.stringify(data);
        })
    };
  });
</script>
<style>
  body {
    text-align: center;
    font-family: "Helvetica", sans-serif;
  }
  h1 {
    font-size: 2em;
    font-weight: bold;
  }
  .box {
    border-radius: 5px;
    background-color: #eee;
    padding: 20px 5px;
  }
  button {
    color: white;
    background-color: #4791d0;
    border-radius: 5px;
    border: 1px solid #4791d0;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    background-color: #0F5897;
    border: 1px solid #0F5897;
  }
</style>
<h1>Cat Photo Finder</h1>
<p id="message" class="box">
  The message will go here
</p>
<p>
  <button id="getMessage">
    Get Message
  </button>
</p>
```
