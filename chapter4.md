---
title: 'Looking at data with plots'
description: 'R has very powerful tools for looking at data with plots.  We explore some simple plots.'
---

## Histograms

```yaml
type: NormalExercise
key: 37d36434b1
xp: 100
```

R has a very powerful set of functions for plotting data.

It is easy to make simple plots, but, with a little experience, you can make almost any plot you want.

To start, we will explore the values in the `mat_mort_ratio` column of our data frame.

One simple thing we could do is a histogram.  R has a `hist` function,
to make histograms.  Here you will make a histogram for the
`mat_mort_ratio` column.

`@instructions`
Run the code in the script window, to show the histogram of the `mat_mort_ratio` values.  Click "Submit" when you have finished.

`@hint`
If you have deleted the code, copy paste `hist(gender_data$mat_mort_ratio)`
into the script window.

`@pre_exercise_code`
```{r}
gender_data <- read.csv('http://bit.ly/gender-stats-data')
```

`@sample_code`
```{r}
# Show a histogram of the `mat_mort_ratio` values.
hist(gender_data$mat_mort_ratio)
```

`@solution`
```{r}
hist(gender_data$mat_mort_ratio)
```

`@sct`
```{r}
# From :http://datacamp.github.io/testwhat/articles/glossary.html#check-ggplot
ex() %>% {
  check_function(., "hist") %>% check_arg("x") %>% check_equal()
  }
```

---

## Hist yourself

```yaml
type: NormalExercise
key: bd38b15751
xp: 100
```

At the beginning of this tutorial, you did a plot of the values in the
`health_exp_per_cap` column against the matching values in the `mat_mort_ratio`
column.

You have just done the histogram for `mat_mort_ratio`.  Now do the histogram for `health_exp_per_cap`.

`@instructions`
Show the histogram of the values in the `health_exp_per_cap` column of
`gender_data`.

`@hint`
Did you call the `hist` function on the values of the `health_exp_per_cap`
column?

`@pre_exercise_code`
```{r}
gender_data = read.csv('http://bit.ly/gender-stats-data')
```

`@sample_code`
```{r}
# Show the histogram for the 'health_exp_per_cap' column of 'gender_dat'

```

`@solution`
```{r}
hist(gender_data$health_exp_per_cap)
```

`@sct`
```{r}
ex() %>% {
  check_function(., "hist") %>% check_arg("x") %>% check_equal()
  }
```

---

## Histograms, variables

```yaml
type: NormalExercise
key: 32d8888562
xp: 100
```

Here is some revision on variables.

Remember, all that time ago, you made a variable `health_exp_col` that pointed to the `healt_exp_per_cap` column in `gender_data`?  You did it like this:

```{r}
health_exp_col <- gender_data$health_exp_per_cap
```

Because `health_exp_col` now points to the same values as `gender_data$health_exp_per_cap`, if you do `hist(health_exp_col)`, you will get the same histogram as you would for `hist(gender_data$health_exp_per_cap)`.

`@instructions`
Make a new variable `mat_mort_col` that points to the `mat_mort_ratio` column of `gender_data`.

Show a histogram of the values of `mat_mort_col`.

`@hint`
Do you have a variable `mat_mort_col` that points to `gender_data$mat_mort_ratio`?

`@pre_exercise_code`
```{r}
gender_data = read.csv('http://bit.ly/gender-stats-data')
```

`@sample_code`
```{r}
# Make a new variable 'mat_mort_col' that points to the 'mat_mort_ratio' colummn.


# Do a histogram on the values of 'mat_mort_col'


```

`@solution`
```{r}
mat_mort_col <- gender_data$mat_mort_ratio
hist(mat_mort_col)
```

`@sct`
```{r}
ex() %>% {
  check_object(., "mat_mort_col") %>% check_equal()
  check_function(., "hist") %>% check_arg("x") %>% check_equal()
  }
```

---

## Scatter plots

```yaml
type: NormalExercise
key: 002cef1965
xp: 100
```

Now we are ready to go back to the plot we did at the start of this tutorial.

So far, the functions we have used, have had one argument - and so one variable
between the parentheses.  For example:

```{r}
head(gender_data)
hist(mat_mort_col)
```

We are now going to use the `plot` function.  That usually takes two arguments
\- and therefore, has two variables between the parentheses.  The two arguments
are the values for the x axis and the values for the y axis.

`@instructions`
The script windows contains the code to plot the `health_exp_per_cap` column of
`gender_data` against the `mat_mort_ratio` column of `gender_data`. Run the
code to see the result, and then click Submit to continue.j

`@hint`
If you have deleted the code, copy paste `plot(gender_data$health_exp_per_cap,
gender_data$mat_mort_ratio)`.

`@pre_exercise_code`
```{r}
gender_data <- read.csv('http://bit.ly/gender-stats-data')
```

`@sample_code`
```{r}
# Plot 'health_exp_per_cap' (x axis) against 'mat_mort_ratio' (y axis).
plot(gender_data$health_exp_per_cap, gender_data$mat_mort_ratio)
```

`@solution`
```{r}
plot(gender_data$health_exp_per_cap, gender_data$mat_mort_ratio)
```

`@sct`
```{r}
ex() %>% {
  check_function(., "plot") %>% {
    check_arg(., "x") %>% check_equal()
    check_arg(., "y") %>% check_equal()
  }
}
```

---

## You scatter

```yaml
type: NormalExercise
key: f1fad864ed
xp: 100
```

You are well on your way to masteRy.

Here is an exercise that is a little more difficult, to stretch your new skills.

You are going to plot the total health expenditure for each country against the maternal mortality ratio.  You first have to calculate the total health expenditure, and then plot it against the `mat_mort_ratio` column of the data frame.

`@instructions`
Make a new variable `total_health_exp` with the total dollar health expenditure
for every country.  The variable should be the multiplication of the values in
the `health_exp_per_cap` column by the corresponding values in the `population`
column.

Plot `total_health_exp` (on the x axis) against the values from the
`mat_mort_ratio` column (on the y axis).

`@hint`
Did you calculate `total_health_exp` with `gender_data$health_exp_per_cap * gender_data$population`?

`@pre_exercise_code`
```{r}
gender_data <- read.csv('http://bit.ly/gender-stats-data')
```

`@sample_code`
```{r}
# Make a new variable 'total_health_exp' that contains
# the 'health_exp_per_cap' column times the 'population' column.


# Plot 'total_health_exp' on the x axis, 'mat_mort_ratio' column on y axis


```

`@solution`
```{r}
total_health_exp <- gender_data$health_exp_per_cap * gender_data$population
plot(total_health_exp, gender_data$mat_mort_ratio)
```

`@sct`
```{r}
ex() %>% {
  check_object(., "total_health_exp") %>% check_equal()
  check_function(., "plot") %>% {
    check_arg(., "x") %>% check_equal()
    check_arg(., "y") %>% check_equal()
  }
}
```
