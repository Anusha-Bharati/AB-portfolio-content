
# Why I Stopped Sending Every Paper to the LLM

While building BuzzSieve, one of the first problems I ran into was surprisingly simple: **there were too many papers**.

Searching Europe PMC could return a large number of results, but not every result was useful. Some papers only loosely matched the search. Others were older, less relevant, or simply did not contain enough information to justify sending them to an LLM.

My first instinct was to let the AI decide which papers were useful. Technically, that works. But it also means paying for model calls on papers that could have been filtered out much earlier.

That felt wasteful.

## Filtering before AI

I changed the pipeline so that BuzzSieve does more work before OpenAI is involved.

The system now looks at things such as the title, abstract, publication date and evidence-related signals to calculate a score for each paper.

The basic flow became:

**Search → rank → filter → use AI**

instead of:

**Search → send everything to AI → hope for the best**

This also made the system easier to reason about. I could inspect why a paper ranked highly without relying on an LLM to explain every decision.

## Relevance was harder than expected

Keyword matching worked initially, but it quickly became obvious that it was too simplistic.

A paper might contain the search term several times without actually being very useful. Another paper might use slightly different wording while being much more relevant.

I ended up treating ranking as its own problem rather than just a small filtering step.

I also wanted searches to stay flexible. BuzzSieve should work with whatever someone searches for rather than depending on a fixed list of predefined topics.

That meant the ranking logic needed to work directly against the user's query and the paper's metadata.

## Keeping AI where it is useful

The main lesson for me was that adding an LLM does not mean every part of the system needs an LLM.

For BuzzSieve, normal code is better for things like filtering, scoring and removing obviously weak candidates.

The LLM becomes much more useful later, when the system needs to understand and restructure the selected research into things like key findings, limitations and readable summaries.

It also keeps the cost much more predictable.

There is still plenty to improve in the ranking system, especially around recognising papers with strong quantitative results and distinguishing genuinely useful evidence from papers that only look relevant from their wording.

But separating **selection** from **generation** made the overall system much cleaner.
