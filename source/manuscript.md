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

bibliography: library.bib
csl: "../styles/american-geophysical-union.csl"
---

# Introduction

Test citation @McMillan2017

# Methods

# Implications and Discussion

# Timetable

# References
