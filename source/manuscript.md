---
title: "Pandoc manuscript starter kit"
author:
- Author One
- Author Two

date: \today{}

fontsize: 12pt
geometry: "left=3.2cm,right=2cm,top=2cm,bottom=2cm"
numbersections: true
header-includes:
- \usepackage{setspace}
- \doublespacing
- \usepackage{fancyhdr}
- \fancyhead[RO, RE]{Fancy Header \thepage}
- \cfoot{}
- \pagestyle{fancy}
- \renewcommand{\headrulewidth}{0pt}
- \usepackage{times}
- \raggedright

bibliography: [library.bib]
csl: "../styles/american-geophysical-union.csl"
---

# Introduction

Test citation @McMillan2017

Equation @eq:description, 
$$
y = mx + b
$$ {#eq:description}

# Methods

  Right     Left     Center     Default
-------     ------ ----------   -------
     12     12        12            12
    123     123       123          123
      1     1          1             1

Table:  Demonstration of simple table syntax.

# Implications and Discussion

# Timetable

![The project's timetable is organized by its major parts (Part I, II and III, above). Black squares mark completed tasks. EGU: European Geosciences Union conference (April). AGU: American Geophysical Union conference (December). F17, W18, etc.: fall, winter, summer semesters](figs/gantt.pdf){#fig:gantt}

# References

\small\rmfamily
