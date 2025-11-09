November 5<sup>th</sup>, 2025<br>
**MPAD2003: Introductory Data Storytelling**<br>
**<ins>Erica Lee, Alex Overton, Angus Mclean</ins>**<br>
*Presented to Jean-Sébastien Marier*<br>

# Exploratory Data Analysis (EDA) & Pitch

 <!--Use one hashtag symbol (`#`) to create a level 1 heading like this one.

## Foreword

For this assignment, you must extract data from a dataset provided by the instructor. You must then clean and analyze the data, create exploratory charts/visualizations, and find a potential story idea. Your assignment must clearly detail your process. You are expected to write about 1500-2000 words, and to include several screen captures showing the different steps you went through. Your assignment must be written with the Markdown format and submitted on GitHub Classroom.

I have been assigning different versions of this project to my digital journalism and data storytelling students for a few years now. Its structure was inspired by the main sections/chapters of [*The Data Journalism Handbook*](https://datajournalism.com/read/handbook/one/). This version was further inspired by the [Key Capabilities in Data Science](https://extendedlearning.ubc.ca/programs/key-capabilities-data-science) program offered by the University of British Columbia (UBC).

**Here are some useful resources for this assignment:**

* [GitHub's *Basic writing and formatting syntax* page](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
* [The template repository for this assignment in case you delete something by mistake](https://github.com/jsmarier/jou4100_jou4500_mpad2003_project2_template)

Did you notice how to create a hyperlink? In Markdown, we put the clickable text between square brackets and the actual URL between parentheses.

And to create an unordered list, we simply put a star (`*`) before each item.-->

## Introduction
For this assignment, my team and I will clean and analyze Statistics Canada’s Long Form Census, specifically the Ward Data for the city of Ottawa, ON, from 2021. We will create visualizations and charts to help clearly communicate a narrative whose origins were found within the data.  

This data was collected as a sample, surveying only 25% of households in Ottawa. The data, available [online here](https://open.ottawa.ca/datasets/ottawa::2021-long-form-census-ward-data/explore), was most recently updated on October 19th, 2025 and was first published on November 29th, 2023. This version is subject to change should the Data be updated. [Here is the CSV file we used during our EDA](2021_Long_Form_Census_-_Ward_Data.csv). The data provides insight into the lives of Ottawans through many aspects of their lives, including the language(s) spoken at home.

Here is a map of the Wards of Ottawa, taken from [the City of Ottawa](https://ottawa.ca/en/city-hall/elections/ward-maps-and-school-board-zones#) to provide a visual reference to the data henceforth decribed.
![](Map_City_Wards.png)

Our process will be broken up into the following sections:
- **Getting Data**
- **Understanding Data**
- **Our Potential Story**
- **Conclusion**


## Getting Data

 <!--Use two hashtag symbols (`##`) to create a level 2 heading like this one.

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
This also shows how to create an ordered list. Simply put `1.` before each item. -->
To import this data into Google Sheets:
1. Go to Open Ottawa’s page for [this particular dataset](https://open.ottawa.ca/datasets/8f75667abca94de8a7d4c467c3bc6f81/explore)
2. Download the data; it is available as a CSV file.
3. Create a blank spreadsheet in Google Sheets.
4. Go to File > Import. Select the downloaded file before hitting “Import data”.
![](screenshot-after-import-to-google-sheets.png)<br>

[Here is a link to our Google Sheet](https://docs.google.com/spreadsheets/d/1Bm7OXJO5cfourgJ5xlKDuFZYEm1oy1jB5kEU_uD9vC4/edit?usp=sharing)

This data set is big, with a total of 2603 rows and 26 columns. Overall, the data looks reasonably clean, but that’s before any analysis has been conducted. We found a small error quickly in B24; the total of the values from the individual wards doesn’t match the total provided in B24.

Column A’s values contain a mix of different types of variables. There’s usually a nominal variable heading the variables below it. For example, A3’s value is “Total - Age groups of the population - 25% sample data”, and then A5:A28 contain specific ranges. Column B contains the data for the entire city, a total of all of the wards’ data. Column B contains a mix of discrete and continuous values. There are continuous values from B85:Z85, which represent the percentage of respondents’ income that is from their employment. There are also discrete values, such as those in B724:Z724, representing the number of people whose mother tongue is American Sign Language. Generally, as the wards move towards the downtown core, the rate of global non-response increases, peaking at 7.60% in the 12th Ward, Rideau-Vanier, a huge increase over the whole city, 3.10%.

We’d like to learn more about the Canadian Deaf community in Ottawa. We can see bubbles of small communities across the different wards that use American Sign Language (ASL), Langue des Signes Québécoise (LSQ) (referred to as “Quebec Sign Language” in the dataset) or Indigenous Sign Languages in their homes; as native Signers and as those who use them as an additional language. We would like to learn more about the history of the Deaf community of Ottawa. Our primary question is “Is participation in the Deaf community a contributing factor in choosing where to live as a Sign Language user?”

## Understanding Data

### VIMO Analysis

<!--Use three hashtag symbols (`###`) to create a level 3 heading like this one. Please follow this template when it comes to level 1 and level 2 headings. However, you can use level 3 headings as you see fit.-->

For our VIMO analysis, we’re looking specifically at rows 1407 - 1410 of the original data set. Overall, the totals appear to be inconsistent with the specific data. For example, when totalling C1407:Z14:07, which should represent all of the data for the city’s “total - Knowledge of languages for the population in private households,” the number differs from the total in B14:07 by 10. This isn’t a massive discrepancy, but it is especially troubling, given that this data was collected at a sample level and therefore could be exaggerating or exacerbating the scale of discrepancies that would be seen with a complete population survey.

![](total knowledge error image for VIMO.png)<br>

However, as this is government data which was collected for Canada’s 2021 Census, we have a high degree of confidence in its accuracy. The government of Canada notes that to ensure its accuracy via ensuring participation, it will contact “non‑respondent households at key times to remind them to participate in the census and persuade them to complete the questionnaire” (Statistics Canada, 2021). They also adapted their approach for collecting data due to safety concerns caused by the COVID-19 pandemic. They primarily opted for an online questionnaire, alongside other options for those who needed access to them, which showed “many advantages: it increases the number of online responses, a mode that facilitates the flow of questions and real-time response edits; and it reduces non-response, the need for costly follow-up, and the number of questionnaires to register and the amount of data to capture. In the end, it increases the quality of the census” (Statistics Canada, 2021). All of which support the accuracy of the data and help prevent missing, outlying or incorrect entries in the data published.

<!-- Support your claims by citing relevant sources. Please follow [APA guidelines for in-text citations](https://apastyle.apa.org/style-grammar-guidelines/citations).

**For example:**

As Cairo (2016) argues, a data visualization should be truthful... -->

### Cleaning Data

Before beginning our analysis, the dataset needed to be cleaned in order to make the data more consistent and easier to follow. There were several unnecessary rows, some extra whitespace, and lengthy text entries that needed to be adjusted and reorganized. I used Google Sheets to address these issues and followed the cleaning methods we learned during this course.

I began by reviewing the dataset and removing irrelevant data to focus only on the information related to sign language. To do this, I used the find tool (command + F) to search for every row that mentioned sign language and deleted all other entries. This reduced the dataset to only the relevant data, which made it much easier to analyze.

After deleting all unnecessary rows and columns, I used Google Sheets’ Data Clean Up Suggestions to remove extra whitespace from cells. This automatically applied the TRIM function to the relevant cells, ensuring that there were no trailing spaces that could cause issues in later analysis.

Next, I decided to transpose the data to make it easier to interpret. Originally, the dataset had wards listed across columns and sign languages listed across rows. To switch their positions, I used the TRANSPOSE function (=TRANSPOSE(A1:Y5)), which swaps rows and columns.

The names in the dataset were long, including the suffix “ - Ward”. To simplify them, I used the SPLIT function (=SPLIT(A2; “ - Ward”) to separate the text into two columns and then deleted the extra portion, leaving only the ward name.

Lastly, I froze the top row using View → Freeze → 1 Row so that the headers remained visible while scrolling through the dataset. While this step didn’t change much about the dataset, it improved readability and navigation during analysis.

Here is what the dataset looked like after being cleaned:

![](cleaned-data-screen-capture.png)<br>

### Exploratory Data Analysis (EDA)

I made a pivot table that shows the sum of all signers across each ward in Ottawa, along with the specific sum of just the ASL and QSL signers, in order to see which wards have the highest number of total signers, as well as compare the number of ASL and QSL signers there are in each ward. If certain wards stand out, that might suggest that the deaf community participation could indeed influence residential clustering.

![](signers-pivot-table-screen-capture.png)<br>
*Figure 2: This pivot table shows the sum of all signers across each ward in Ottawa*

After taking the pivot table and turning it into a column chart, it’s fairly easy to see how signers are distributed across wards in the city of Ottawa. The chart shows that signers are spread throughout the city, with totals ranging from 45 to 135 people per ward. The highest numbers appear in Alta-Vista, Knoxdale-Merivale, and Rideau-Vanier, while the lowest are in Capital and West Carleton-March. The data also shows that Ottawa is mainly ASL-dominant, with only 5 wards reporting QSL signers and many wards having small populations of users of other Sign Languages. 
 

![](signers-distribution-chart.png)<br>
*Figure 3: This exploratory chart shows how signers are distributed throughout Ottawa*

Through this analysis, I learned that signing populations are not evenly distributed across Ottawa and that language type (ASL vs. QSL vs. Indigenous or other Sign Languages) could potentially play a role in how communities are formed. I also learned that visual tools such as pivot tables and charts make it easier to spot patterns and think critically about what might cause them.

The potential story here is that certain wards might have stronger Deaf or signing communities, possibly because of access to community services, schools or networks that support sign language users. The fact that QSL is only present in 5 wards could suggest that there are localized French Deaf communities, while the overall dominance of ASL points to broader accessibility and use across the city.

For next steps, it would be useful to compare these totals to each ward’s overall population to see if the high counts actually represent larger Deaf communities or just larger ward populations. Calculating signers per capita could reveal stronger concentration patterns. It may also be worth exploring demographic or geographic factors, like proximity to schools for the Deaf or community centers, to understand why certain wards have higher totals.


## Potential Story

The potential story that we could tell with this data is that certain wards might have larger Deaf communities due to access to support structures, such as schools or community networks for the Deaf. In order to *tell* this story, we would likely need other resources such as maps of support centers for the Deaf, testimony from involved individuals, and possibly statistics from sources such as the city website. 

For testimony, we could interview members of the Deaf community who live in districts with a large number of Deaf people in them to see what they find appealing about the area, or conversely, we could interview in smaller communities to see what they feel is lacking. We could also interview people who work at support centers or schools for the Deaf in order to see what they feel they do to make the area attractive. We could also interview Denise DeShaw,  who used to be the head of the Ontario Association for the Deaf (OAD) and is currently the head of the ASL program at Carleton.

Many online resources can help provide more context to the story, such as news articles, studies, or city releases from the area. This additional context and data could help us flesh out, verify and add a personal touch to the story. This allows it to be clearer and more impactful. Some potential sources that could align with these criteria are:

- [An article about Ottawan Deaf advocacy for sign languages to be recognized as official Canadian languages in Ottawa before it was recognized under the Accessible Canada Act in 2019](https://capitalcurrent.ca/ottawas-deaf-community-calls-for-official-recognition-of-sign-language/)
- [An article about an event recognizing Ottawa’s Deaf community on Parliament Hill during International Week of Deaf People (IWDP)](https://charlatan.ca/ottawa-raises-deaf-flag/)
- [An article about opportunities in education for the Deaf in Ottawa](https://www.ocdsb.ca/programs-learning/special-education/special-education-elementary/elementary-special-education/deaf-hh)

## Conclusion

While completing this assignment, one aspect that we found challenging was that the data had a small error in it at the start, and was in need of cleaning. If the error had not been noticed and we had gone ahead with cleaning the data, it could have resulted in it getting lost and messing up the data and results, which would have been unfortunate for our analysis. Thankfully, it was found and rectified before the cleaning process, which also helped clarify the data. By trimming down on blank spaces, uneven rows and columns, and repetitive labelling, we were able to clean the data down to a concise spreadsheet that made it clearer to view the data pertinent to our goals.

An aspect of this assignment that we found rewarding was that once the data was cleared, some clear patterns emerged from the data, especially once it was visualized in charts and tables. This would make it easier to work towards answering our main question, as clear patterns and trends are easier to begin to understand when visualized, as well as aiding in identifying missing information.

One gap in my own knowledge that I have identified is that I do not really have any preexisting knowledge of the Deaf community in Ottawa, and I did not really know where to look first for supplementary materials for this assignment. I feel that I have rectified this somewhat, although I feel there is still a lot to learn. One thing that could have been done differently on this assignment is that we could have committed the project at more regular intervals, although I am unsure if this would have impacted the final result at all or not.

## References
Grieve, N. (2024, May 4). Convert rows to columns in Google Sheets[Video]. YouTube. https://www.youtube.com/watch?v=9kc0PUOuCJw 

Jean-Sébastien, M. (2021, October 9). Cleaning Data in Google Sheets[Video]. YouTube. https://youtu.be/U4yigiawIEU?si=UkYborn3k3y-Q3qo 

Jean-Sébastien, M. (2021, October 19). Using Pivot Tables in Google Sheets[Video]. YouTube. https://youtu.be/cCVl0h-9HmU?si=hLPD51qubB8fzC_x 

Statistics Canada. (2021). Coverage Technical Report, Census of Population, 2021: 4. Census data collection. Statcan.gc.ca; Government of Canada. https://www12.statcan.gc.ca/census-recensement/2021/ref/98-303/2021001/chap4-eng.cfm