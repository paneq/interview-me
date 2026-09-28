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
9. **Before putting a design choice to me, check whether the codebase already settled it.** An
   established mechanism for the same problem, such as a shared helper, a convention, or the pattern
   the neighbouring code uses, is a fact, not an open decision. Follow it and tell me which one it
   is. Ask only when nothing covers the case, or when you think the established way is wrong, and
   then say why.
10. **When a proposal needs a workaround, find the root cause before recommending it.** If a design
    only works by special-casing, such as a second field, a flag, or reading from two places, ask why
    the thing forcing it exists and whether changing that is simpler. When the proper fix is large,
    say so, and let me decide whether it belongs in this ticket or its own.
11. **Don't ask about trivial things. Fix them and tell me.** A typo, a wrong line number, a wording
    slip or a formatting fix in the living document isn't a decision.

## Presenting context

Pick the smallest view that makes the point, and put it next to the short text it supports.

- **Say where every symbol lives.** Never a bare method, type or field name: give its package or
  crate, its file, and the layer it belongs to. Stay on one layer per explanation, and present an
  API question in API terms, not as UI behavior.
- **Show code with its surroundings, never a single line.** Quote the enclosing function or struct,
  or enough lines to show what the line sits inside, or summarize the block as pseudo-code with the
  key line marked. Show the whole block when leaving parts out would hide ownership or order.
- **Draw how things flow** as a call tree, each node with its location and layer:

  ```text
  submitForm              web/src/forms/submit.ts      UI
    createSession         api/src/sessions/create.rs   API
      persistPrompt       api/src/db/prompts.rs        database
  ```

  Use a sequence diagram (text, or Mermaid where it renders) when several parties exchange messages.
- **Mark what changes with `+` / `-`** on the tree, struct or schema that exists today, so the
  present and the proposal read side by side.
- **Give the smallest concrete example** of the problem: the input that triggers it and what comes out.
- **Say what kind of problem it is:** broken behavior, a missing test, a design smell, a cost.
- **Use the codebase's words and mine.** Never introduce a term of your own without defining it.
- **Keep prose short.** When I say I'm lost, don't add more prose: show the one thing I asked about,
  with its location and surroundings.
