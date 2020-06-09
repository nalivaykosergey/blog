---
title: Slides
summary: Predator-prey model construction method.
authors: []
tags: []
categories: []
date: "2019-02-05T00:00:00Z"
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: black
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
---

# Predator-prey model

---

## Model. Model description.

---

The simplest model of interaction of two types of "predator - prey" -
Lotka-Volterra model. This two-species model is based on
the following assumptions:


1. The population numbers of prey x and predators y depend only on time

2. In the absence of interaction, the number of species changes by the model
Malthus, with the number of prey increasing and the number of predators falling.


---

3. Natural mortality of the prey and natural birth rate of the predator
are considered insignificant

4. The saturation effect of both populations is not considered

5. The rate of increase in the number of prey decreases proportionally
predator abundances

---

In this model, x is the number of prey, y is the number of predators.

<img class="special-img-class" src="/img/predator-prey model slides img/model.png" />

Evolution of the prey population and
predators in the Lotka-Volterra model

---




## Algorithm.

---

Our predator-prey model has only two initial states: 
1. Stationary state (Figure 1, point A)
2. The state having a deviation from the stationary one (Figure 1, point B)

<img class="special-img-class" src="/img/predator-prey model slides img/figuresAB.png" />

---


### With a small change in the model, the following happens:

$$
\frac{dx}{dt} = -ax(t) + bx(t)y(t)
$$

$$\frac{dy}{dt} = cy(t) - dx(t)y(t)$$


Here x - number of preys, y - number of predators. a - ratio of natural mortality of predators, b - ratio of natural increase in preys, c - ratio of increase in predators, d - ratio of mortality of preys.

---

Scheme:

<img class="special-img-class" src="/img/predator-prey model slides img/scheme.png" />

---

## Software solution.

---


<img width = "600" class="special-img-class" src="/img/predator-prey model slides img/octave.png" />

<p style = "float:right">To solve this problem, we used the system for mathematical calculations gnu octave. GNU Octave is a free system for mathematical calculations, using a high-level MATLAB-compatible language.</p>

---

### Code.

```MATHLAB
set(figure,'Name','Lotka-Volterra models of Predator-Prey Relationships','NumberTitle','off')

function dx=f(x,t)
	dx(1) = -0.2*x(1) + 0.05*x(1)*x(2);
	dx(2) = 0.5*x(2) - 0.02*x(1)*x(2);
endfunction


x0=[5;10]; 
t = [0: 0.1: 400];
y = lsode("f", x0, t);
y1 = y(:, 1);
y2 = y(:, 2);

sPoint = [ 0.5/0.02; 0.2/0.05 ]

subplot(2,2, 1:2);
  	hold on
  	plot(sPoint(1),sPoint(2), 'o')
	plot(y1, y2, "linewidth", 1 , 'm');
  	legend("Stationary point", "LotkaVolterra equations")
	xlabel("Predators");
	ylabel("Preys");
	title("Predator-Prey model");
subplot (2, 2, 3);
	plot(t, y1, "linewidth", 1 , 'g');
	xlabel("Time");
	ylabel("Number of predators");
	title("Number of changes predator populations");
subplot (2, 2, 4);
	plot(t, y2, "linewidth", 1 , 'c');
	xlabel("Time");
	ylabel("Number of preys");
	title("Number of changes prey populations");
```
