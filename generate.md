---
layout: post
title: Generate Page
---

# Generate Page

Select options from the dropdowns below:
    
| Форма | Описание |
| --- | --- |
| <select name="option1"><option value="">Select option 1</option><option value="Value 1">Value 1</option><option value="Value 2">Value 2</option><option value="Value 3">Value 3</option></select> | <span id="options-1"></span> |
| <select name="option2"><option value="">Select option 2</option><option value="Value 4">Value 4</option><option value="Value 5">Value 5</option><option value="Value 6">Value 6</option></select> | <span id="options-2"></span> |
| <select name="option3"><option value="">Select option 3</option><option value="Value 7">Value 7</option><option value="Value 8">Value 8</option><option value="Value 9">Value 9</option></select> | <span id="options-3"></span> |



Selected options: <span id="selected-options"></span>

<script>
  // Get the select elements
  const option1 = document.querySelector('select[name="option1"]');
  const option2 = document.querySelector('select[name="option2"]');
  const option3 = document.querySelector('select[name="option3"]');

  // Get the span element for displaying selected options
  const selectedOptions = document.querySelector('#selected-options');
  const options1 = document.querySelector('#options-1');
  const options2 = document.querySelector('#options-2');
  const options3 = document.querySelector('#options-3');

  // Add event listeners to the select elements
  option1.addEventListener('change', updateSelectedOptions);
  option2.addEventListener('change', updateSelectedOptions);
  option3.addEventListener('change', updateSelectedOptions);

  // Function to update the selected options
  function updateSelectedOptions() {
    // Get the selected values
    const value1 = option1.value;
    const value2 = option2.value;
    const value3 = option3.value;

    // Update the text of the span element with the selected values
    selectedOptions.textContent = `${value1}, ${value2}, ${value3}`;
    options1.textContent = `${value1}`;
    options2.textContent = `${value2}`;
    options3.textContent = `${value3}`;
  }
</script>



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
