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

Commander les relais

## Décisions

PNP car les relais ont la masse commune forcée par le fonctionement du circuit.
...

## Choix

...

# Resistance base du transistor precedents

## qte par PCB

2 ou 0 selon configuration

# conditions 

THT

## calculs

...

# 555

## qte par PCB 

1 ou 0 selon configuration

## conditions 

THT

# potentiometre

## condition

Avec au moins 1 interrupteurs
4.7 kohm ou 5 kohm linéraire (conservé le même composants)
~300° de rotation

## choix

...

# condensateur de charge décharge

# conditions

céramique si la valeur existe, sinon à film
dimensionné pour 1 kHz (Arduino environ 500 Hz ou 1kHz)

# calculs

```
C = 1 / (0.693 * Rpot * f)
  = 1 / (0.693 * 4700 * 1000) = 307 nF =(E12) 270 nF 
```

# choix

...

# transistor driver MOSFET

# qte sur le PCB

1 

## descisions

NPN car MOSFET est de type P

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

# choix

...

# MOSFET

## conditions

U_ds_max > 24 VDC
I_d_max > 3 A
U_gs_max > 12 VDC
R_ds_on << 1 ohm

## descision

type P pour correspondre au fonctionnement des autres alimentations et éviter les saut de tension aux changement d'alimentations

## choix

IRF4905PbF

# condensateur de découplage

## qte par PCB

1 ou 0 selon configuration

## choix

...



