---
author: Jaspreet Singh & Daniël Stekelenburg
title: An Integrated trust and reputation model for open multi-agent systems
subtitle: A paper by Trung Dong Huynh, Nicholas R. Jennings & Nigel R. Shadbolt (2006)
theme: uucs
mainfont: Ubuntu Light
sansfont: Ubuntu Light
---

# Overview

1. Terminology
2. The FIRE Model
3. Results
4. Conclusions

---

# .. an open MAS?

> “...systems in which agents can freely join and leave at any time and where the agents are owned by various stakeholders with different aims and objectives.”

. . .

This causes some uncertainties:

1. Agents tend to be self-interested and may be unreliable
2. No agent can know everything about the environment
3. No central authority can control everything


---

# Sources of trust/reputation

| Source                 | Type                 |
|:-------------          |:-------------        |
| Direct experience      | Interaction trust    |
| Witness experience     | Witness reputation   |
| Role-bases rules       | Role-based trust     | 
| Third-party references | Certified reputation |


---

# Fire

Uses all four sources of information

Works, based on the following assumptions:

* Agents are willing to share their experiences with others (as witnesses or as referees)
* Agents are honest in exchanging information with one another.

. . .

So… we do not consider the problem of lying and inaccuracy.

---


# How to quantify trust/reputation? 

## The old way

Just take the average of all the ratings.

. . .

However... these ratings are not equally relevant: 

* Older ratings might not be as relevant as new ones
* Some ratings are more credible than other depending on the source

So in what other way can we quantify trust?

---

# How to quantify trust? 

## The FIRE way

Every rating is a tuple $r = (a,b,c,i,v)$.

Where $a$ and $b$ are the agents participating in transaction $i$. Value $v \in [-1, +1]$ is the rating given by agent $a$ to agent $b$ regarding regarding topic $c$ (e.g. quality, honesty).

These ratings are stored in the agent's local database. 

. . .

Since ratings become outdated over time, an agent only stores the latest $H$ transactions it gave to other agents.

---

# How to quantify trust? 

## The FIRE way

Use a rating weight function $\omega_K$ for every type of trust, where $K \in \{I,R,W,C\}$.

. . .

This gives us:

\begin{equation} 
\mathcal{T}_K(a,b,c) = 
\frac{\sum\nolimits_{r_i \in \mathcal{R}_K(a,b,c)} \omega_K (r_i) \cdot v_i}
{\sum\nolimits_{r_i \in \mathcal{R}_K(a,b,c)} \omega_K (r_i)} 
\end{equation}

---

# What about reliability

---

# Summary


<!-- Local Variables:  -->
<!-- pandoc/write: beamer -->
<!-- pandoc/latex-engine: "xelatex" -->
<!-- pandoc/template: "beamer-template.tex" -->
<!-- End:  -->
