---
layout: post
title:  "Diametrics - ArchHacks Winner"
categories: [personal project]
tags: [hackathon, healthcare]
image:
  feature: Diametrics.png
comments: true
---
This project is a way to receive heath insights from diabetes data inspired by the Diabetes Hack category at ArchHacks. One of our teammates in the hackathon is a type 1 diabetic and had to adjust to managing it when diagnosed. An application like this simplifies visualizing the data and also indicates when the insulin to glucose levels are not within safe parameters.

<!--more-->

## What is it?

DiaMetrics takes the data from a diabetic's life and plots the glucose levels against time throughout the day. It lists only the past 24 hours worth of data as to only contain relevant information. Calculations are also done based on the food consumed, as the ratio of the carbohydrates and insulin are exponentially weighted through time in a moving average. This average weights relevant information more and depicts a proper insulin to glucose level ratio.

## How we Built it
The Highcharts library allowed us to create our dynamic graph. This was supported with a Django back end and an Angular 4 front end to set up the interactive website. The numpy Python library was used to create the algorithm that maintains a weighted insulin to glucose average. Amazon Web Services hosted everything and allowed us to flesh out the project.

## What we Learned

We learned about deployment and the Django REST framework, both of which we explored in our implementation. Some of us learned the fundamentals of JavaScript, while others gained experience using Angular 4. The numpy algorithm provided a different venture into data science, which was motivated by a publication on Exponentially Weighted Moving Average Control Charts (http://pubs.acs.org/doi/abs/10.1021/ie070589b) and how they are effective in detecting shifts in means. This will help forecast future observations and allow users to take preventative actions while allowing them to be easily aware of their average insulin to glucose levels and when this value steps outside of normal distributions. We thought about originally using machine learning in lieu of this, but numerical statistics are a proven way of detecting shifts and measuring any nonrandom patterns in data (as referenced in the paper above).

## What is Next 

We'd like to include much more interactivity in our project, such as being able to select time series for multiple days and cross referencing them over time to accrue a normal behavior pattern for their diabetes. Furthermore, gamifying the project to make kids interested in being in control of their diabetes is an issue that we hope to incorporate.

## How do I use it?

Visit the Github page for [Diametrics](https://github.com/kblicharski/diametrics).

Run
`npm install -g @angular/cli@latest`

Clone the repository
`git clone https://github.com/kblicharski/archhacks2017`

and then enter commands
```
cd website
npm install
ng serve
```

and then navigate to
`localhost:4200`
in your browser.
