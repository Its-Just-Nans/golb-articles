# Maths

## Articles

- great article to understand normalization and dot product : [https://stackoverflow.com/a/45410687/15568835](https://stackoverflow.com/a/45410687/15568835)
- [classification-metrics](https://kobia.fr/category/classification-metrics/)

## Great videos

- [Vectors](https://www.youtube.com/watch?v=Ej3ZVxljJfo)
- [Matrices and Transformations](https://www.youtube.com/watch?v=HgQzOmnBGCo)
- [Trigonometry](https://www.youtube.com/watch?v=IydbTBZJy7w)

## Website

- [https://www.mathraining.be/](https://www.mathraining.be/)
- [https://www.euclideanspace.com/](https://www.euclideanspace.com/)
- [http://ddmaths.free.fr/niv2.html](http://ddmaths.free.fr/niv2.html) - Math exercises
- [http://jgaltier.free.fr/liens.htm](http://jgaltier.free.fr/liens.htm) - Additional math resources
- [http://perso.eleves.ens-rennes.fr/~tpier758/cours.html](http://perso.eleves.ens-rennes.fr/~tpier758/cours.html) - Clean math courses
- [https://www.math.univ-paris13.fr/~borello/teaching](https://www.math.univ-paris13.fr/~borello/teaching)

## Quelques notations mathématiques

### Ensembles de nombres

```latex
\N = \text{Ensemble des entiers naturels} = \{ 0;1;2;3; ... \}
\newline
\Z = \text{Ensemble des entiers relatifs} = \{ ... ; -3 ; -2 ; -1 ; 0 ; 1 ; 2 ; 3 ; ... \}
\newline
\mathbb{Q} = \text{Ensemble des nombres rationnels} = \{ \frac{a}{b}~\text{tels que}~a \in \Z \text{,}~b \in \Z~\text{et}~b \ne 0 \}
\newline
\R = \text{Ensembles des nombres réels}
\newline
\mathbb{C} = \text{Ensembles des nombres complexes}
\newline
~~~~~~~\text{Notons A un ensemble de nombres réels}
\newline
\mathbb{R} \setminus A = \text{Ensemble des réels, privé de tous les réels qui appartiennent à A}
\newline
\R^* = \text{Ensembles des nombres réels non nuls} = \R \setminus \{ 0 \}
\newline
\mathbb{R}^+ = \text{Ensembles des nombres réels positifs}
\newline
\R^- = \text{Ensembles des nombres réels négatifs}
```

### Intervalles

```latex
\lbrack a ; b \rbrack~\text{Ensemble de tous les réels compris entre a et b, les bornes a et b comprises.}
\newline
\text{Il est appelé "intervalle fermé a, b".}
\newline
\rbrack a ; b \lbrack~\text{Ensemble de tous les réels compris entre a et b, les bornes a et b exclues.}
\newline
\text{Il est appelé "intervalle ouvert a, b".}
\newline
\lbrack a ; b \lbrack~\text{Ensemble de tous les réels compris entre a et b, la borne a comprise et la borne b exclue.}
\newline
\text{Il est appelé "intervalle fermé en a, ouvert en b".}
```

### Quelques symboles

```latex
\forall~\text{quel que soit}
\newline
\exists~\text{il existe}
\newline
\in~\text{appartient}
```

### Quelques lettres grecques

```latex
\alpha~\text{(alpha)}~~
\beta~\text{(beta)}~~
\gamma~\text{(gamma)}~~
\delta~\text{(delta)}~~
\Delta~\text{(Delta maj)}~~
\newline
\epsilon~\text{(epsilon)}~~
\theta~\text{(téta)}~~
\lambda~\text{(lambda)}~~
\zeta~\text{(zeta)}~~
\mu~\text{(mu)}~~
\newline
\xi~\text{(xi)}~~
\eta~\text{(eta)}~~
\nu~\text{(nu)}~~
\pi~\text{(pi)}~~
\Pi~\text{(Pi maj)}~~
\newline
\rho~\text{(rho)}~~
\sigma~\text{(sigma)}~~
\Sigma~\text{(Sigma maj)}~~
\tau~\text{(tau)}~~
\upsilon~\text{(upsilon)}~~
\phi~\text{(phi)}~~
\Phi~\text{(Phi maj)}~~
\newline
\chi~\text{(chi)}~~
\psi~\text{(psi)}~~
\Psi~\text{(Psi maj)}~~
\omega~\text{(omega)}~~
\Omega~\text{(Omega maj)}~~
```

> <https://katex.org/docs/supported.html>

## Euler constant `e`

```latex
exp^{x}
``` is called the `natural exponential function`


```latex
e=\sum \limits _{n=0}^{\infty }{\frac {1}{n!}}=1+{\frac {1}{1}}+{\frac {1}{1\cdot 2}}+{\frac {1}{1\cdot 2\cdot 3}}+\cdots\newline
e= 2.718 281 828...
```

## exp(ix)

```latex
exp^{ix} = cos(x) + i sin(x)\newline

exp^{ix} = \frac{exp^{ix} + exp^{-ix}}{2} + i\cdot\frac{exp^{ix} - exp^{-ix}}{2i}\newline

exp^{ix} = \frac{exp^{ix} + exp^{-ix}}{2} + i\cdot\frac{exp^{ix} - exp^{-ix}}{2i}\newline

exp^{ix} = \frac{exp^{ix} + exp^{-ix}}{2} + \frac{exp^{ix} - exp^{-ix}}{2}\newline

exp^{ix} = \frac{exp^{ix} + exp^{-ix} + exp^{ix} - exp^{-ix}}{2}\newline

exp^{ix} = \frac{exp^{ix} + exp^{ix} + exp^{-ix} - exp^{-ix}}{2}\newline

exp^{ix} = \frac{exp^{ix} + exp^{ix}}{2}\newline

exp^{ix} = \frac{2exp^{ix}}{2}\newline

exp^{ix} = exp^{ix}\newline
```

## exp(-ix)

```latex
exp^{-ix} = cos(x) - i sin(x)\newline

exp^{-ix} = \frac{exp^{ix} + exp^{-ix}}{2} - i\cdot\frac{exp^{ix} - exp^{-ix}}{2i}\newline

exp^{-ix} = \frac{exp^{ix} + exp^{-ix}}{2} - i\cdot\frac{exp^{ix} - exp^{-ix}}{2i}\newline

exp^{-ix} = \frac{exp^{ix} + exp^{-ix}}{2} - \frac{exp^{ix} - exp^{-ix}}{2}\newline

exp^{-ix} = \frac{exp^{ix} + exp^{-ix} - (exp^{ix} - exp^{-ix})}{2}\newline

exp^{-ix} = \frac{exp^{ix} + exp^{-ix} - exp^{ix} + exp^{-ix}}{2}\newline

exp^{-ix} = \frac{exp^{ix} - exp^{ix} + exp^{-ix} + exp^{-ix}}{2}\newline

exp^{-ix} = \frac{exp^{-ix} + exp^{-ix}}{2}\newline

exp^{-ix} = \frac{2exp^{-ix}}{2}\newline

exp^{-ix} = exp^{-ix}\newline
```

## Cercle trigonométrique et sinus

![sinus](./data/sinus.gif)
