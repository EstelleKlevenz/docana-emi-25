
## Project Report Template

> This repository serves as a template for your project reports as part of the Document Analysis lecture. To set up your project report as a webpage using GitHub Pages, simply follow the steps outlined in the next chapter.
>
>**Some Organizational Details:** Get creative with your project ideas! Just make sure they relate to Natural Language Processing and incorporate this specified dataset: [Link to data](https://huggingface.co/datasets/webis/tldr-17), [Link to paper](https://aclanthology.org/W17-4508.pdf). Submissions should be made in teams of 2-3 students. Each team is expected to create a blog-style project website, using GitHub Pages, to present their findings. Additionally, teams will deliver a lightning talk during the final lecture to discuss their project. Add all your code, such as Python scripts and Jupyter notebooks, to the `code` folder. Use markdown files for your project report. [Here](https://docs.gitlab.com/ee/user/markdown.html) you can read about how to format Markdown documents. 
>
>Have fun working on your project! 🥳

## Setup The Report Template

Follow this steps to set up your project report:

1. **Fork the Repository:** Begin by creating a copy of this repository for your own use. Click the `Fork` button at the top right corner of this page to do this.

2. **Configure GitHub Pages:** Navigate to `Settings` -> `Pages` in your newly forked repository. Under the `Branch` section, change from `None` to `master` and then click `Save`.

3. **Customize Configuration:** Modify the `_config.yml` file within your repository to personalize your site. Update the `title:` to reflect the title of your project and adjust the `description:` to provide a brief summary.

4. **Start Writing:** Start writing your report by modifying the `README.md`. You can also add new Markdown files for additional pages by modifying the `_config.yml` file. Use the standard [GitHub Markdown syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) for formatting. 

5. **Access Your Site:** Return to `Settings` -> `Pages` in your repository to find the URL to your live site. It typically takes a few minutes for GitHub Pages to build and publish your site after updates. The URL to access your live site follows this schema: `https://<<username>>.github.io/<<repository_name>>/`

***

# Project Title

_Group members: Nina Geyer, Estelle Klevenz, Liane Strauch_

## Introduction

_Start off by setting the stage for your project. Give a brief overview of relevant studies or work that have tackled similar issues. Then, clearly describe the main question or problem your project is designed to solve._

How do you say it?
Recent studies in the realm of the political sciences have shown a shift in the rethoric of politicians. They propose that the current dissemination of misinformation in political discourse is linked to an "alternative understanding of truth and honesty that emphasizes invocation of subjective belief at the expense of reliance on evidence" [Source-2]. This can be seen and measured through the language that politicians use.
As social media is cited as a key medium for spreading misinformation [Source-2], it is interesting to have a look, not only *wwat* kind of information is spread, but also *how?*.

### Evidence minus Intuition (EMI)

To answer that question we employ the EMI-Score. The Evidence-minus-Intuition measure was created in the context of US congressional speeches and the communication of politicians. It aims to capture how much of their language is "evidence-based" opposed to "intuition-based" to give insight into their approach to honesty and truthfulness [Source-1]. "Evidence-based" reasoning apporaches truth "by relying on evidence, facts, data and other elements of external reality" [Source-1] whereas the "intuition-based" approach relies "on feelings, instincts, personal values and other elements drawn mainly from a person’s internal experiences." in its conception of truth [Source-1]. 
The EMI is not concerned with the actual truth value of the content it is applied on but only considers the rhetoric. Therefore, we cannot infer anything about the actual quality of posts. But we assume that the concept can be transferred from political speech to the diverse content of Reddit forums - the social-media data to be analyzed -  and can be employed to gain insight about the present language.

Our research quest is to show that the EMI can be applied to the domain of social-media and to find out how language is used in different subreddits.

### Hypotheses

The data employed are Reddit posts from different subreddits, subforums on the platform. We expect some to have more evidence based language and other to rely more on intuition in how contents are discussed.

### Roadmap

After preprocessing we calculated the EMI score for subreddits, posts and individual words. To do this we followed the approach of the authors of the EMI score, as described in their paper from 2024 [Source-1]. The results were visually explored in histograms, wordclouds and PCA.

To validate our findings and test them for their robustness we conducted several "experiments" changing different settings of the approach. As a first experiment we compared the EMI scores for the long-posts with those of the corresponding summaries. Secondly we followed the process described by the authors and constructed and applied our own dictionary and thus a vocabulary definition of evidence resp. intuition based on the language used in the reddit forums. Lastly we experimented with a different embedding / latent representation by applying BERT instead of the word2vec algorithm/method (XX) to the long posts.

## Dataset

_Provide a short description of the dataset used in your project. Focus on highlighting the aspects that are particularly relevant to your work._

The dataset contains Reddit subreddit posts containing "TL;DR" from 2006 to 2016. "TL;DR" is short for "too long, didn't read" and indicates that a summary to a given post is given (either written by the author of the post or someone in the comments). The posts can be submissions or comments but only human produced, as bot-posts were filtered out. The original dataset contains 3,848,330 posts of 29'651 subreddits. For each posts the dataset has infromation on the author, the text body (raw and normalized), content, summary, subreddit and subreddit_id.

The dataset was originally intended to train summary-prediciton but it is suitable for our task as well as working with "TL;DR" posts ensures a certain length of the posts which helps with consistent quality of the computed EMI scores and relativizes the influence of single words. 
The fact that bot posts were filtered is also important, as our analysis focuses on the language of humans in specific contexts.

To make the dataload manageable we filtered for the subreddits that contain more than 10'000 posts. We then did a manual selection of subreddits we expected to show either strong evidence-based language or intuition-based language. After an initial inspection we eliminated those, whose mean value of the EMI was closest to zero.

16 subreddits remained in our selection, which meant 615392 posts to analyze. The subreddits are: XX

Analysis happened mostly on the content column and the summary, grouped by subreddit.

## Methods

### Setup 


_Outline the tools, software, and hardware environment, along with configurations used for conducting your experiments. Be sure to document the Python version and other dependencies clearly. Provide step-by-step instructions on how to recreate your environment, ensuring anyone can replicate your setup with ease:_

```bash
conda create --name myenv python=<version>
conda activate myenv
```

_Include a `requirements.txt` file in your project repository. This file should list all the Python libraries and their versions needed to run the project. Provide instructions on how to install these dependencies using pip, for example:_

```bash
pip install -r requirements.txt
```

### Experiments

_Report how you conducted the experiments. We suggest including detailed explanations of the preprocessing steps and model training in your project. For the preprocessing, describe  data cleaning, normalization, or transformation steps you applied to prepare the dataset, along with the reasons for choosing these methods. In the section on model training, explain the methodologies and algorithms you used, detail the parameter settings and training protocols, and describe any measures taken to ensure the validity of the models._

A) main analysis
XX SAMPLING - explain choice and expectations?
PREPROCESS
- tokenize
- lowercase
- punctuation removal
- stopword removal
- stemming
EMI
- word2vec
- evidence and intuition vector
- cosine similarity
- EMI score
    - z-stand for bin of post len
