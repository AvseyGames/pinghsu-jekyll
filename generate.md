---
layout: post
title: Generate Page
---





Выберите значения из списка ниже, чтобы сгенерировать результат:

{% assign values1 = "Значение 1, Значение 2, Значение 3" | split: ", " %}
{% assign values2 = "Значение A, Значение B, Значение C" | split: ", " %}
{% assign values3 = "Значение X, Значение Y, Значение Z" | split: ", " %}

## Список 1

<select id="select1">
  <option value="">Выберите значение</option>
  {% for value in values1 %}
    <option value="{{ value }}">{{ value }}</option>
  {% endfor %}
</select>

## Список 2

<select id="select2">
  <option value="">Выберите значение</option>
  {% for value in values2 %}
    <option value="{{ value }}">{{ value }}</option>
  {% endfor %}
</select>

## Список 3

<select id="select3">
  <option value="">Выберите значение</option>
  {% for value in values3 %}
    <option value="{{ value }}">{{ value }}</option>
  {% endfor %}
</select>

## Результат

<form id="result-form">
  <input type="text" id="result" name="result" value="" readonly>
</form>

<script>
  // Получаем элементы списков и формы результата
  var select1 = document.getElementById("select1");
  var select2 = document.getElementById("select2");
  var select3 = document.getElementById("select3");
  var resultForm = document.getElementById("result-form");
  var result = document.getElementById("result");

  // Обновляем результат при изменении выбранных значений
  select1.addEventListener("change", updateResult);
  select2.addEventListener("change", updateResult);
  select3.addEventListener("change", updateResult);

  function updateResult() {
    // Получаем выбранные значения из списков
    var value1 = select1.value;
    var value2 = select2.value;
    var value3 = select3.value;

    // Формируем строку результатов
    var resultString = "";

    if (value1) {
      resultString += value1 + ", ";
    }

    if (value2) {
      resultString += value2 + ", ";
    }

    if (value3) {
      resultString += value3;
    }

    // Устанавливаем значение формы результата
    result.value = resultString;
  }
</script>
