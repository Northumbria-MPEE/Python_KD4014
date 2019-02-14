---
title: Running your Code as a Python Script
teaching: 10
exercises: 10
questions:
- "How can I export my Jupyter notebook as a Python script?"
- "How do I run a Python script?"
- "How can I pass an argument to my script?"
objectives:
- "Export a Jupyter notebook to a Python script"
- "Run a Python script using the terminal"
- "Write a Python script which takes a command line argument"
keypoints:
- Copy/paste or use the `%%writefile myfile.py` notebook magic to export a single cell
- Use `jupyter nbconvert --to script my_notebook.ipynb` to export a complete notebook 
- Use `python script_name.py` to run a script from the terminal
- Import the `sys` module and use `sys.argv` to take a command line argument
---

You may find easier to share a plain text file.
Easier to version control (though there are other tools)

Need to show how to save plots on previous section

To export a single cell


To export a complete notebook


To run a script from the terminal

To take a command line argument