# Named Entity Recognition for the Disambiguation of Specific Numerals in Romanian

## Introduction
This paper presents a specialized extension to a robust hybrid system designed for the transcription and identification of compound and special numeral entities in Romanian [1]. While the base system effectively processes complex numerical structures and standardized codes (e.g., IBAN, VIN, CNP) through a pipeline of Named Entity Recognition (NER), Large Language Models (LLMs), and deterministic rules, it encounters persistent ambiguity with "un" and "o" forms. The objective of this work is to disambiguate these specific numerals when they quantify human entities (e.g., "un bărbat" — one man) as opposed to their role as indefinite articles (e.g., "un accident" — an accident). By addressing this edge case, we aim to enhance the semantic precision of the existing numeral-processing framework.

## Methods and Results
The methodology focuses on integrating a high-precision disambiguation layer into the established NER-driven pipeline. We fine-tune a pre-trained bert-base-romanian-cased-v1 transformer model specifically for token classification of these ambiguous forms [2]. The model is trained on a manually curated dataset of Romanian text, annotated using the BIO (Beginning-Inside-Outside) tagging scheme, where numerals referring to persons are explicitly labeled. This specialized module acts as a granular filter before the reconstruction stage, ensuring that only true numerals are passed to the word-to-number conversion components.
To rigorously evaluate the system's robustness, testing was conducted on a custom dataset engineered with linguistic traps. This included interjections (e.g., "O!" — oh!), personified inanimate entities (e.g., "un robot utilitar" — a utility robot), and ordinal structures (e.g., "un al treilea" — a third one). The fine-tuning process was conducted over 5 training epochs, showing a consistent performance increase that stabilized at a final F1-Score of 95.24% and an Accuracy of 99.54%.
Furthermore, qualitative analyses highlight the model's exceptional capability to accurately delimit complex noun phrases (e.g., "un purtător de cuvânt") and successfully filter out ordinal numbers that do not begin with "un" or "o".

## Conclusions
The integration of this disambiguation module represents a critical refinement of the parent hybrid architecture, addressing a nuanced linguistic challenge unique to morphologically rich languages like Romanian. The study demonstrates that specialized NER models fine-tuned on task-specific datasets are essential for handling ambiguities in numeral classification. This work contributes to the overall robustness of Romanian numeral processing, particularly in contexts where accurate person-centric quantification is mandatory.

## Acknowledgement
This research is supervised by LTC. Assoc. Prof. Eng. Ștefan-Adrian Toma.

## References
[1] Vasile Dragoș-Mitruț, Ștefania Ștefănescu and Ștefan-Adrian Toma. “Transcription and Identification of Compound and Special Numeral Entities Using Artificial Intelligence and Rule-Based Methods.” The 13th Conference on Speech Technology and Human-Computer Dialogue (SPED 2025), Cluj-Napoca, Romania, 19-22 Oct. 2025.
[2] Stefan Dumitrescu, Andrei-Marius Avram, and Sampo Pyysalo. “The birth of Romanian BERT” in Findings of the Association for Computational Linguistics: EMNLP 2020, pages 4324–4328 [Online]. Association for Computational Linguistics. Available: https://aclanthology.org/2020.findings-emnlp.387
