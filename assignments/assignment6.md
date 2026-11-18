# Assignment 6: Automating charts with Codex and Datawrapper

**Due Dec. 9**

## Option to count this as two assignments

You may choose to have Assignment 6 **count as two assignments in your assignment average**. The same percentage grade will be entered twice. Because it gives Assignment 6 more weight, this option could raise or lower your assignment average.

The same requirements and grading criteria apply; no additional work is required.

**You must email me BEFORE the Assignment 6 deadline if you want to use this option.** State that you want Assignment 6 to count as two assignments. Requests received after the deadline will not qualify. 

# The assignment

Use Codex to build a repeatable Python script (`.py` file) that uses the [sample D.C. Council bill data](../class12/bill_categories_sample.csv) to programatically create three Datawrapper charts: one for housing, education and business. Each chart should show the number of bills in that category at each legislative status.

**You will direct Codex through prompts. You are not expected to write Python code yourself, and you will not use a Jupyter notebook.** You are responsible for explaining what the script does, checking its results and making sound chart design decisions.

## 1. Read the guide and set up your Datawrapper API

In [First Automated Chart](https://palewi.re/docs/first-automated-chart/index.html), by Ben Welsh and Sergio Sanchez Zavala, read **[“What is an API?”](https://palewi.re/docs/first-automated-chart/index.html#what-is-an-api)** and follow **[“Create a Datawrapper API key”](https://palewi.re/docs/first-automated-chart/index.html#create-a-datawrapper-api-key)** to set up your access. We will not cover API key setup in class.

The rest of the guide is a reference for you and Codex. Give Codex the guide's link and ask it to adapt the chart creation and styling instructions to this assignment. **You do not need to follow the notebook instructions or type the example code. Do not install Jupyter or create an `.ipynb` file for this assignment.**

You will use the sample CSV I provide, rather than the guide's Baltimore arrest data. In the Housing, Education and Business columns, `true` means the bill matched that category's keywords; `false` means it did not.

You can also ask Codex to explain unfamiliar directions or help troubleshoot errors. Give it the guide's link and describe that you are using a Python script, not a notebook.

**Treat your API key like a password. Do not paste it into a Codex conversation or include it in your Python code.** Ask Codex to make the script request the key through a terminal input prompt when it runs, with the characters visible as you enter them. Paste the key at that prompt and press Enter. The script should use the key without saving it in a file. 

## 2. Sketch the process before asking Codex to build it

Draw a first version of a flowchart showing how you think the tool should work. Pen and paper may be easiest, or you can write it in markdown. Use it to organize your prompts. After the script works, revise the drawing to show what it actually does; submit that final version.

You can use this as an example of a data pipeline flow chart: [Example from class](https://docs.google.com/presentation/d/1pRNz2Cs_GFpj2xfWj5CrgLSEoHEJb1CI4RZGPlm6B_s/edit?slide=id.h7cb6f1eb4cb49f2e_1_35#slide=id.h7cb6f1eb4cb49f2e_1_35)

The flowchart needs to explain more than “data → API → charts.” At minimum, show:

* The input file and what information it includes.
* How it decides which bills belong in each chart.
* How individual bill records become counts by status.
* Which steps repeat for housing, education and business. Indicate that these are repeating sections, rather than drawing three unrelated workflows.
* What data and design settings get sent to Datawrapper, and where the API key is used. 

## 3. Build the script through Codex prompts

**Prompt Codex to generate a Python script (`py` file) that takes the sample data and makes 3 charts (1 for housing, 1 for education, 1 for business) via the Datawrapper API.** The charts should show the number of bills by status, like our in-class example.

Because Codex will not inherently have a deep working knowledge of the Datawrapper API, you may need to prompt it with the URLs for the [First Automated Chart](https://palewi.re/docs/first-automated-chart/index.html) guide or the [Datawrapper developer documentation](https://www.datawrapper.de/developer/getting-started) as context.

Your script must read the supplied CSV and use the Datawrapper API to create all three charts when it runs. It should calculate the chart values from the input file, rather than have the answers typed into the code.

Ask Codex to make your script runnable with `uv`. This is so it will run the same on my computer as your computer, regardless of our Python setups.

The `.py` file should be in the same folder as the input data CSV. Ask Codex to make the script read the supplied CSV from that folder without requiring a file path specific to your computer.

### Run the finished script yourself in the Terminal app.

Instructions to do this:

1. Open Terminal. Use the `cd` command to move into the folder containing your script and data. (You can ask Codex for help with this.)
    * For example, if your `.py` script and CSV are in `Desktop/comm260/`, type `cd ~/Desktop/comm260` into Terminal, then hit Enter.
2. Type `uv run assignment6.py` then hit "return" to run the Python file. If you get an error that `uv` is not installed, ask Codex to help you install it on your computer first (we will go over this part in class).
3. When the script asks for your API key, paste it at the terminal input prompt and press Enter.

Read the terminal output and inspect the charts in Datawrapper. If the program fails, share the error message with Codex and ask it to explain and fix the problem. If you want to make changes to the charts, tell Codex what those are. Run the revised script from Terminal again.

I should be able to put your script and the supplied CSV in the same folder, run `uv run assignment6.py` from that folder in the terminal, and enter my own API key at the prompt. If this does not work, you will not receive full points for this assignment.

### Chart requirements

Use a consistent status order across the three charts:

1. New
2. Under Council Review
3. Enacted
4. Under Congressional Review
5. Official Law

Do not show **withdrawn** bills. Include statuses with zero bills so readers can compare the charts consistently. 

**You must use Codex to change the script and apply your design changes through the API.** This is so the submitted script reproduces the design of the charts you submit. Changes made only by clicking in the Datawrapper editor will not accomplish that.

Each chart must have:

* An appropriate chart type and readable labels.
* A clear headline and a description of what is being counted.
* Your name in the byline and a source credit to D.C. Council.
* A note explaining that the categories can overlap. 

Write your own headlines, descriptions and notes, then ask Codex to apply them via the Python script. 

Your script can create new charts each time you run it or update the existing charts. Tell Codex which you want when creating the Python script.

Once you're happy with your charts, ask Codex to publish your charts so the links can be viewed without signing into your account. Keep the published versions consistent with your final script -- you should not be making changes to the charts in the web browser.

## 4. Check the chart counts

Use Excel or another independent method to verify one status count in each category against the supplied CSV: one housing count, one education count and one business count. In your Markdown submission, identify the category and status you checked, explain how you checked it (ie pivot tables, filtering, etc.) and report both your independent count and the chart's count. (If you identify any errors through this check, fix them before submitting the assignment.)

# What to turn in

Upload these to your assignment repository:

* **`assignment6.py`: Your final working Python script.** It should request the API key at runtime.
* **`assignment6.md`:** Include links to all three published Datawrapper charts; your flow chart (can be an image or markdown); your three independent count checks from section 4.

## AI use

Use AI to help build and troubleshoot the script and apply your chart design decisions. 

The following should represent your own writing and thought process: **Do not use AI to write your headlines, descriptions, notes or other chart text; create your flowchart; or write your explanations of the independent count checks.** For the chart text you write, you should provide it to Codex and ask it to apply that text to the Datawrapper charts via the Python script.

**My disclosure:** I used Codex to write and edit portions of this assignment. 

# How this will be graded

I will attempt to run your script with my API key; look at the charts it creates to see if they match yours; and check if the data in the charts is accurate. I will grade via the following rubric:

* **Script:** Reads the supplied data, calculates the correct counts and creates all three charts through the API with the submitted design. Runs with `uv run assignment6.py` from the folder containing the script and supplied CSV, and requests the API key as directed.
* **Chart design, labeling and accuracy:** Readable charts with appropriate headlines, descriptions, sources, notes and consistent comparisons. Your markdown file includes three independent count checks with correct results and a clear explanation of the checking method.
* **Flowchart and reasoning:** Accurately explains the input, category selection, counting, repetition, data and design settings sent to Datawrapper, and use of the API key, with clear evidence that you understand the process.
