---
id: bad87fee1348bd9aec908849
title: Füge Elemente deinen Bootstrap Wells hinzu
challengeType: 0
forumTopicId: 16636
dashedName: add-elements-within-your-bootstrap-wells
---

# --description--

Jetzt sind wir mehrere `div`-Elemente tief in jeder Spalte unserer Reihe. Tiefer werden wir nicht gehen. Nun können wir unsere `button`-Elemente hinzufügen.

Verschachtel drei `button`-Elemente in jedes deiner `div`-Elemente mit dem Klassennamen `well`.

# --hints--

Drei `button`-Elemente sollten in jedem deiner `div`-Elemente der Klasse `well` verschachtelt sein.

```js
assert(
  $('div.well:eq(0)').children('button').length === 3 &&
    $('div.well:eq(1)').children('button').length === 3
);
```

Du solltest insgesamt 6 `button`-Elemente haben.

```js
assert($('button') && $('button').length > 5);
```

All deine `button`-Elemente sollten abschließende Tags enthalten.

```js
assert(
  code.match(/<\/button>/g) &&
    code.match(/<button/g) &&
    code.match(/<\/button>/g).length === code.match(/<button/g).length
);
```

# --seed--

## --seed-contents--

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <div class="well">



      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">



      </div>
    </div>
  </div>
</div>
```

# --solutions--

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <div class="well">
        <button></button>
        <button></button>
        <button></button>
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">
        <button></button>
        <button></button>
        <button></button>
      </div>
    </div>
  </div>
</div>
```
