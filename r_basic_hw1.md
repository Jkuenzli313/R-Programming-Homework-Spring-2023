# R-Programming-Homework-Spring-2023
#' ---
#' title: HW1
#' author: Jake Kuenzli
#' date: 01/17/2023
#' output: html_document
#' ---
#' Q1
tgpp <- read.csv('Documents/CofC Spring 2023 copy/R Programming/tgpp.csv')
tgpp <- read.csv('https://raw.githubusercontent.com/dmcglinn/quant_methods/gh-pages/data/tgpp.csv')
#' Q2: Name of Columns
head(tgpp)
tail(tgpp)
names(tgpp)
#' Q3: How many rows/columns
dim(tgpp)
#' What object is in each column?
sapply(tgpp, class)
#' Values for specific data files?
tgpp[c(1, 5, 8), c(3, 7, 10)]
#' Creating a plot of scale v. richness
plot(richness ~ scale, data = tgpp, xlab='m^2', ylab='richness', col='firebrick4')
#' Plot set to log=xy
plot(scale~richness, data = tgpp, xlab='m^2', ylab='richness', col='firebrick4', log='xy')
#pdf('./scale v. richness.pdf)
#pdf('./scale v. richness.pdf)
par(mfrow = c(2,1))
plot(scale~richness, data = tgpp, xlab='m^2',
     ylab='richness', col='firebrick4')
plot(scale~richness, data = tgpp, xlab='m^2', 
     ylab='richness', col='firebrick4', log='xy')

