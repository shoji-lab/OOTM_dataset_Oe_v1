# OOTM_dataset_Oe_v1
This repository provides **OOTM (Outfit of The Moment) datasets** for training LLM to generate women's outfit description for specific situation in Japanese society.

The datasets were constructed as part of an ongoing academic research project on Fashion Information Access Technologies.
Further technical details will be released in a future publication.

## Overview
This repository distributes a paired dataset consisting of textual situations and outfit descriptions that match those situations. The dataset was constructed using a generative annotation approach, where a Vision-Language Model (VLM) was used to reverse-engineer situational context from fashion images. This dataset is designed to bridge the semantic gap between abstract real-world scenarios and concrete, high-fidelity fashion prompts for generative AI.

## Dataset Detail
This dataset was constructed by captioning outfit images from social media using a Vision-Language Model (VLM). For each outfit image, the VLM generates a detailed description of the attire and specifically verbalizes a situation where the outfit could be worn.

### Methodology

- **VLM Annotator**: Google's Gemma 3 (gemma-3 27b) was used for generating both descriptions and situations.

- **Situation Components**: Each situation is structured based on six elements: season, weather, location, activity, mood_theme, and companion.

    - The companion element may be null in cases where the situation does not involve others.

- **Text Generation**: These elements were mapped to the following natural language template:

"An outfit for {activity} at {location} in {season}. The weather is {weather}. Aiming for a {mood_theme} look. Going with {companion}." 

- The distributed CSV file provides these situations in their final natural language format, already converted from the raw components.

### Structure
Each CSV file contains the following columns:
- **ID**: A unique identifier for each record.
- **caption**: A detailed description of the outfit suitable for the given situation.
- **situation**: The specific situational context generated (annotated) by the VLM.

## Repository Structure
```
├── README.md           <- Project overview and dataset documentation
└── csv/
    ├── train_open.csv  <- Training set (7,746 pairs) 
    ├── val_open.csv    <- Validation set (968 pairs) 
    └── test_open.csv   <- Test set (968 pairs)
```

## Why "v1"?
This dataset represents our initial effort to verbalize outfits that match specific real-world situations. We designated this as "v1" because we plan to continuously iterate on the methodology and release improved versions in the future.

### Future Work
For future releases, we aim to:

- Incorporate Expert Annotations: Enhance the reliability of situation-coordinate pairings through professional fashion expertise.

- Increase Dataset Diversity: Expand the collection to include a broader variety of fashion styles, demographics, and highly specific or unconventional situations.

- Refine Data Quality: Implement manual filtering processes to ensure higher semantic consistency between situations and coordinate descriptions.

## License
This dataset is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License](https://creativecommons.org/licenses/by-nc/4.0/). 

**Usage Note**:
* **Academic Use**: You are free to use this dataset for research purposes, provided that you cite our original paper(to appear).
* **Disclaimer**: This dataset is derived from publicly available data on WEAR for research purposes. We do not own the rights to the original fashion styles or trends depicted in the descriptions.

## Maintainer
Yuma Oe  
Shoji Laboratory, Shizuoka University
Web: [https://kodhrt.github.io/](https://kodhrt.github.io/){:target="_blank"}

## Citation
```
@inproceedings{Oe2026asymmetric,
  title={Asymmetric Pipeline for Dataset Construction and Situation-aware Generative Outfit Retrieval Leveraging Differences in Task Difficulty},
  author={Yuma Oe, Katsumi Tanaka, Yoshiyuki Shoji},
  booktitle={Proceedings of the 16th ACM International Conference on Multimedia Retrieval},
  year={2026}
}
```
