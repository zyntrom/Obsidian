# ✅ **AI FOR DEBUGGING AND LEARNING

## 1. Purpose of This Lesson

This section teaches how to use AI as a debugging tool, not just as a code generator. Developers spend a significant amount of time fixing errors, and AI can help analyze errors, explain stack traces, and clarify underlying concepts.

---

## 2. Debugging Workflow with AI

### Step 1: Reproduce the Bug

Before fixing a bug, always reproduce it.

- Clone the project:
    `git clone https://github.com/kalviumcommunity/blogify-bug-hunt cd blogify-bug-hunt`
- Install dependencies:
    `npm install`
- Run the project:
    `npm start`
- Observe the error and stack trace.

### Why this step matters:

- Ensures the bug is real, consistent, and reproducible.
- Gives you the exact error message needed for diagnosis.

---

## 3. Using AI to Diagnose Errors

### Technique 1: "Explain This Error" Prompt

When you see an error in the terminal:

1. Copy the full error message and stack trace.
2. Open GitHub Copilot Chat.
3. Ask:
    
    `I'm getting this error when I run npm start in my Node.js project. Can you explain what this error means and suggest a fix?  [paste the full error]`

AI will:

- Break down the error message.
- Identify the cause.
- Point to the file and line number.
- Suggest the correct fix.

This avoids guessing and speeds up debugging.

---

## 4. Deepening Understanding After Fixing the Bug

Debugging is not only about fixing; it is also about understanding why the bug happened.

### Technique 2: Ask for the Concept Behind the Error

Once the error is fixed, ask:

`What is the difference between module.exports and exports in Node.js?  Give me an example of the correct way and incorrect way to export a single function.`

This helps convert a one-time fix into permanent understanding.

---

## 5. Common Bug Cause in This Exercise

The intentional bug in the project is related to:

### **Incorrect usage of CommonJS exports**

Specifically:

- Confusion between `module.exports` and `exports`
- Assignment patterns that break their reference relationship

Example of the mistake:

```jsp
exports = function() { ... }
```

This does **not** export anything because it breaks the reference to `module.exports`.

Correct pattern:

```js
module.exports = function() { ... }
```

---

## 6. Practical Activity Summary

### You must complete:

1. Clone the repository.
2. Install dependencies with `npm install`.
3. Reproduce the error by running `npm start`.
4. Use Copilot’s “Explain this error” prompt to diagnose.
5. Apply the fix.
6. Confirm that the server now runs successfully.
7. Ask a follow-up question to learn the underlying concept.
8. (Optional) Create a branch, commit your fix, and open a Pull Request.

This teaches real-world debugging habits.

---

## 7. Key Concepts (Exam Points)

- AI tools can interpret error messages and stack traces.
- Debugging always begins with reproducing the error.
- Copilot Chat can explain errors, suggest fixes, and clarify concepts.
- `module.exports` and `exports` behave differently when exporting single values.
- A faulty export strategy can break module functionality.
- Creating a separate branch and Pull Request is standard professional workflow.

---

## 8. Effective AI Debugging Prompts

These are the exact types of prompts you need to know for the quiz.

### 1. Explain the error

`Explain this error and tell me how to fix it: [paste error]`

### 2. What caused this error?

`Why did this error happen, and how can I prevent similar issues?`

### 3. Fix this code

`Here is the file causing the issue.   Fix the code and explain the solution.`

### 4. Compare concepts

`What is the difference between module.exports and exports? Give examples.`

### 5. Verify fix

`Does this fix correctly solve the problem and follow best practices?`