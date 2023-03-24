# Group 3 : Sai Myint, Yoojin Oh, Liz Ward, Karl Wirth

    library(ggplot2)
    library(cowplot)

## Question 1:

### Generate 50,000 observations from a random t (gen t03= rt(3)) distribution with the following degrees of freedom \[3, 6, 12, 27, 59\] and also a standard normal distribution.

  
Setting up the plots for the t distributions and standard normal

    # Creating t distributions for each degree of freedom
    t_dist3 <- rt(50000,3)
    t_dist6 <- rt(50000,6)
    t_dist12 <- rt(50000,12)
    t_dist27 <- rt(50000,27)
    t_dist59 <- rt(50000,59)

    # Distribution for standard normal
    normal <- rnorm(50000)

Generating the Plots for t distribution \[3,6,12,27,59\]

    hist(t_dist3)

![](ProblemSet2_files/figure-markdown_strict/unnamed-chunk-3-1.png)

    hist(t_dist6)

![](ProblemSet2_files/figure-markdown_strict/unnamed-chunk-3-2.png)

    hist(t_dist12)

![](ProblemSet2_files/figure-markdown_strict/unnamed-chunk-3-3.png)

    hist(t_dist27)

![](ProblemSet2_files/figure-markdown_strict/unnamed-chunk-3-4.png)

    hist(t_dist59)

![](ProblemSet2_files/figure-markdown_strict/unnamed-chunk-3-5.png)

    hist(normal)

![](ProblemSet2_files/figure-markdown_strict/unnamed-chunk-3-6.png)

We can see that when the degrees of freedom increases in the
t-distribution it approaches a standard normal. With the degree of
freedom at 59, the distribution looks very close to a standard normal
distribution.

## Two Tailed 95% Scores of the T Distribution

Determine the two tailed 95% scores of the t distribution for each
degree of freedom and compare them to a z of the significance (1.96)

#### Calculating the Two Tail 95% score

    # Z Score for the significance of 1.96
    zscore <- qt(0.95,1)

    # Calculating T scores for each Degrees of Freedom
    tscore3 <- qt(0.95,3)
    tscore6 <- qt(0.95,6)
    tscore12 <- qt(0.95,12)
    tscore27 <- qt(0.95,27)
    tscore59 <- qt(0.95,59)

    # Combinding all the t score for each DF to t_scores to print all in one
    t_scores <- c(tscore3,tscore6,tscore12,tscore27,tscore59)

    # Printing Scores
    print (t_scores)

    ## [1] 2.353363 1.943180 1.782288 1.703288 1.671093

    print (zscore)

    ## [1] 6.313752

The Z score is significantly higher than the t scores of every
distribution. We expected this because the degrees of freedom is like a
safety net, and is a more conservative test than the standard normal
distribution.
