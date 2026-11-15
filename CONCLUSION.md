# Lab 05 — Conclusion

<!--
Read this before you write.

This file is graded by your instructor, by hand, and it is worth 6 of the 15 points.

- Type it yourself. Do not use a chatbot, an AI assistant, an AI autocomplete or a "rewrite my
  text" tool for any part of it, not even for grammar. English that is plain and a little
  clumsy but yours is better than polished text that is not.
- Use your own numbers. Every number you quote must be one your own notebook printed. Copy
  the number exactly as it appeared. A number your notebook did not print is marked as wrong.
- Answer in your own words, about 80-200 words per question. A short answer that uses your
  numbers beats a long answer that could have been written by anyone.
- Delete these comment lines if you like. Keep the three headings and the last line.
-->

## 1. Which layer changed your results the most?

Give the numbers before -> after for that layer (correct / wrong / no answer, out of 20) and say
whether it changed what the agent *can do* or only what it *admits*. If no layer changed the
number of correct answers, say so and explain what the layers did change instead.

(write here)

| Config | Correct | Wrong | No answer |
|---|---:|---:|---:|
| bare | 15 | 5 | 4 | 
| + layer 1 | 15 | 9 | 0 |
| + layer 2 | 15 | 8 | 1 |
| + layer 3 | 10 | 4 | 10 |
layer 1 - the model started answering alias-questions but some of the answers turned out to be wrong
layer 2- practically didn't affect the result
one question went from wrong to no answer
layer 3 reduced the number of wrong answers but at the same time lost five correct answers because of the strict ANSWER format check
no one layer add + correct answer but it divided beetwin it 

## 2. One failure the full harness did not fix

Pick one question that the full harness (layer 3) still gets wrong or refuses. Give its id
(q01 ... q20). Open its trace in the notebook: at which step did it go wrong, and what did
the model do instead? Name one thing you would add to the harness, and what it would cost
(extra model calls, tokens, time, or a new way to fail).

(write here)

I choose q12, the first step was correct and the model called get_series(Pavlodar, avg_monthly_wage, 2020, 2025) and got all needed values
the mistake happened in the calculation step, instead of using the 2025 value it used the 2021 value and also reversed the formula, because of that it produced -11.2457% which is wrong
layer 3 did not catch this because all numbers came from tool outputs
the answer was grounded but not correct
one thing I would add is a simple check that verifies the years used in the calculation match the years from the question
the cost would be extra logic or one more model call which means more tokens and more time.


## 3. Workflow or agent for the monthly ranking?

Dala Insight wants to publish, every month, "which region is highest and which is lowest on one
indicator in one year". Would you ship the fixed workflow or the agent? Use the accuracy, the
number of model calls, the tokens and the time you measured in Part 1. Then say in one sentence
what kind of question would make you choose the other one.

(write here)

I would ship the workflow, t--,i and

I wrote this file myself, without any AI tool.
