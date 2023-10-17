# Knapsack Implementation

This custom implementation of the genetic algorithm for the knapsack problem uses both roulette wheel and tournament selection. It also has genetic algorithms such as crossover and mutation.

## Features

- **Supports both roulette wheel and tournament selection for both config files
- **Plots showing clear visual outputs for every step
  
- **Flexible parameters**:
    - `Tournament size`: For tournament based selection.
    - `Population Size`: Specify the number of instances for the generation
    - `Stop Criterion`: Generation after which the process end


## Usage

1. Initialize the initial population from the config files and calculate fitness.
2. If the weight in the knapsack exceeds max weight, the fitness is -1
3. For the next generation, choose whether to go ahead with just selection or crossover and mutation.
4. The third step is common for both tournament and roulette wheel. Calculate fitness for population of every generation.
5. Repeat step 3,4 until you reach Stop. 
6. Plot and visualise the outputs


## Function Descriptions

### 1. `get_initial_population (config)`
- **Description**: Populates variables from config and initialize P at gen 0.

### 2. `calc_fitness(P)`
- **Description**: calculates fitness using the fitness function of highest value. 
    If the weight in the knapsack exceeds the maximum weight, the fitness value is assigned as -1
    
    P - population

### 3. `selection_using_tournament(P,tournament_size=5)`
- **Description**: P - population
    Instance is selected using tournament selection
    Uses tournament selection with tournament size of 5.

### 4. `selection_using_roulette(P)`
- **Description**: P - population
    Instance is selected using roulette wheel selection.

### 5. `reproduction(a,b,index)`
- **Description**: a - instance 1
    	b - instance 2
    	index - index for single point crossover.

### 6. `mutation(P)`
- **Description**: P - population
Mutation randomly selects an instance, index and swaps the value at thatindex. The output of this function is a mutated population


### 7. `tournament(P,n,m)`
- **Description**: Using tournament selection - if the option is only selection, only selection operation is performed. 
    If we choose to perform reproduction operation, crossover is performed
    Similarly we can choose if we want to perform mutation
    P - population
    n- user selected choice (performs either just selection or crossover)
    m - user selected choice (either to perform mutation or not)

### 8. `roulette(P,n,m)`
- **Description**:  Using roulette wheel selection - if the option is only selection, only selection operation is performed. 
    If we choose to perform reproduction operation, crossover is performed
    Similarly we can choose if we want to perform mutation
    P - population
    n- user selected choice (performs either just selection or crossover)
    m - user selected choice (either to perform mutation or not)

### 9. `active_gene_tourn()`
- **Description**: shows the number of active genes in the fittest individual of every generation
    uses tournament selection

### 10.`active_gene_roulette()`
- **Description**: shows the number of active genes in the fittest individual of every generation
    uses roulette wheel selection.


