**Overview**

This corpus is a curated, sentence-level dataset for evaluating social and intersectional bias in NLP systems across compounding identity dimensions and contexts. It pairs intersectional sentences that encode real-world stereotypes or structural barriers with neutral controls to support both qualitative audits and quantitative benchmarking. The corpus is suitable for probing classification and generation behaviors, and for computing association-style bias metrics.



**Provenance and Literature Grounding**

Sentence examples and category selections were ideated from prior research to ensure alignment with established sociological and intersectional scholarship:



Safiya Umoja Noble (2018), Algorithms of Oppression.



Joy Buolamwini (2024), Unmasking AI.



Derous et al. (2019) on gender bias and hiring.



Purdie-Vaughns \& Eibach (2008) on intersectional invisibility.



Turner et al. (2018) on detecting stereotypes and social bias.



These sources guided the definition of intersections, domains, and the narrative patterns represented in the sentences.



**Data Fields**

Class: Intersectional category label (e.g., “Race + Region + Tech-Ethics”, “Gender + Race + Public-Health”, “Neutral”).



Sentence: A single sentence reflecting a stereotype/systemic pattern (for non-neutral classes) or a domain-relevant neutral statement (for baseline).



Optional metrics (if included in a given release): CEAT, I-WEAT, I-SEAT, IIBS. These columns are designed for sentence-level bias scoring and may be present in extended exports or appended after analysis runs.



Note: Depending on the specific CSV distribution, numeric metric columns may require light cleaning (e.g., smart quotes, trailing spaces in header names) to parse reliably.



**Category Schema**

The corpus represents intersections spanning identity dimensions and application contexts. Representative classes include:



Tech-Ethics: Race + Region + Tech-Ethics; Gender + Class + Tech-Ethics.



Public-Health: Gender + Race + Public-Health; Appearance + Region + Public-Health; Age + Region + Public-Health; Race + Disability + Public-Health.



Career \& Wealth: Class + Age + Career-Wealth; Region + Gender + Career-Wealth; Gender + Age + Career-Wealth.



Education Access: Disability + Region + Education-Access; Culture/Tradition + Gender + Education-Access; Class + Culture/Tradition + Education-Access.



Workplace Dynamics: Culture/Tradition + Age + Workplace; Appearance + Class + Workplace; Age + Appearance + Workplace; Race + Culture/Tradition + Workplace.



Additional intersections: Appearance + Gender + Ethnicity; Ethnicity + Age + Tech-Ethics; Region + Ethnicity + Tech-Ethics; Disability + Race + Career-Wealth.



Neutral: Domain-relevant neutral controls.





**Usage**

Model evaluation: Probe for disparate toxicity, sentiment, refusal/acceptance, likelihood, or continuation patterns across intersectional classes vs. neutral.



Metric computation: Populate CEAT/I-WEAT/I-SEAT/IIBS and report per-class and macro aggregate statistics, including confidence intervals and effect sizes.



Qualitative review: Pair metrics with expert annotations assessing harmfulness, stereotyping intensity, and context fidelity; use dependency relations to inspect how models handle demographic markers.



**Reproducibility**

Record exact toolchain: tokenizer/preprocessor settings, RoBERTa checkpoint name and version, SpaCy model/version, and random seeds.



Scripted pipeline: Provide scripts/notebooks for preprocessing, embedding generation, dependency parsing, demographic marker extraction, and bias metric computation.



Versioning: Publish dataset hashes and a class-count manifest per release to detect drift; log metric configurations and attribute/target word sets for CEAT/WEAT/SEAT experiments.



Ethical Considerations and Risk Mitigation

Purpose and scope: The dataset intentionally contains stereotype-referencing text solely for measurement, auditing, and mitigation research. It should not be used to generate or reinforce stereotypes in end-user applications.



Sensitive content handling: Implement content warnings; avoid broad public display of sensitive examples outside research contexts; provide reviewer guidance and support resources.



Data anonymization: Sentences are curated and not tied to identifiable individuals; ensure any future augmentations preserve this standard.



Responsible release: Consider a research license limiting use to auditing, fairness testing, and education. Include a non-endorsement statement clarifying that these sentences are for bias detection, not endorsement.



Access control: Offer a public “light” subset and gated access to the full sensitive set via request and Terms of Use. Track who accesses full sets for accountability.



Reproducibility of findings: Pin tool versions and seeds; release scripts and attribute/target lexicons; publish per-sentence IDs/hashes so results can be independently reproduced.



Ongoing monitoring: Invite feedback and issue reports; run periodic audits comparing intersectional slices vs. neutral baselines to track improvements; revise or retire problematic items.



**Known Limitations**

Class size variability: Some classes may have smaller sample sizes than others, affecting metric stability. Use bootstrapping or hierarchical modeling where appropriate.



Parsing/formatting robustness: Smart quotes or decorative separators in some CSV exports can interfere with automated parsing. Normalize quotes and trim header whitespace (e.g., “I-SEAT ” → “I-SEAT”) before analysis.



Domain and language scope: The dataset focuses on English-language, text-only examples with specific domains; generalization to other languages, modalities, or contexts requires care.



**Methodology for Intersectional Class Selection**

This section summarizes the formal methodology that guided the class design.



Conceptual framework and literature review: Following Kimberlé Crenshaw’s intersectionality framework, a targeted review across sociology, critical race studies, gender studies, and disability studies was conducted. Candidate intersections were required to demonstrate multidimensionality (two or more identity axes) and empirical support (documented evidence of stereotypes or structural barriers in professional, educational, or public-health domains).



Preliminary class inventory: An initial pool of 50 dyadic and triadic combinations (e.g., Gender \& Race; Race \& Disability \& Public-Health) was drafted and evaluated for scholarly salience and representational balance (including both majority and marginalized configurations).



Expert panel validation: A panel of five domain experts (two sociologists, one linguist, one public-policy researcher, one disability studies scholar) reviewed the list to confirm theoretical coherence, surface under-researched intersections (e.g., Class + Age + Career), and prioritize by relevance and impact.



Final selection and domains: The final set focused on 21 classes organized into thematic domains:



Tech Ethics: Race + Region + Tech-Ethics; Gender + Class + Tech-Ethics.



Public Health: Gender + Race + Public-Health; Appearance + Region + Public-Health.



Career \& Wealth: Class + Age + Career-Wealth; Region + Gender + Career-Wealth.



Education Access: Disability + Region + Education-Access; Culture/Tradition + Gender + Education-Access.



Workplace Dynamics: Culture/Tradition + Age + Workplace; Appearance + Class + Workplace.



Corpus construction: For each class, five sentences were drafted to represent common narratives or stereotypes with length control (target 15–25 words), neutral framing where possible to isolate class effects, and a balanced distribution across classes and neutral controls.



