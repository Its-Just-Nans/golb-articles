# Télécommunications

## Sources

- Cours, TPs et TDs de **Mme.THEYS**
- Cours, TPs et TDs de [**M.PAYAN**](https://www.i3s.unice.fr/~fpayan/)
- [Site Web de M.Mazet](http://miv.u-strasbg.fr/mazet/mazet-fr.html)
- [Animations sur le site de M.Mazet](http://miv.u-strasbg.fr/mazet/animations/)

---

## Bit symbole et valence

Un **symbole** contient plusieurs bits. Le nombre de bits par symbole est noté `n`.

Le nombre d'états possibles d'un signal transmis appelé [valence](https://fr.wikipedia.org/wiki/Valence_(r%C3%A9seau)) est noté M.

On le calcul donc avec la `valence` (nombre d'états possibles) :

<div class="katex-center">

```latex
M = 2^n
```

</div>

---

## Débit symbole et débit binaire

Le débit symbole est également appelé **rapidité de modulation**. Le débit symbole est l'inverse du temps symbole :

Débit symbole (**en bauds**)

<div class="katex-center">

```latex
R = \frac{1}{Ts}
```

</div>

Le débit binaire est l'inverse du temps **binaire** :

Débit binaire (**en bits/s**)

<div class="katex-center">

```latex
Rb = \frac{1}{Tb}
```

</div>

On peut donc réaliser des conversions entre débit symbole et débit binaire:

Débit binaire en débit symbole en utilisant la Valence (**en bits/s**)

<div class="katex-center">

```latex
Rb = R \cdot log_2(M) = R \cdot n
```

</div>

---

## Éléments de la chaîne de transmission

- `BER` : Bit Error Rate, nombre d'erreur par bit
- `SER` : Symbol Error Rate, nombre d'erreur par symbole

### 1. Le codage source

Le `codage source` sert à compresser les données à envoyer pour réduire le nombre de bits à transmettre.

### 2. Le codage canal


Le `codage canal` sert à ajouter de la redondance dans les données à envoyer. Cela sert à corriger les potentielles erreurs (bruit, interférences...) lors de la transmission.

### 3. Le modulateur numérique

Le modulateur transmet les bits par paquets, appelés symbole. Les symboles forment un alphabets.

Exemple d'alphabet de 4 symboles : m1 = 00, m2 = 01, m3 = 10, m4 = 11

Le modulateur numérique est constitué de deux éléments :
- le codeur transforme le symbole mk en un jeu de paramètres (ak, Phik)
- le modulateur construit un signal Sk(t) d'une durée Ts (durée symbole) grâce aux paramètres ak et Phik

### 4. Le canal

Le canal agit comme un filtre passe-bande, de plus, il ajoute du bruit et effectue une distorsion d'amplitude et de phase sur le signal.

Le signal reçu est donc :

<div class="katex-center">

```latex
x(t) = Spk(t) + w(t)
```

</div>

> Légende :
>
> - `x(t)` : signal reçu
> - `Spk(t)` : le signal déformé par le filtre passe-bande
> - `w(t)` : le bruit

### 5. Le démodulateur numérique

Le démodulateur transforme le signal et une suite de bits.

Le démodulateur numérique est constitué de deux éléments :
- le détecteur retrouve les param^tres (ak, Phik)
- le décodeur reconstruit un symbole à partir du signal x(t) et des paramètres ak et Phik, cette valeur peut être fausse si le signal est dégradé

### 6. Le décodage canal

Le décodage canal sert à utiliser la redondance mit en place pour corriger les erreurs

### 7. Le décodage source

Le décodage source décompresse la séquence de bits.

Le signal final pourra être différent du signal source à cause des erreurs

---


## Capacité d'un canal de transmission

### Théorème de Shannon-Hartley

Le théorème de Shannon-Hartley permet de connaître la capacité :

<div class="katex-center">

```latex
C = B \cdot log_2(1 + \frac{S}{N})
```

</div>

> Légende :
>
> - `C` : la capacité en bits/s
> - `B` : la bande occupée en Hz
> - `S/N` : le rapport signal sur bruit
> - `(1 + S/N)` : la valence maximale


Le bruit implique une limitation sur la valence ce qui limit la capacité

On a donc

<div class="katex-center">

```latex
R_b <= C
```

</div>

> Légende:
>
> - `Rb` : le débit binaire de la source
> - `C` : la capacité du canal

### Théorème de Nyquist

Le théorème de Nyquist définie la largeur de bande minimale pour un canal (pour qu'il n'y est pas d'interférences inter-symboles - IIS)

<div class="katex-center">

```latex
B >= R
```

</div>

> Légende :
>
> - `B` : la largeur de bande
> - `R` : le débit symbole

Comme la bande passante d'un canal est limité, le temp symbole est lui aussi limité donc la rapidité de la transmission est limité

### Diagramme de l'oeil

Le diagramme de l'oeil permet de détecter les interférences inter-symboles (IIS).

Pour le tracer, on prend une période (soit T ou 2*T) et on trace le signal sur cette période donnée.

On peut donc mesurer la distance horizontale, aussi appelée "l'ouverture de l'oeil".

[Animation du diagramme de l'oeil](http://miv.u-strasbg.fr/mazet/animations/eyediag.html)

---

## Diagramme de constellation

Le diagramme de constellation permet de mesurer l'écart entre les symboles créer par le modem IQ.


Le code de Gray permet de réduire les erreurs, il sert à définir un seul bit différent pour chaque déphase de pi/2

---

## Modulations

Pour transmettre le signal, on le module à l'aide de certains méthodes de modulations.

Si on veut réduire la bande de fréquence occupée par le signal, on utilise des cosinus surélevé ou des gaussiennes au lieu de pulse carré.

On mesure l'efficacité (qu'il faut maximiser) de la modulation à l'aide de la formule suivante :

<div class="katex-center">

```latex
p = \frac{R_b}{B}
```

</div>

> Légende :
>
> - `p` : l'efficacité
> - `Rb` : le débit binaire de la source
> - `B` : la largeur de bande


### ASK

_**A**mplitude-**S**hift **K**eying_.

On module en variant l'**amplitude**

|                                                                Fonctionnement                                                                                |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| ![FSK image form Wikipedia](https://www.researchgate.net/profile/Ahmad_Fauzi_Abas/publication/221907745/figure/fig1/AS:670028466765837@1536758643863/Example-of-ASK-modulation-foramt-a-binary-signal-and-b-ASK-modulated-signal.png) |

### FSK

_**F**requency-**S**hift **K**eying_ (aussi appelé **MDF** - Modulation par Déplacement de Fréquence).

On module en variant la **fréquence**

|                                                                Fonctionnement                                                                                |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| ![FSK image form Wikipedia](https://upload.wikimedia.org/wikipedia/commons/thumb/9/90/Frequency-shift_keying_fr.svg/330px-Frequency-shift_keying_fr.svg.png) |

### MSK

Le MSK (Minimum Shift Keying), utilisé dans lee GSM est une variante du FSK où le signal est démodulé de façon cohérente.

### GMSK

Le GMSK (Gaussian Minimum Shift Keying) est une variante du MSK qui utilise un filtre Gaussien pour réduire la largeur de bande.

### PSK

_**P**hase-**S**hift **K**eying_ .

On module en variant la **phase**.

On peut donc choisir plusieurs phases, voici les modulations PSK connus :

#### BPSK

_**B**inary **P**hase-**S**hift **K**eying_. C'est donc une modulation PSK avec seulement **deux phases**

|                                             Fonctionnement                                          |                                  Diagramme de constellation                                              |
|:---------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------:|
| ![BPSK](https://i.pcmag.com/imagery/encyclopedia-terms/psk-_psk.fit_lim.size_1050x.gif) | ![BPSK](https://upload.wikimedia.org/wikipedia/commons/thumb/4/41/BPSK_Gray_Coded.svg/200px-BPSK_Gray_Coded.svg.png) |

#### DPSK

Le DPSK est une modulation par phase qui utilise la phase du symbole précédent pour coder un symbole.

#### QPSK

_**Q**uadrature **P**hase-**S**hift **K**eying_ aussi appelé **4-PSK**.

C'est donc une modulation PSK avec **quatre phases** différentes

|                                             Fonctionnement                                          |                                  Diagramme de constellation                                              |
|:---------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------:|
| ![QPSK](https://i.pcmag.com/imagery/encyclopedia-terms/psk-_qpsk.fit_lim.size_800x.gif) | ![QPSK constellation](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/QPSK_Gray_Coded.svg/200px-QPSK_Gray_Coded.svg.png) |

### QAM

_**Q**uadrature **A**mplitude **M**odulation_ (en français MAQ - modulation d'amplitude en quadrature).
