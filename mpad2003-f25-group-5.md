**November 5, 2025**<br>
**Course Code & Course Name**<br>
**Student's First Name & Last Name**<br>
**Presented to Jean-Sébastien Marier**<br>

# Exploratory Data Analysis (EDA) & Pitch

Use one hashtag symbol (`#`) to create a level 1 heading like this one.

## Foreword

For this assignment, you must extract data from a dataset provided by the instructor. You must then clean and analyze the data, create exploratory charts/visualizations, and find a potential story idea. Your assignment must clearly detail your process. You are expected to write about 1500-2000 words, and to include several screen captures showing the different steps you went through. Your assignment must be written with the Markdown format and submitted on GitHub Classroom.

I have been assigning different versions of this project to my digital journalism and data storytelling students for a few years now. Its structure was inspired by the main sections/chapters of [*The Data Journalism Handbook*](https://datajournalism.com/read/handbook/one/). This version was further inspired by the [Key Capabilities in Data Science](https://extendedlearning.ubc.ca/programs/key-capabilities-data-science) program offered by the University of British Columbia (UBC).

**Here are some useful resources for this assignment:**

* [GitHub's *Basic writing and formatting syntax* page](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
* [The template repository for this assignment in case you delete something by mistake](https://github.com/jsmarier/jou4100_jou4500_mpad2003_project2_template)

Did you notice how to create a hyperlink? In Markdown, we put the clickable text between square brackets and the actual URL between parentheses.

And to create an unordered list, we simply put a star (`*`) before each item.

## 1. Introduction

Insert text here.

## 2. Getting Data

Use two hashtag symbols (`##`) to create a level 2 heading like this one.

To include a screen capture, use the sample code below. Your images should be saved in the same folder as your `.md` file.

![](import-screen-capture.png)<br>
*Figure 1: The "Import file" prompt on Google Sheets.*

**Here are examples of functions and lines of code put in grey boxes:**

1. If you name a function, put it between "angled" quotation marks like this: `IMPORTHTML`.
1. If you want to include the entire line of code, do the same thing, albeit with your entire code: `=IMPORTHTML("https://en.wikipedia.org/wiki/China"; "table", 5)`.
1. Alternatively, you can put your code in an independent box using the template below:

``` r
=IMPORTHTML("https://en.wikipedia.org/wiki/China"; "table", 5)
```
This also shows how to create an ordered list. Simply put `1.` before each item.

## 3. Understanding Data

### 3.1. VIMO Analysis

Use three hashtag symbols (`###`) to create a level 3 heading like this one. Please follow this template when it comes to level 1 and level 2 headings. However, you can use level 3 headings as you see fit.

Insert text here.

Support your claims by citing relevant sources. Please follow [APA guidelines for in-text citations](https://apastyle.apa.org/style-grammar-guidelines/citations).

**For example:**

As Cairo (2016) argues, a data visualization should be truthful...

### 3.2. Cleaning Data

Before beginning our analysis the dataset needed to be cleaned in order to make the data more consistent and easier to follow. There were several unnecessary rows, some extra whitespace, and lengthy text entries that needed to be adjusted and reorganized. I used Google Sheets to address these issues and followed cleaning methods learned during this course.

I began by reviewing the dataset and removing irrelevant data to focus only on the information related to sign language. To do this, I used the find tool (command + f) to search for every row that mentioned sign language and deleted all other entries. This reduced the dataset to only the relevant data which made it much easier to analyze.

After deleting all unnecessary rows and columns, I used Google Sheets Data Clean Up Suggestions to remove extra whitespace from cells. This automatically applied the TRIM function to the relevant cells, ensuring that there were no trailing spaces that could cause issues in later analysis.

Next, I decided to transpose the data to make it easier to interpret. Originally the dataset had wards listed across columns and sign languages listed across rows. To switch their positions, I used the TRANSPOSE function (=TRANSPOSE(A1:Y5)), which swaps rows and columns.

The names in the dataset were long, including the suffix “ - Ward”. To simplify them, I used the SPLIT function (=SPLIT(A2; “ - Ward”) to separate the text into two columns and then deleted the extra portion, leaving only the ward name.

Lastly, I froze the top row using View → Freeze → 1 Row so that the headers remained visible while scrolling through the dataset. While this step didn’t change much about the dataset, it improved readability and navigation during analysis.

Here is what the dataset looked like after being cleaned:

![](cleaned-data-screen-capture.png)<br>

### 3.3. Exploratory Data Analysis (EDA)

I made a pivot table that shows the sum of all signers across each ward in Ottawa, along with the sum of just the ASL and QSL signers, in order to see which wards have the highest number of total signers, as well as compare the amount of ASL and QSL signers there are in each ward. If certain wards stand out, that might suggest that the deaf community participation could indeed influence residential clustering.

![](signers-pivot-table-screen-capture.png)<br>
*Figure 2: This pivot table shows the sum of all signers across each ward in Ottawa*

After taking the pivot table and turning it into a column chart, it’s fairly easy to see how signers are distributed across wards in the city of Ottawa. The chart shows that signers are spread throughout the city, with totals ranging from 45 to 135 people per ward. The highest numbers appear in Alta-Vista, Knoxdale-Merivale, and Rideau-Vanier, while the lowest are in Capital and West Carleton-March. The data also shows that Ottawa is mainly ASL-dominant, with only 5 wards reporting QSL signers. 

![](signers-distribution-chart.png)<br>
*Figure 3: This exploratory chart shows how signers are distributed throughout Ottawa*

Through this analysis, I learned that signing populations are not evenly distributed across Ottawa and that language type (ASL vs. QSL) could potentially play a role in how communities are formed. I also learned that visual tools such as pivot tables and charts make it easier to spot patterns and think critically about what might cause them.

The potential story here is that certain wards might have stronger Deaf or signing communities, possibly because of access to community services, schools or networks that support sign language users. The fact that QSL is only present in 5 wards could suggest that there are localized french deaf communities, while the overall dominance of ASL points to broader accessibility and use across the city.

For next steps, it would be useful to compare these totals to each ward’s overall population to see if the high counts actually represent larger deaf communities or just larger ward populations. Calculation signers per capita could reveal stronger concentration patterns. It may also be worth exploring demographic or geographic factors, like proximity to schools for the Deaf or community centers, to understand why certain wards have higher totals.


## 4. Potential Story

Insert text here.

## 5. Conclusion

Insert text here.

## 6. References

Jean-Sébastien, M. (2021, October 9). Cleaning Data in Google Sheets[Video]. YouTube. https://youtu.be/U4yigiawIEU?si=UkYborn3k3y-Q3qo 

Grieve, N. (2024, May 4). Convert rows to columns in Google Sheets[Video]. YouTube. https://www.youtube.com/watch?v=9kc0PUOuCJw 

Jean-Sébastien, M. (2021, October 19). Using Pivot Tables in Google Sheets[Video]. YouTube. https://youtu.be/cCVl0h-9HmU?si=hLPD51qubB8fzC_x 




