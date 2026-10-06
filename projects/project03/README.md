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

# Personal Reflections
**Group Leader: Maggie Wenger**

**Other Members:**

**Other Members:**

# Generative AI Appendix
We used Claude when we were struggling with figuring out how to incorporate reverse and forward strands. It gave us a quick explanantion for how we should score `kmer` against both strands, and then use `rng.choice()` with the weighted scores.