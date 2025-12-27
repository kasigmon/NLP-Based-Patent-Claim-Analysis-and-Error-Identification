# Natural Language Processing-Based Patent Claim Analysis and Error Identification
*Kirk A. Sigmon, kirk.a.sigmon.th@dartmouth.edu*

This is ***experimental*** code used to evaluate the use of modern Natural Language Processing ("NLP") techniques, such as [SpaCy](https://spacy.io/), to process patent claims for purposes such as analysis and error identification.  Arguably, this is just a more modernized, slightly more experimental version of [ClaimMaster](https://www.patentclaimmaster.com/).  One advantage of this work is that it could be used to programmatically and quickly evaluate large swaths of claims for major issues, particularly with enough computational firepower.

***THIS SHOULD NOT BE USED FOR REAL LEGAL WORK.***  This is experimental only, and is not intended for "live" use.  It is not legal advice, and should not be construed as such.  It is largely programmed in my free time, and is full of limitations and errors. 

Current functionality:

* **Antecedent Basis Analysis** - Identifies Noun Phrases (NP) that have been introduced but not used, used but not introduced, or properly introduced and used.  This tends to suggest antecedent basis issues under 35 U.S.C. § 112.
* **Structural Analysis** - Uses [GraphViz](https://graphviz.org/) and SpaCy's transformers-based pipeline model ([en_core_web_trf](https://huggingface.co/spacy/en_core_web_trf)) to roughly graph different limitations of a claim.

Future functionality(?):
* **Embedding-based Comparisons** - Use of embedding techniques to programmatically compare claims (both within and without a single patent).  Currently, I'm slightly biased towards using [BGE](https://bge-model.com/).  This will likely be done in various dimensions:
  * Identifying possible support issues - that is, comparing weak or potentially nonexistent semantic coverage by comparing embeddings from a claim to embeddings from a specification.  This could also be used on the other hand (as a quick and dirty support search engine).
  * Identifying unique steps within lengthy claims - that is, highlighting limitations or clauses that stick out (for better or worse).
  * Identifying family and/or portfolio-level standouts/trends.  For example, a quick diagnostic tool for major continuation-level shifts.
