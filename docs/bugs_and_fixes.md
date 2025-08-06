# Bugs and Fixes – Custom NER with spaCy

During the internship, I trained a custom spaCy NER model on a hand-annotated dataset of code-mixed English–Indian (Telugu, Tamil) sentences. This section documents a key bug I encountered and how I resolved it.

---

## Issue: "Span indices exceed the length of the doc"

When attempting to train the NER model, spaCy raised the following error:
ValueError: [E103] Trying to set entities with start and end indices that exceed the length of the Doc

This occurred because:
- The annotated character spans did not align with the token boundaries spaCy generated
- Some entities were annotated with off-by-one or extra whitespace due to manual annotation

---

## Fix: Adjusting Span Indices to Match spaCy Tokenization

To resolve this:
1. I parsed each sentence with spaCy’s tokenizer and verified whether the annotated spans matched a valid token span
2. For invalid spans, I either:
   - Trimmed whitespace
   - Re-tokenized and recalculated character offsets using spaCy’s `doc.char_span()`
3. Any annotation that failed validation was logged and skipped to avoid crashing training

---

## Outcome

After cleaning the annotation indices:
- The NER model trained successfully
- Token alignment errors were eliminated
- I better understood spaCy’s strict entity span handling and tokenizer behavior

---

## Notes

- This bug is common when converting datasets from CSV to `.spacy` format
- It highlights the importance of validating annotations against the tokenizer before training
