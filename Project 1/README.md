# CS571: Artificial Intelligence 
### Assignment 1: Python 
Due: Friday, February 4 2022

For this problem, you are only allowed to use standard python libraries. You may not use third party libraries or call any shell/bash functions. 

You are given a list of tuples of the form (<float> x, <float> y, <float> r) (Let’s call these c-tuples). Each c-tuple represents a circle on a rectangular coordinate space, with x and y being the coordinates of the center, and r being the radius. Assume that each c-tuple has a unique radius. 

Let a cluster of circles be a group of circles where each circle in the group overlaps with at least one other circle in that group. A path is formed between two circles when they overlap. Define a cluster as a group of n circles, where each circle is reachable from every other circle through the formed paths. 

Write a python script that does the following: Return True if the given circles form a cluster and return false if they don’t form a cluster. 
