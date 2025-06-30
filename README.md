
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
Recent studies in the realm of the political sciences have shown a shift 


A lot is going on on Reddit.
In numerous subreddits, almost everything is discussed: People look for advice on life choices, shopping suggestions, are eager to understand something, learn something, rant about a thing or look to exchange experiences or discuss a topic.
You can make Reddit a source for just about anything. And it is used that way! In a survey conducted 2024 by the Pew Research Center, around a third of the platform's users that participated stated that they regularly use Reddit as a source of information [FOOTNOTE-1].
People use the various forums that Reddit offers in its subreddits as a source of information...but what is the quality of this information?

### Evidence minus Intuition (EMI)

To answer that question we employ the EMI-Score. The Evidence-minus-Intuition measure was created in the context of US congressional speeches and the communication of politicians. It aims to capture how much of their language is "evidence-based" opposed to "intuition-based" to give insight into their approach to honesty and truthfulness [FOOTNOTE-2]. "Evidence-based" reasoning apporaches truth "by relying on evidence, facts, data and other elements of external reality" [FOOTNOTE-4] whereas the "intuition-based" approach relies "on feelings, instincts, personal values and other elements drawn mainly from a person’s internal experiences." in its conception of truth [FOOTNOTE-5]. 
The EMI is not concerned with the actual truth value of the content it is applied on but only considers the rhetoric. Therefore, we cannot infer anything about the actual quality of posts. assume that the concept can be transferred from political speech to the diverse content of Reddit forums without complications.

- topics and discussions on reddit seperated through subreddits. super diverse - interesting to see how the language is different for different subreddits

### Roadmap

- dataset with content from different subreddits
- EMI score (how to)
    - dictionary
    - word2vec
- visualizations
    - wordclouds
    - PCA
1. different dictionary
2. different model (BERT)
2. comparison on post level: long vs summary

## Dataset

_Provide a short description of the dataset used in your project. Focus on highlighting the aspects that are particularly relevant to your work._

different subreddits
- TLDR
	- nur datensatz mit langen posts, identifiziert durch TLDR
	- nur posts, keine thread-responses
- datensatz aus paper zu summary training

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

## Results and Discussion

_Present the findings from your experiments, supported by visual or statistical evidence. Discuss how these results address your main research question._

## Conclusion

_Summarize the major outcomes of your project, reflect on the research findings, and clearly state the conclusions you've drawn from the study._

## Contributions

| Team Member      | Contributions                                             |
|------------------|-----------------------------------------------------------|
| Nina Geyer       | main word2vec preprocessing & analysis, visualizations    |
| Estelle Klevenz  | webpage, dictionary experiments                           |
| Liane Strauch    | slides, model experimetns (BERT)                          |

## References

_Include a list of academic and professional sources you cited in your report, using an appropriate citation format to ensure clarity and proper attribution._

https://www.pewresearch.org/journalism/fact-sheet/social-media-and-news-fact-sheet/ [FOOTNOTE-1]

Computational analysis of US congressional speeches reveals a shift from evidence to intuition (EMI-paper) [Source-1]

From alternative conceptions of honesty to alternative facts in communications by US politicians [Source-2]

https://dictionary.cambridge.org/de/worterbuch/englisch/information [FOOTNOTE-6]