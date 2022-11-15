# Designing Data Products - Final Project

This project aims to analyze the likelihood of a Congress Bill to be passed given a set of variables.

![Screen Shot 2022-11-13 at 1 30 24 AM](https://user-images.githubusercontent.com/6238480/201509044-ea9ce453-6db1-4a4d-96ce-b736c525d0d7.png)

Understanding the increasingly important process of forming regulations and laws in the country, we decided to explore the possibility in determining the likelihood of a proposed bill in being passed by the House. This exercise can be useful for lobbyists, corporations in formulating political strategies, or even the general public during voting periods.

Data cleaning process - [Link](https://github.com/brianmulyadi/Designing-Data-Products/blob/main/dataset.ipynb)
Data analysis process - [Link](https://github.com/brianmulyadi/Designing-Data-Products/blob/main/pass_bill.ipynb)

### Problem Statement

```To discover relevant factors that can help to predict the likelihood of a Bill being passed in the House```

Dataset used in this exercise comes from [ProPublica](https://projects.propublica.org/api-docs/congress-api/)

*Member* -
Details of Congresspeople in the House in each session with supporting information on leanings, gender, time served on the House

*Bills* -
Details on the bills originating in the House in each session with supporting information on policy areas, sponsor, cosponsors, date of introduction, outcome of bill etc.

**Feature Vectors**

- Policy area
- Is the bill introduced by a Congressperson from the majority house?
- Number of cosponsors
- % of cosponsors from the majority house
- Is the sponsor in a leadership role?
- Political leaning of the sponsor [dwNominate](https://en.wikipedia.org/wiki/NOMINATE_(scaling_method)) Seniority of the sponsor
- % of votes against the party (sponsor)

Using the different models and optimization methods, we produced the following result:

![Screen Shot 2022-11-13 at 1 31 02 AM](https://user-images.githubusercontent.com/6238480/201509275-12844e9b-4244-4e8e-b64b-3465baa00832.png)

### Main Findings

By observing the best model, we can draw several key insights as follows:
- Higher polarization leads to a higher success/fail rate of passing a bill
- Number of cosponsors in majority help in passing a bill
- Certain policy areas have higher likelihood of being passed (i.e. National Security, Emergency Management, etc.)
 
### Use cases

*Law Firms and Clients* -
Consider a world where law firms are able to reach out to their clients and alert them that a bill is more likely to pass and explain how it would impact their business.

*Corporations & Lobbyists* -
Our model has the ability to recreate how companies interact with Washington, helping them make decisions about investing efforts in the political process.

*Societal Impact* -
Citizens will have the ability to stay informed about important bills impacting their personal lives like health and employment related bills. Political outcomes can be volatile and impact financial markets. Using our model, the prediction can promote stability.

### Productionization

![Screen Shot 2022-11-13 at 1 31 49 AM](https://user-images.githubusercontent.com/6238480/201509396-95748b52-d500-428f-ada6-d7abccdfb3d9.png)

One of the potential output of this model is to create a website that allows users to predict the outcome of a bill by entering some variables.

Steps:
1. Pick the Policy Area of your bill
2. Enter how many Republican Co-Sponsors you have for your bill
3. Enter how many Democrats Co-Sponsors you have for your bill
4. Enter who is Sponsoring your bill

Value propositions:
- **Hold your representative accountable** - The tool can be used by citizens to understand the voting patterns of their representatives.
- **Calculate the probability of a new bill getting passed** - This can be used by Policy Analysts and Lawmaker advisors to predict how their bill will be voted upon by the House.
- **Predict the voting behavior of a member** - The tool can also predict how different parameters impact that member - so changing those parameters can persuade the member to change their voting behaviour.

### Further improvements

Include features that consider the prior voting record of all members of the Congress which might influence their vote on the current bill

Consider public sentiment which could influence their local Congressperson's
opinion and vote

Dive a little deeper by running textual analysis on the bill text to identify patterns and key drivers like funding etc.

Consider macroeconomic factors like inflation, unemployment etc.
