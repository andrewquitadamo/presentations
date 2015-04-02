class: center, middle

# IPython Notebook and Useful Shell Commands

Andrew Quitadamo  
Programming II

---

# IPython Notebook

* IPython Notebooks provide a way to combine code, texts and plots.

--

* Similar to old-school lab notebooks, where results and methods are together. Somebody could look at your lab notebook and reproduce your analysis (in theory). 

--

* Works in your browser, similar to the interactive Python shell on the command line.

---

# Version 3.0.0

* IPython Notebooks aren't just for Python. Version 3.0.0 makes using the different kernals easier. 

--

* R, Julia, Perl, Bash, Spark, Haskell, Clojure, Go, Scala and many others.

---

# NBViewer

* Website to display and share IPython Notebooks with others

--

* [Paper in Nature Genetics](https://github.com/theandygross/TCGA/tree/master/Analysis_Notebooks#guide-to-running)

---

# Installing

* [Install Instructions](http://ipython.org/install.html)

--

* I would highly suggest using Anaconda. You should be able to download it onto the lab computers, and use it to install IPython, Numpy, Scipy, and other Python packages without administrator access.

---

# Using IPython Notebook

```
ipython notebook
```

---

# More Advanced Shell Commands

* A ton of data manipulation, and even some analysis can be done without using R, or Python, or Excel. 

--

* These commands are pretty universal across the *nix distributions.

---

# cut

* You can use cut to access columns of data


```
cut -f 2 data.txt
```

---

* You can specify the deliminator

```
cut -d';' -f 2 data.txt
```

---

# sort

* It does exactly what it says

```
sort data.txt
```

--

* You can specify which column to sort on using the -k flag

```
sort -k 2,2 data.txt
```

--

* You can specify to sort numerically

```
sort -n data.txt
```

--

* And of course combine them

```
sort -n -k 2,2 data.txt
```

---


