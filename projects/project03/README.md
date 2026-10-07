# Introduction
Identifying regulatory motifs — short, recurring sequence patterns such as transcription factor binding sites — is a central problem in computational biology. Because these motifs are typically short, degenerate, and scattered across many sequences without exact alignment, they cannot be found through simple string matching alone; the search space of 
possible motif positions and compositions grows too large for exhaustive search to be practical.

This project implements Gibbs sampling, a Markov Chain Monte Carlo (MCMC) approach to identifying sequence enrichment. Gibbs sampling uses a stochastic, optimization-based strategy: it starts from a random guess, iteratively scores candidate positions against a position weight matrix (PWM) representing the current best estimate of the motif, and  resamples one sequence's position at a time — conditioned on the model built from all other sequences — to converge toward an optimal solution.

# Pseudocode
```
    
```

# Successes
We all seemed to be getting the hang of GitHub and managing pull requests and collaborative coding. We had great success meeting and partner coding over teams calls, as well as working independently and keeping each other up to date on the progress of our collective code.

# Struggles
Issue: Our group struggled for a while understanding how to implement the forward and reverse strands.

Fix: We took time to talk it out with eachother, and determined how we wanted to proceed with the scoring and keeping track of forward and reverse strands. We ended up deciding to keep track of the strands by appending either `0` or `1` for forward and reverse complement respectively

Issue: When first running the "Challenge Yourself" section, we came up with a completely empty graph. 

Fix: We figured out that it could likely be because we still had harcoded the number of iterations to loop through when finding motifs, menaing maybe things had not converged by that time. We fixed this by using the `pmf_ic()` function, to correctly check for and monitor the status of convergence. 

# Personal Reflections
**Group Leader: Maggie Wenger**

I think this project was an overall success. Our group was able to work together really well both asynchonously and synchronously over Teams and GitHub to work through the algorithm throughout the two weeks. I (along with my group members) struggled in the beginning and had to spend time with pen and paper just to figure out the concept and the logitstics of what this code was supposed to do and how to tackle it. Spending this much time problem-solving and getting knee-deep in the code really helped me to understand what Gibbs Sampling does and how to weight our randomization at nearly every step.

Future Directions: If we had more time to work on this code, one of the things I would have liked to do would be to make more functions, so that our main `GibbsMotifFinder()` wasn't so crowded. For example, having a helper function `init_motifs()` for initializing motifs at each sequence, and `check_convergence()` for finding if we have reached convergence during our iterations.

**Other Members:**

**Other Members:**

# Generative AI Appendix
We used Claude when we were struggling with figuring out how to incorporate reverse and forward strands. It gave us a quick explanantion for how we should score `kmer` against both strands, and then use `rng.choice()` with the weighted scores.