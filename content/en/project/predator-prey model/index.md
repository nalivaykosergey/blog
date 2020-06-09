---
title: Predator-Prey Model
summary: Predator-prey model construction method.
tags:
- Mathematical model 
date: "2020-05-28T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  focal_point: Smart

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.


---
## Model description


The simplest model of interaction of two types of "predator - prey" -
Lotka-Volterra model. This two-species model is based on
the following assumptions:
- The population numbers of prey x and predators y depend only on time
(the model does not take into account the spatial distribution of the population by
occupied territory)
- In the absence of interaction, the number of species changes by the model
Malthus, with the number of prey increasing and the number of predators falling.
- Natural mortality of the prey and natural birth rate of the predator
are considered insignificant
- The saturation effect of both populations is not considered
- The rate of increase in the number of prey decreases proportionally
predator abundances

$$
\frac{dx}{dt} = -ax(t) + bx(t)y(t)
$$

$$\frac{dy}{dt} = cy(t) - dx(t)y(t)$$

In this model, x is the number of victims and y is the number of predators. Coefficient a describes the rate of natural increase in the number of victims in the absence of predators, C-the natural extinction of predators deprived of food in the form of victims. The probability of interaction between a victim and a predator is calculated in proportion to both the number of victims and the number of predators themselves (xy). Each interaction reduces the population of prey, but increases the population of predators (the members are bsa and dxy on the right side of the equation).

## Task: 

In the forest live x number of wolves eating hares, the number of which in the same forest y. As long as the number of hares is large enough to feed all wolves, the number of wolves grows until the time comes that the food is no longer enough for all. Then the wolves will start dying and their numbers will decrease. In this case, at some point the number of hares will start to increase again, which will lead to a new growth of the wolf population. This cycle will be repeated as long as both populations exist. In addition, the number of flocks is affected by disease and aging. This model is described with the following equation:


$$
\frac{dx}{dt} = -ax(t) + bx(t)y(t)
$$

$$\frac{dy}{dt} = cy(t) - dx(t)y(t)$$

$a, d$ - mortality rate

$b, c$ - population growth rates


1. Plot the dependence of $x$ on $y$ and graphs of functions $x(t)$ from $y(t)$
2. Find the stationary state of the system.

## Solution

Link to github : [link](https://github.com/nalivaykosergey/predator-prey-model)

## Output

<img class="special-img-class" src="/img/predator-prey model slides img/output.png" />
