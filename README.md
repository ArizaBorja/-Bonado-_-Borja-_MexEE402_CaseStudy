# MexEE 402: Data Preprocessing Case Study

MexEE Elective 2: Data Science and Machine Learning
Batangas State University, Alangilan Campus
1st Semester, AY 2026-2027

## Members

| Name | Student Number | Section |
|---|---|---|
| Bonado, Lance Exequiel | 23-07326 | MEXE-4102 |
| Borja, Ariza Mae | 23-09405 | MEXE-4102|

## Notebook links

| Chapter | Member 1 and Member2 | 
|---|---|
| Ch1_2_3 | [link](https://colab.research.google.com/drive/1bSbDPa-42N8aKf8HrlIZ6h0mt-D5fOas?usp=sharing) | 
| Ch4 | [link](https://colab.research.google.com/drive/1mOd8t9PrOxiI4VBW41erXWWq4vpptUFn?usp=sharing) |
| Ch5 | [link](https://colab.research.google.com/drive/1Quv1GaV8TllQ2OSIIZoA-Ze_uTJlf-Zm?usp=sharing) | 
| Ch6 | [link](https://colab.research.google.com/drive/1y-CJ3HR6GvyNx2FS-_xkPQ3p_8QzTNbg?usp=sharing) | 
| Ch7 | [link](https://colab.research.google.com/drive/1BPjOLsQVnV-jEhDgyhi-Jj8RFLM-RVGy?usp=sharing) | 
| Ch8 | [link](https://colab.research.google.com/drive/1uP0FrHuPT0wdTK9tfVFxnYdqqWUbrZ4R?usp=sharing) | 
| Ch9 | [link](https://colab.research.google.com/drive/1hAUbiuy2FDV0yht5Cvp1ZoK6z70tsm7v?usp=sharing) | 

## What we learned

 **Chapter 1_2_3** 

The first chapter taught us about a lot of things, first is about the csv file. It is a little bit hard to figure out on our end but it surprises us that a single website holds different and hundreds of datasets. Second is the concept of data processing, this chapter helps us to create a foundation on what data processing does and how important it is in machine learning. It also taught us that not all the data can be kept, those that don't contribute are needed to be removed to avoid inconsistencies and inaccurate results. 

**Chapter 4**

In this chapter, we realized that raw data can be transformed into more useful information through feature engineering. What surprised us in this chapter is how the representation of a data can be changed from numerical to categorical and make it much more useful for machine learning. Through this chapter we learned that data can be represented in different ways and make it much more useful than before. 

**Chapter 5**

In this chapter, we get a much better grip of what scaling is and how important it is for numerical values that have very different numerical ranges. At first, we thought that even though the datasets have different numerical values it is fine as long as we use proper codes and address. However, we realized that it does not work that way and got a full understanding of what really was the appropriate approach when one data has a very different numerical range than the other to make sure that both data will be able to contribute more fairly. 

**Chapter 6**

In this chapter, we learned more about outliers and how important it is to identify unusual values in a dataset. At first, we thought that an unusual value could simply be ignored, but we realized that it can affect the results and give inaccurate information. What surprised me in this chapter is that there are different ways to identify outliers, such as using the Z-score and IQR, and they do not always give the same result.

**Chapter 7**

In this chapter, we learned about feature selection and how important it is to choose only the features that can actually contribute to the data. Before this chapter, we thought that using more features would always give better results, but we realized that unnecessary features can make the model less effective.

**Chapter 8**

In this chapter, it made us realize how important it is to adjust model settings and balance your dataset so the machine doesn't just guess the most common answer every time. We also learned how to upload datasets into the code, which was useful because it showed us how the dataset can be directly used for processing instead of just looking at the data separately. 

**Chapter 9**

In this chapter, We learned that preprocessing data is like an assembly line where the order of operations and data types matter completely. It surprised us because of how changing numerical data into categories, such as different age groups, can make the information easier to understand and compare.


## Errors we found

### For Chapter 6

The code runs without error, but it fails to detect the value 100 as an outlier because the Z-score cutoff is set too high (> 3). Because 100 inflates both the average and standard deviation of a small dataset, its Z-score only reaches ~2.62, leaving the outlier list empty. This creates a contradiction since the text claims 100 was detected. Lowering the threshold to > 2 or > 2.5 fixes the issue, while the IQR method below works as expected.


### For Chapter 7

The code runs without crashing, but it runs into a issue because your dataset only has 7 rows. When you tell it to split the data into 5 folds, some validation groups end up with only 1 row. Scikit-learn can't calculate scores like R2 on a single row, which triggers metric warnings. 


### For Chapter 9

Converting Age into text labels like Child breaks the numerical pipeline, as it expects numbers to calculate medians and scale values. Applying this age discretization after preprocessing alters the original dataset while leaving one-hot encoded columns in the output array, which incorrectly shifts column index 2 from Age to a Pclass variable during plotting. Finally, filling missing Pclass values with the text string 'missing' creates a type mismatch with its numeric data.



## Note on AI tools

We used Gemini as an AI tool to help us check for errors in the code for each chapter. We used the prompt, “Act as an experienced programmer and carefully check the code below for syntax errors, logic errors, and incorrect commands or variables. Explain each error simply. If there are none, simply say that the code is correct. Give your answer in only one paragraph.” We also used Gemini and ChatGPT to help us understand the questions and improve our answers by explaining what the questions were asking and helping us organize our ideas. We did not use the AI to replace our understanding of the code or questions; we used it as a guide to identify errors, understand the lessons, and refine our answers.

## References

McKinney, W. (2021). Python for Data Analysis, 3rd ed. O'Reilly.
VanderPlas, J. Python Data Science Handbook.
Any other page or article you used.
