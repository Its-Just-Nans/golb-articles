# Electricity

## Théorème de Millman

Dans un réseau électrique de branches en paralléle, comprenant chacune un générateur de tension parfait en série avec un élément linéaire, la tension aux bornes des branches est égale a la somme des forces électromotrices respectivement multipliées par l'admittance de la branche, le tout divisé par la somme des admittances.

L'admittance, notée `Y`, est l'inverse de l'impédance `Z`. Elle se mesure en siemens (`S`). On a: `Y = 1/Z` avec `Z` en ohm (`Ω`).

## Les lois de Kirchhoff

Ce sont des propriétés physiques qui s'appliquent sur les circuits électriques. Ces lois portent le nom du physicien allemand Gustav Kirchhoff qui les a établies en 1845. Les deux lois de Kirchhoff sont :

- La loi des noeuds : la somme algébrique des intensités des courants qui entrent par un noeud est égale a la somme algébrique des intensités des courants qui en sortent
- La loi des mailles : dans une maille d'un réseau électrique, la somme des tensions le long de cette maille est toujours nulle. En d'autres termes, si on fait le tour d'une maille et que l'on additionne toutes les tensions de celle-ci (en faisant attention au sens), la somme sera égale a zéro.

## Théorème de superposition

Dans un circuit linéaire, le courant produit par plusieurs sources de courants indépendantes est égale a la somme des courants produits par chaque source prise isolément.

## Théorème de Thévenin

Tout sous-réseau d'un réseau peut être remplacé par un générateur de tension et une résistance en série avec ce générateur.

Méthode pour trouver le générateur de Thévenin :

1. Isoler le réseau (c'est a dire retirer tous les éléments qui ne font pas partis du sous réseau pour lequel on désire connaître le générateur de Thévenin).
2. Remplacer les sources de tension par des courts circuits et les sources de courant par des circuits ouverts.
3. Calculer la résistance de Thévenin (la résistance équivalente du circuit).
4. Rebrancher les sources (annuler l'étape 2).
5. Calculer la tension de Thévenin (tension équivalente entre les deux bornes du réseau pour lequel on cherche le générateur de Thévenin).

## Théorème de Norton

Tout sous-réseau d'un réseau peut être remplacé par un générateur de courant et une résistance en parallèle avec ce générateur.

- [http://ahistace.chez-alice.fr/documents/Chapitre1Fondamentaux.pdf](http://ahistace.chez-alice.fr/documents/Chapitre1Fondamentaux.pdf)
- [http://digital.r2.enst.fr/](http://digital.r2.enst.fr/) - ELECINF simulator
