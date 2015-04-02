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

--

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

# >

* > redirects the output from stdout to the file that you specify

    ```
    sort data.txt > data.sorted
    ```

---

# uniq

* uniq removes duplicates, but the file must be in sorted order

    ```
    uniq data.sorted
    ```

--

* uniq can also count the number of occurances in a file with the -c flag

    ```
    uniq -c data.sorted
    ```

---

# |

* | or pipe redirects the output of one command and uses it as the input of another. 

--

* So instead of doing everything step-by-step, we can use redirection to create one command.

    ```
    sort data.txt | uniq
    ```
---

# grep

* grep is used for searching files

    ```
    grep searchterm data.txt
    ```

--

* You can also use regular expressions with grep

    ```
    grep '^start' data.txt
    ```

--

* You can also use grep to count occurances of the search term.

    ```
    grep -c searchterm data.txt
    ```

---

# sed

* sed is really useful in text manipulation

--

* You can print out specific lines 
    ```
    sed -n 3,27p file
    ```

--

* You can delete lines
    ```
    sed 1d file1 > file2
    ```

    ```
    sed 2,17d file1 > file2
    ```

--

* You can use sed to replace patterns

    ```
    sed 's/find/replace/g' file1 > file2
    ```

--

* For example if you want to remove the white space infront of the counts from uniq you could use sed

    ```
    sort data.txt | uniq | sed 's/^ *//g' 
    ```
---

