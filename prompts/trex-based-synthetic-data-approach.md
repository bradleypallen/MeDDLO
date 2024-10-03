# Modified Approach: Generating Synthetic Data Using T-REx Dataset

## 1. Dataset Selection
Use the T-REx dataset as the primary source of facts and aligned text. T-REx contains Wikipedia abstracts aligned with Wikidata statements, providing a rich source of knowledge triples and corresponding natural language expressions.

## 2. Data Preprocessing
a) Extract relevant triples from T-REx that involve properties suitable for graded predicates. Focus on properties like:
   - Height (P2048)
   - Population (P1082)
   - Age (P3629)
   - Temperature (P2076)
   - Cost (P2284)

b) Identify the corresponding aligned text in the Wikipedia abstracts for these triples.

## 3. Categorization of Properties
Categorize the selected properties into appropriate graded predicate groups:
- Height → tall/short
- Population → populous/sparse
- Age → old/young
- Temperature → hot/cold
- Cost → expensive/cheap

## 4. Generate Positive Examples
Use the aligned text from T-REx as a basis for generating positive examples. Modify the original LLM prompt to work with this aligned text:

<antArtifact identifier="trex-positive-example-generation-prompt" type="text/markdown" title="Modified LLM Prompt for Generating Positive Examples from T-REx">
# Task: Generate Positive Examples for Metalinguistic Agreement Detection Using T-REx Data

Your task is to generate statements that agree with given facts from the T-REx dataset, using graded predicates. These examples will be used to evaluate an LLM's ability to detect agreement between statements and facts.

## Instructions:

1. You will be provided with a fact from T-REx and its corresponding aligned text.
2. Generate a new statement that agrees with this fact, phrasing it using graded predicates (e.g., tall, short, populous, sparse, old, young, hot, cold, expensive, cheap).
3. Ensure your statement is semantically consistent with the fact and the aligned text, but does not simply repeat them verbatim.
4. Vary your language and the degree of the graded predicate (e.g., "very tall", "somewhat expensive", "extremely old").
5. Sometimes include comparative statements when appropriate.
6. Occasionally introduce relevant context that supports the agreement.

## Example:

T-REx Fact: &lt;Mount Everest, height, 8848 meters&gt;
Aligned Text: "Mount Everest is Earth's highest mountain above sea level, located in the Mahalangur Himal sub-range of the Himalayas. The China–Nepal border runs across its summit point."
Generated statement: "Mount Everest is an extraordinarily tall mountain, towering above all others on Earth."

## Guidelines:

- Use natural, conversational language.
- Avoid directly stating numerical values from the fact.
- Ensure your statement would be generally agreed upon by most people familiar with the subject.
- If the fact involves a comparison, maintain that comparison in your generated statement.
- Feel free to add relevant context from the aligned text, but make sure it doesn't change the core meaning.

## Your output:

For each T-REx fact and aligned text provided, generate one statement that agrees with it, following the above instructions and example.
