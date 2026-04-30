# Note on AI Use

---

AI LLMs were used throughout the project to supplement analysis, primarily to speed up coding and reaffirm statistical coherency (i.e. reviewing which tests to use), but most personally helpful in providing more professional aesthetics to visualisations and webpages. Prior to undertaking the project, Claude.ai was prompted with the instructions to make a 'plan of action', essentially listing an order of what actions/visualisations ought to be in each stage. AI usage by each stage was as follows.

---

### Notebook 01 (Data Cleaning)

In the initial stages of the project, the first use of AI was of Claude.ai to carry out a preliminary summary of data trends, with the large dataset downloaded input into the LLM with the prompt of 'summarise any trends in the dataset of South America attached'. From this point the intensive/extensive dynamic became clear, and coding began. The primary assistant used for this was Google Colab's Gemini Assistant tool, used to code:
- tagging state and non-state actor labels
- tagging 'others' and 'NaN' actor labels
- finding nulls missed, i.e. removing 'no reported deaths' events from events tagged as fatal
- fixing errors in code for parameter checks

Additionally, Claude.ai assisted in identifying which columns were redundant for analysis (done with two prompts identifying columns that repeated others and columns with insufficient data, i.e. too many nulls or the same output for all events). The automatic Google Search Gemini summary was also used various times in understanding logical progression of code and reviewing the applicability of actions in class demonstrations to this project.

---

### Notebook 02 (Exploratory Analysis)

The primary use in this dataset was for the writing of code, with Gemini Assistant used to code:
- producing summary statistics
- bar-and-line chart code
- line chart comparison code
- histogram code

Given the larger amounts of code required for data visualisations, the assistant not only sped up analysis, but avoided issues of human error that needed to be fixed by AI in the first notebook. The only other usage of AI at this stage was use of Claude.ai to work out which type of visualisation was best for the data at hand, i.e prompting 'what type of graphs would best visualise fatality distribution of number of events'.

---

### Notebook 03 (Main Analysis)

Claude.ai was utilised at the beginning of this analysis to identify the logical order of code, prompted with the two prior notebooks to 'give me a logical progression of visualisations demonstrating the intensive/extensive dynamic'. This informed the structure of code, giving generalised bullet points on the direction code should take (e.g. form a ratio of state to non-state fatalities) although some cells were swapped around for personal preference on report progression. Otherwise, Gemini Assistant was again used for large code cells, with charts coded by the assistant and then adjusted aesthetically by the author. The 'explain code' function of the Assistant was also particularly useful in increasing personal understanding of how the AI was going about coding visualisations, allowing the spotting of errors (e.g. the original plotting of every year's lethality ratio, rather than just spike years). Gemini also fixed initial errors in the layout of the heatmap.

With this notebook being the main analysis, the finished notebook was then run through Claude.ai to double check for errors and/or missed analytical opportunity. From this action, the LLM identified A) the need for a Mann-Whitney U Test to confirm statistical significance (with the Gemini Search summary detailing what the test is and its uses), and B) the need for a markdown of summary sentences covering findings across the notebooks. Claude automatically produced these sentences, although they were adapted by the author to be less vague and repetitive than the LLM generated.

---

### Python Script (for HTML Report)

Claude.ai was used to first produce a base structure of code - a code template was generated for the report, with placeholders for analysis based on the assignment instructions input earlier as well as on the notebooks input earlier. This response also produced the idea of Plotly interactive graphs, which were input below notebook figures and charts with the Gemini Assistant coding tool. A second prompt was run to ask for a few different visual styles for the report, with the one picked based off ACLED-style aesthetics, but fitting with the existing blue-red colour scheme of notebook graphs. Claude then regenerated the placeholder code to include the design code, which was subsequently copied across to Colab and written out with full analysis from the author.

Gemini Assistant's 'explain code' function was also used prior to locally downloading the .py to identify any outstanding formatting errors (without changing them before the author could check, as the 'transform code' option does), as well as explaining the process of locally running the file into a HTML page.


Beyond the above listed, the only other use of AI was to produce a template for formatting of the README file, with placeholder tabs produced in the same way as the Python Script, and then replaced with the author's writing after pasting into the repository. Otherwise, all markdown cells and written analysis are independently written by the author, and the initial scope and analytical direction of the data downloaded (South America and focus on state violence) was organically thought of.
