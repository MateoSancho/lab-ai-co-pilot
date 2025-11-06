Prompt 1

Explain this JavaScript function in detail. Add comments as needed.

function mysteryOp(arr) {
  return arr.reduce((acc, val) => acc ^ val, 0);
}

Claude --->
// Performs cumulative XOR across array items
// reduce() loops through elements while maintaining the accumulator
// Starting from 0, it flips bits based on each value’s binary pattern

Chat GPT-->
// This function takes an array of numbers and returns the XOR (exclusive OR) of all its elements.
function mysteryOp(arr) {
  // The reduce() method combines array elements into a single value.
  // acc starts at 0, and we XOR it with each val in the array.
  return arr.reduce((acc, val) => acc ^ val, 0);
}

// Example:
// [2, 3, 2] -> 2 ^ 3 ^ 2 = 3 (since 2 XOR 2 = 0, and 0 XOR 3 = 3)

Gemini --->
// Returns XOR of all elements in arr
// Efficient for finding a unique element when all others appear twice


Prompt 2

Write a function that changes the text of an HTML element with id "status" when a button is clicked. Use vanilla JavaScript and follow accessibility best practices.

Claude --->
<button id="statusButton">Change Status</button>
<p id="status" aria-live="polite">Loading...</p>

<script>
document.querySelector("#statusButton").addEventListener("click", () => {
  document.querySelector("#status").textContent = "Status successfully changed.";
});
</script>

Chat GPT-->
<button id="updateBtn" aria-label="Update status">Update</button>
<p id="status">Waiting...</p>

<script>
document.getElementById("updateBtn").addEventListener("click", function() {
  const statusEl = document.getElementById("status");
  statusEl.textContent = "Status updated!";
});
</script>

Gemini --->
<button id="btn">Click</button>
<p id="status">Not clicked</p>

<script>
btn.onclick = () => status.innerText = "Clicked!";
</script>


Prompt 3

Refactor this function to make it readable and efficient. Add meaningful variable names and comments.

function r(a){let b=0;for(let i=0;i<a.length;i++){if(a[i]%2===0){b+=a[i]}}return b}

Claude --->
// Adds up even elements from an array
function addEvenElements(array) {
  let sum = 0;
  for (const element of array) {
    if (element % 2 === 0) sum += element;
  }
  return sum;
}

Chat GPT-->
// Returns the sum of all even numbers in an array
function sumEvenNumbers(numbers) {
  let total = 0;
  for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] % 2 === 0) {
      total += numbers[i];
    }
  }
  return total;
}

Gemini --->
function sumEven(a){
  return a.reduce((sum, n)=> n%2===0 ? sum+n : sum, 0);
}

AI Evaluation Table:
| AI Tool |Task| Clarity (1-5) | Accuracy (1-5) | Speed (1-5) | Notes |
|---------|---|---|---|---|--------------------------------|
| ChatGPT | 1 | 5 | 5 | 4 | Very clear with examples       |
| Claude  | 1 | 4 | 5 | 5 | Concise explanation            |
| Gemini  | 1 | 3 | 5 | 5 | Too brief, lacks detail        |
| ChatGPT | 2 | 5 | 5 | 4 | Good accessibility practices   |
| Claude  | 2 | 5 | 5 | 5 | Excellent aria-live usage      |
| Gemini  | 2 | 3 | 4 | 5 | Missing accessibility features |


My Pick:
Claude

Pros & Cons
ChatGPT
Pros: Very detailed explanations, includes practical examples, strong on accessibility

Cons: Can be slightly verbose, sometimes provides more information than needed

Claude
Pros: Excellent balance of clarity and conciseness, modern coding practices, strong accessibility focus

Cons: Occasionally too brief for complex concepts

Gemini
Pros: Very fast responses, functional programming approach

Cons: Often too brief, misses important details, weaker on accessibility

Task-by-Task Highlights
Task 1: ChatGPT provided the most thorough explanation with a practical example. Claude was concise but accurate. Gemini was too brief.

Task 2: Claude excelled with aria-live="polite" for dynamic content. ChatGPT used aria-label. Gemini missed accessibility entirely.

Task 3: Claude's modern for-of loop was elegant. ChatGPT's traditional approach was clear. Gemini's functional approach was clever but had poor variable naming.

Surprises & Bugs
Surprise: Claude's use of aria-live="polite" in Task 2 was an excellent accessibility practice I hadn't considered

Bug: Gemini's use of onclick and innerText in Task 2 represents outdated practices

Observation: ChatGPT consistently provides examples which aids learning

Final Thoughts
I would trust Claude in a real project because it consistently provides clean, modern, and accessible code with the right balance of detail. While ChatGPT gives more comprehensive explanations, Claude's responses are more practical for daily development work. Gemini, while fast, often misses important details that could lead to accessibility or maintenance issues.