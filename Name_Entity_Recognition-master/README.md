# Name Entity Recognition

Named-entity recognition (NER) (also known as entity extraction) is a sub-task of information extraction that seeks to locate and classify named entity mentions in unstructured text into pre-defined categories such as the person names, organizations, locations, medical codes, time expressions, quantities, monetary values, percentages, etc.



# Problem Description

Clinical studies often require detailed patients’ information documented in clinical narratives. Named Entity Recognition (NER) is a fundamental Natural Language Processing (NLP) task to extract entities of interest (e.g., disease names, medication names and lab tests) from clinical narratives, thus to support clinical and translational research. Clinical notes have been analyzed in greater detail to harness important information for clinical research and other healthcare operations, as they depict rich, detailed medical information.

For example, here is a sentence from a clinical report:

We compared the inter-day reproducibility of post-occlusive reactive hyperemia (PORH) assessed by single-point laser Doppler flowmetry (LDF) and laser speckle contrast analysis (LSCI).

In the sentence given, **reactive hyperemia (in bold) is the named entity with the type disease/indication.**


## Data Description

**The train file has the following structure:**

- id	Unique ---->ID for a token/word
- Doc_ID--------->Unique ID for a Document/Paragraph
- Sent_ID-------->Unique ID for a Sentence
- Word----------->Exact word/token
- tag (Target)------>Named Entity Tag


The target ‘tag’ follows the Inside-outside-beginning (IOB) tagging format. The IOB format (short for inside, outside, beginning) is a common tagging format for tagging tokens in named entity recognition. The target ‘tag’ has three kinds of tags


- **B-indications :** Beginning tag indicates that the token is the beginning of a disease entity (disease name in this case).
- **I-indications :** Inside tag indicates that the token is inside an entity.
- **O-indications** : Outside tag indicates that a token is outside a disease entity.


Therefore, any word which does not represent the disease name has to be classified as “O” tag. Similarly, the first word of disease name has to be classified as **“B-Indication” and following words of disease name as “I-Indication”**.

- [Dataset can be downloaded from here](https://www.kaggle.com/rsnayak/hackathon-disease-extraction-saving-lives-with-ai)
