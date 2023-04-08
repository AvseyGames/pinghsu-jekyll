---

layout: post

title: Private policy

---

Select options from the dropdowns below:

| **Option 1** | **Option 2** | **Option 3** |
| ------------ | ------------ | ------------ |
| Select option | Select option | Select option |
| Value 1      | Value 2      | Value 3      |
| Value 4      | Value 5      | Value 6      |
| Value 7      | Value 8      | Value 9      |

Selected options: <span id="selected-options"></span>

<script>
  // Get the select elements
  const option1 = document.querySelector('select[name="option1"]');
  const option2 = document.querySelector('select[name="option2"]');
  const option3 = document.querySelector('select[name="option3"]');

  // Get the span element for displaying selected options
  const selectedOptions = document.querySelector('#selected-options');

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
  }
</script>
