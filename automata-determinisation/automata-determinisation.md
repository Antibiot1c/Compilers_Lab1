## What is the language accepted by the automaton in the figure below?

#### The given automaton is an ε-NFA (ε-transitions are present).

#### The language accepted by the automaton includes all the strings that lead to the accepting state (state 7, indicated by the double circle).

#### From the automaton, we can see:

#### The ε-transition from state 1 to state 2.
#### The ε-transition chain: 1 → 2 → 3 → 4.
#### The transitions labeled x, y, z.
#### The ε-transition from state 6 to state 7.
#### To derive the language, let's observe the paths:

#### Starting from state 1, through ε-transitions, it can reach states 2, 3, and 4.
#### From state 1, we can go to state 5 by x, and then from 5 to 6 by ε, and from 6 to 7 by ε.
#### Alternatively, from state 1 to state 6 directly by z and then to 7 by ε.
#### Another path is from state 1 to state 2 by ε, then to state 6 by y, and then to 7 by ε.
#### Thus, the language accepted includes strings:

#### "x" (from 1 to 5 to 6 to 7)
#### "z" (from 1 to 6 to 7)
#### "ε" (empty string, through ε-transitions)
#### "y" (from 1 to 2 to 6 to 7)
#### Therefore, the language 𝐿 accepted by the automaton is:𝐿={𝜖,𝑥,𝑦,𝑧}

## Show that it is not deterministic.

#### An automaton is deterministic if, for every state and every input symbol, there is exactly one transition.

#### This automaton is not deterministic due to the following reasons:

#### There are ε-transitions present (1 to 2, 1 to 3, etc.), which means the automaton can transition without consuming any input symbol.
#### From state 1, on input ε, there are multiple transitions possible (to states 2, 3, 4, etc.).
#### The same input symbol can lead to multiple states.

## Determinise it.

#### To convert the ε-NFA to a DFA, we use the subset construction method, which involves creating new states for each possible combination of NFA states.

### Step-by-Step Determinisation:
#### ε-closure Calculation:

#### ε-closure(1) = {1, 2, 3, 4}
#### ε-closure(2) = {2, 3, 4}
#### ε-closure(3) = {3, 4}
#### ε-closure(4) = {4}
#### ε-closure(5) = {5, 6, 7}
#### ε-closure(6) = {6, 7}
#### ε-closure(7) = {7}

### Creating the DFA States:

#### Start state: {1, 2, 3, 4} (from ε-closure of the start state 1)

### Transitions for Each DFA State:

#### From {1, 2, 3, 4}:

#### On x: Goes to {5, 6, 7} (from 1 on x, then ε-closure of 5)
#### On y: Goes to {6, 7} (from 2 on y, then ε-closure of 6)
#### On z: Goes to {6, 7} (from 1 on z, then ε-closure of 6)

#### From {5, 6, 7}:

#### No transitions defined for x, y, z, and ε (they are already in accepting state 7).

### Final DFA:

#### Start state: {1, 2, 3, 4}
#### Accepting states: Any state containing state 7 (here, {5, 6, 7} and {6, 7})

#### Transitions:
#### {1, 2, 3, 4} --x--> {5, 6, 7}
#### {1, 2, 3, 4} --y--> {6, 7}
#### {1, 2, 3, 4} --z--> {6, 7}
#### The determinised automaton (DFA) can be summarized as follows:

#### States: { {1, 2, 3, 4}, {5, 6, 7}, {6, 7} }
#### Start State: {1, 2, 3, 4}
#### Accepting States: {5, 6, 7}, {6, 7}
#### Transitions:
#### {1, 2, 3, 4} --x--> {5, 6, 7}
#### {1, 2, 3, 4} --y--> {6, 7}
#### {1, 2, 3, 4} --z--> {6, 7}
#### This DFA accepts the same language: {ε, x, y, z}.
