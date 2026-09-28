---
name: interview-me
description: Interview the user one question at a time, down each branch of the decision tree, until you reach a shared understanding — before doing any work. Use when the user says "interview me", "let's scope this", "walk me through the decisions", or when a task has open design decisions that are the user's to make.
---

# Interview me

Interview me about every aspect of this until we reach a shared understanding.

Walk down each branch of the decision tree, resolving dependencies between decisions one-by-one.

## Rules

1. **For each question, provide your recommended answer.**
2. **Ask the questions one at a time, and make each question one decision.** Wait for feedback on
   each question before continuing. Several questions at once are bewildering, and so is one question
   that bundles several decisions.
3. **If a fact can be found by exploring the environment** (filesystem, tools, etc.), **look it up
   rather than asking me.** The decisions, though, are mine — put each one to me and wait for my answer.
4. **Do not act on it until I confirm we have reached a shared understanding.**
5. **Questions are not confirmations of decisions.**
6. **Do not use built-in "Ask user input" or "options cards display".** Ask in plain prose.
7. **Write facts and decisions to a file as we go.** Keep a living document: facts you looked up
   (with their source — `file:line`, command output), decisions I have made, and the questions still
   open. Update it after each answer rather than reconstructing it at the end.
8. **Before each question, explain the problem, then the context around it, then your recommended
   answer, in plain words.** In the conversation, refer to a decision by what it says, never by its
   number in the living document ("D7"). Nobody remembers what D7 was.
