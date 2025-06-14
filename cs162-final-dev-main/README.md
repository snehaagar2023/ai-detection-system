# CS162 Final Project Dev Set

The format is .jsonl files containing human text under “human_text” and AI text under “machine_text.” The original data comes from the M4 dataset (Wang et al., 2024), so this dataset may not be used for training. 

We may use the same or different models for the final evaluation, and the test data may come from different sources. We will not disclose details about the models used to generate the AI test data to avoid solutions that overfit to these models. 

**Ethics Dev Set**

We provide three datasets for the ethical discussion: 
1. ```german_wikipedia.jsonl``` - derived from M4 dataset and focuses on german text. Same format as dev set. 
2. ```toefl.json``` - 91 essays written by non-native English speakers, .json file containing the essay in `document'. This data is from [this paper](https://arxiv.org/abs/2304.02819). 
3. ```hewlett.json``` - 88 essays written by native English speakers, .json file containing the essay in `document'. This data is from [this paper](https://arxiv.org/abs/2304.02819).
   
You can evaluate your models on these datasets and analyse why the performance is low or high with respect to different non-native English speakers' essays, native English speakers' essays and on multilingual data. 
