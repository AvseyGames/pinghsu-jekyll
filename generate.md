---

layout: post

title: Private policy

---

<div class="generate-container">
  <div class="generate-form">
    <h2>Generate Results</h2>
    <form>
      <fieldset>
        <legend>Select options:</legend>
        <select name="option1">
          <option value="">Select option 1</option>
          <option value="option1value1">Option 1 Value 1</option>
          <option value="option1value2">Option 1 Value 2</option>
          <option value="option1value3">Option 1 Value 3</option>
        </select>
        <select name="option2">
          <option value="">Select option 2</option>
          <option value="option2value1">Option 2 Value 1</option>
          <option value="option2value2">Option 2 Value 2</option>
          <option value="option2value3">Option 2 Value 3</option>
        </select>
        <select name="option3">
          <option value="">Select option 3</option>
          <option value="option3value1">Option 3 Value 1</option>
          <option value="option3value2">Option 3 Value 2</option>
          <option value="option3value3">Option 3 Value 3</option>
        </select>
      </fieldset>
    </form>
  </div>
  <div class="generate-results">
    <h2>Results</h2>
    <p id="result"></p>
  </div>
</div>

<script>
  const option1 = document.querySelector('select[name="option1"]');
  const option2 = document.querySelector('select[name="option2"]');
  const option3 = document.querySelector('select[name="option3"]');
  const result = document.querySelector('#result');

  function updateResult() {
    const values = [option1.value, option2.value, option3.value];
    result.textContent = values.filter(value => value !== '').join(', ');
  }

  option1.addEventListener('change', updateResult);
  option2.addEventListener('change', updateResult);
  option3.addEventListener('change', updateResult);
</script>
