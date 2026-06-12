# Gros relais

## qte par PCB

1

## Conditions

2 contacts de comutation
Courant de commutation min 3.5 A
tension de bobine 12VDC

## Choix

G2RK-2 DC12

# Petit relais

## qte par PCB

1 ou 0 selon configuration

## Conditions

2 contacts de comutation
Courant de commutation min 2 A
tension de bobine 12VDC

## Choix

Relais classique qui rentre dans du DIL-16

# Diode de roue libre

## qte par PCB

2

## Conditions

Diodes de roue libre
THT

## Choix

...

# transistor pour commande du relais

## qte par PCB

2 ou 0 selon configuration

## Conditions

NPN (pour commande par arduino)
Ic = 140 mA 

## Choix

2N2222A

# Resistance base du transistor precedents

## qte par PCB

2 ou 0 selon configuration

# conditions 

THT

## calculs

Ic = 0.140
Ub = 5
Ube = 1.2 (environ)
Ur = Ub - Ube = 5 - 1.2 = 3.8
R = Ur / (Ic / 10) (par principe) = 270 => 270

# resistance de pulldown base transistor precedent

# choix

10 k ohm

# 555

## qte par PCB 

1 ou 0 selon configuration

## conditions 

THT

## choix

TLC555

# potentiometre

## condition

Avec au moins 1 interrupteurs
4.7 kohm ou 5 kohm linéraire (conservé le même composants)
~300° de rotation

## choix

...

# R1 charge

## calculs

environ 10x plus petite que potentiometre

## choix

470 ohm

# diodes charges décharge

## choix

# condensateur de charge décharge

## conditions

céramique si la valeur existe, sinon à film
dimensionné pour 1 kHz (Arduino environ 500 Hz ou 1kHz)

# calculs

```
C = 1 / (0.693 * Rpot * f)
  = 1 / (0.693 * 4700 * 1000) = 307 nF =(E12) 270 nF 
```

# choix

270 nF

# transistor driver MOSFET

## qte sur le PCB

1 

## descisions

NPN car MOSFET est de type P

## calculs

```
Hfe = 50 (apeupret)
I_c = 18e-3
U = 12
Ube = 1.2 (environ)
Ur = 10.8 
R = Ur / (Ic / Hfe) = 600 k =(E12) 1k
```

# choix

2N3904

# MOSFET

## conditions

U_ds_max > 24 VDC
I_d_max > 3 A
U_gs_max > 12 VDC
R_ds_on << 1 ohm

## descision

type P pour correspondre au fonctionnement des autres alimentations et éviter les saut de tension aux changement d'alimentations

## calculs

```
T = 1 / f
  = 1 / 1000 = 0.001
ton = 0.01 * T
    = 0.01 * 0.001 = 10e-6
I_g = Qg / ton
    = 180e-9 / 10e-6 = 18e-3
R_g = Ucc / I_g
    = 20 / 18e-3 = 1.11e3 =~ 1e3 =(E12) 1k ohm
```

## choix

IRF4905PbF

# transistor bloquage sens

## condition 

PNP

## quantité

1

## choix 

MPSA56

# calcul

Ic = 500 mA
Ib = Ic / 10 = 50 mA
U = 12 
Ube = 1.2
Ur = 10.8
R = 10.8 / 0.05 = 216 =(E12) 220