B) extensions
motivation: change orientation (dict), change on what and change how

1. comparison on post level: long vs summary
motivation:
clean sample summaries
train w2v
map wo batch
bin

2. different dictionary
- use preprocessed sample
- inspect original dictionaries
    - word counts
- use words with count >1000 as new seeds
- remove some manually
    find & true for ev
    wrong for int
    add article & argument
- use fasttext embeddings to expand seed words
    - cc.en.300.bin
    - cosine similarity above 0.75
- clean expanded sets from mistakes & smae word 
- combine original with expansion
- get colex viw web interface 
- remove intersection btw ev & in
- remove those that are not associated with the concepts

train w2v for emi with new dict
compute cosine sim
compute scores
map & bin

3. different model (BERT)
motivation:
C) Evaluation
- hstogram over all
- histograms for subreddits
- wordclouds with top toekns
- barplot emi scores
- PCA
    - subreddit vector representation
    - PCA on posts
    



## Results and Discussion

_Present the findings from your experiments, supported by visual or statistical evidence. Discuss how these results address your main research question._

## Conclusion

_Summarize the major outcomes of your project, reflect on the research findings, and clearly state the conclusions you've drawn from the study._

### main analysis
### long vs short
### dictionary
### BERT

## Contributions

| Team Member      | Contributions                                             |
|------------------|-----------------------------------------------------------|
| Nina Geyer       | main word2vec preprocessing & analysis, visualizations    |
| Estelle Klevenz  | dictionary experiments, webpage                           |
| Liane Strauch    | model experiments (BERT), theory, slides                  |

## References

_Include a list of academic and professional sources you cited in your report, using an appropriate citation format to ensure clarity and proper attribution._

Computational analysis of US congressional speeches reveals a shift from evidence to intuition (EMI-paper) [Source-1]

From alternative conceptions of honesty to alternative facts in communications by US politicians [Source-2]