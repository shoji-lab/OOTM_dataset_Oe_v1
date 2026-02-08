# OOTM_dataset_Oe_v1
This repository provides **OOTM (Outfit of The Moment) datasets** for training LLM to generate women's outfit description for specific situation in Japanese society.

The datasets were constructed as part of an ongoing academic research project on Fashion Information Access Technologies.
Further technical details will be released in a future publication.

## Overview
This repository distributes a paired dataset consisting of textual situations and outfit descriptions that match those situations. The dataset was constructed using a generative annotation approach, where a Vision-Language Model (VLM) was used to reverse-engineer situational context from fashion images. This dataset is designed to bridge the semantic gap between abstract real-world scenarios and concrete, high-fidelity fashion prompts for generative AI.

## Dataset Detail
This dataset was constructed by captioning outfit images from social media using a Vision-Language Model (VLM). For each outfit image, the VLM generates a detailed description of the attire and specifically verbalizes a situation where the outfit could be worn.

### Methodology

VLM Annotator: Google's Gemma 3 (gemma-3 27b) was used for generating both descriptions and situations.

Situation Components: Each situation is structured based on six elements: season, weather, location, activity, mood_theme, and companion.

The companion element may be null in cases where the situation does not involve others.

Text Generation: These elements were mapped to the following natural language template:

"An outfit for {activity} at {location} in {season}. The weather is {weather}. Aiming for a {mood_theme} look. Going with {companion}." 

The distributed CSV file provides these situations in their final natural language format, already converted from the raw components.

## Repository Structure
```
├── README.md           <- Project overview and dataset documentation
└── csv/
    ├── train_open.csv  <- Training set (7,746 pairs) 
    ├── val_open.csv    <- Validation set (968 pairs) 
    └── test_open.csv   <- Test set (968 pairs)
```

## Maintainer
Yuma Oe  
Shoji Laboratory, Shizuoka University
