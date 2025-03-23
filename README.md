# Bacteria Growth Dynamics and Antibiotic Dosage Optimization

This project simulates bacteria growth dynamics using pharmacokinetics (PK) and pharmacodynamics (PD) models and optimizes daily antibiotic dosage using Genetic Algorithms (GA). The goal is to eliminate bacteria within 5 days while minimizing the total antibiotic dosage.

## Project Overview
Key Features
1. Bacteria Growth Dynamics:
     - Models bacterial population dynamics using logistic growth.
     - Incorporates horizontal gene transfer (HGT) for resistance spread.
     - Accounts for natural death and antibiotic-induced death.
     - Differentiates between susceptible and resistant bacteria.

2. Antibiotic Pharmacokinetics (PK):
    - Simulates antibiotic degradation using first-order kinetics.
    - Models antibiotic concentration over time based on dosage and degradation rate.

3. Antibiotic Pharmacodynamics (PD):
    - Uses the Hill function to model antibiotic kill rates.
    - Captures saturation effects, cooperativity, and threshold behavior.

4. Optimization with Genetic Algorithms (GA):
    - Elimination of bacteria within 5 days.
    - Minimization of total antibiotic dosage.

5. Sensitivity Analysis:
  - Analyzes the impact of bacteria growth rate (r) and antibiotic degradation rate (k) on treatment outcomes.

## Mathematical Models
### 1. Antibiotic Kill Rate (Hill Function)
The Hill function models the relationship between antibiotic concentration and bacterial kill rate:
  
  $A_{i}(C)  = \text{Emax}_{i} \cdot \frac{C^{n}}{C^{n} + {E50}^{n} }$
  
  Where:
  - $A_{i}(C)$ : Antibiotic kill rate for bacteria type 
  - $C$ : Antibiotic concentration.
  - $\text{Emax}_{i}$ : Maximum kill rate.
  - ${E50}^{n}$ : Concentration for half-maximal effect.
  - $n$ : Hill coefficient (cooperativity).

### 2. Antibiotic Degradation Rate (First-Order Kinetics)
Antibiotic concentration degrades over time:
  
  $C = {C}_{0} * e^{-kt}$
  
  Where:
  - $C$ : Antibiotic concentration at time 
  - $k$ : Degradation rate constant.
  - ${t}_{1/2}$: Half-life of the antibiotic.

### 3. Optimization with Genetic Algorithms  
#### Fitness Function
  - The fitness function balances three objectives:
  - Minimize final bacterial population.
  - Minimize total antibiotic dosage.
  - Achieve treatment within 5 days.
  
  $F = w_{1} \cdot B_{norm} + w_{2} \cdot D_{norm} + w_{3} \cdot T_{f, norm}$

  Where:
  - $B_{norm}$: Normalized total bacterial load.
  - ​$D_{norm}$: Normalized total dosage.
  - $T_{f, norm}$: Normalized final bacteria population.
  - $w_{1}, w_{2}, w_{3}$: Weights for each objective.



#### Optimization Process
  - Initialization: Generate an initial population of dosage schedules.
  - Selection: Select schedules with the best fitness scores.
  - Crossover: Combine schedules to create new offspring.
  - Mutation: Introduce random changes to explore new solutions.
  - Iteration: Repeat until convergence or a stopping criterion is met.

## Reference
1. H. P. Rang, "The Receptor Concept: Pharmacology's Big Idea," British Journal of Pharmacology, 2006.
2. Roland R. Regoes et al., "Pharmacodynamic Functions: A Multiparameter Approach to the Design of Antibiotic Treatment Regimens," Antimicrobial Agents and Chemotherapy, 2004.
3. Iona K. Paterson et al., "Optimising Antibiotic Usage to Treat Bacterial Infections," Scientific Reports, 2016.
