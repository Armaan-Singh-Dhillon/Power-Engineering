# Program-1

## (A) Single phase lines

### Aim : To find GMD and GMR using matlab code

### Theory

**Geometric Mean Radius (GMR):**  
The GMR represents the effective radius of conductors in a single-phase transmission line bundle. It's calculated as the geometric mean of individual conductor radii. Formula: `GMR = √(r₁ * r₂ * ... * rₙ)`.

**Geometric Mean Distance (GMD):**  
The GMD quantifies conductor spacing's equivalent effect on capacitance and inductance. It's found using `GMD = (d₁ * d₂ * ... * dₙ)^(1/n)`.

Both GMR and GMD influence line parameters. Determine conductor arrangement, plug into formulas, and use these values in line parameter calculations for analyzing transmission line behavior. In practical cases, consider more complexities and simulations for accuracy.

### Code

```Matlab
% SINGLE PHASE LINE
clc;
clear all;
D=input('distance between two conductors = ');
r=input('radius of conductor = ');
GMD=D;GMR=0.7788*r;
GMR
GMD
```

### Result

```Matlab
distance between two conductors = 10
radius of conductor = 2

GMD =

    10


GMR =

    1.5576

```

## (B) Three phase lines

## (i) Symmetrical spacing

### Aim : To find GMD and GMR using matlab code

### Theory

**Three-Phase Symmetrical Spacing:**

For a three-phase symmetrical spacing in a transmission line, the formulas for Geometric Mean Radius (GMR) and Geometric Mean Distance (GMD) are as follows:

**GMR Formula:**
GMR = √(r₁ _ r₂ _ r₃)

**GMD Formula:**
GMD = (d₁ _ d₂ _ d₃)^(1/3)

### Code

```Matlab
% THREE PHASE SYMMETRICAL LINE
clc;
clear all;
D=input('distance between any two conductors = ');
r=input('radius of conductor = ');
GMD=D;GMR=0.7788*r;
GMR
GMD
```

### Result

```Matlab
distance between two conductors = 45
radius of conductor = 3

GMR =

    2.3364


GMD =

    45

```

## (ii) Asymmetrical spacing

### Aim : To find GMD and GMR using matlab code

### Code

```Matlab
% ASYMETRECAL SPACING
clc;
clear all;
r=input('radius of conductor = ');;
Dab=6;Dac=12;Dbc=6;Dba=Dab;Dca=Dac;Dcb=Dbc;
GMD=(Dab*Dac*Dbc*Dba*Dca*Dcb)^(1/6);
GMR=0.7788*r;
GMR
GMD
```

### Result

```Matlab
radius of conductor = 1.8

GMR =

    1.4018


GMD =

    7.5595

```

## (iii) Bundled Conductor

### Aim : To find GMD and GMR matlab code

### Theory

A **bundled conductor** refers to the arrangement of two or more individual conductors, like wires or cables, grouped together in a parallel configuration. This approach boosts the collective current-carrying capacity, reduces losses linked to skin effect and proximity effect, and curbs electromagnetic interference. Particularly valuable in high-voltage transmission lines, bundled conductors facilitate efficient power conveyance over extensive distances while curtailing energy dissipation.

The expanded surface area of these conductors also improves heat dispersion, ensuring dependable and consistent electrical transmission crucial for contemporary power grids.

### Code

```Matlab
% BUNDLED CONDUCTOR
clc;
clear all;
Daa=0.016*0.7788;
Da1a1=Daa;
Daa1=0.45;Da1a=0.45;
GMR=(Daa*Daa1*Da1a1*Da1a)^(1/4);
dab=12;dab1=12.45;da1b=11.55;da1b1=12;
Dab=(dab*dab1*da1b*da1b1)^(1/4);
Dbc=Dab;
dca=24;dca1=23.55;dc1a=24.45;dc1a1=24;
Dca=(dca*dca1*dc1a*dc1a1)^(1/4);
GMD=(Dab*Dbc*Dca)^(1/3);
GMR
GMD
```

### Result

```Matlab
radius of conductor = 1.8

GMR =

    0.0749


GMD =

   15.1151

```

## (iii) Double Circuit Lines

### Aim : To find GMD and GMR matlab code

### Theory

A **double circuit line** pertains to an arrangement where two separate sets of conductors, often with their own phases or functions, are operated in parallel on the same transmission tower or infrastructure. This design optimizes the utilization of transmission infrastructure and land resources.

Double circuit lines find significant application in high-voltage transmission networks, providing an efficient means to transmit large amounts of electricity across extended distances.

### Code

```Matlab
% DOUBLE CIRCUIT VERTICAL CONFIGURATION
clc;
clear all;
E0=8.854187817*10^-12;
r=input('enter radius of conductor = ');
h=input('enter the distance between b and b1 = ');
m=input('enter distance between a and b1 = ');
n=input('enter distance between a and a1 or c and c1 = ');
D=input('enter the distance between a and b1 = ');
r1=0.7788*r;
Dsa=sqrt(r1*n);Dsb=sqrt(r1*h);Dsc=Dsa;
GMR=(Dsa*Dsb*Dsc)^(1/3);
Dab=sqrt(D*m);
Dbc=Dab;Dca=sqrt(2*D*h);
GMD=(Dab*Dbc*Dca)^(1/3);
GMR
GMD
```

### Result

```Matlab
enter radius of conductor = 2
enter the distance between b and b1 = 10
enter distance between a and b1 = 20
enter distance between a and a1 or c and c1 = 30
enter the distance between a and b1 = 10

GMR =

    5.6920


GMD =

   14.1421

```

## (B)Find inductance and capacitance

## (i) Single phase lines

### Aim : To find inductance and capacitance using matlab code.

### Theory

Calculating **capacitance** and **inductance** using Geometric Mean Distance (GMD) and Geometric Mean Radius (GMR) involves formulas that account for conductor arrangement. For capacitance per unit length (C'), use `C' = 2πε / ln(GMD / GMR)`, considering permittivity (ε). For inductance per unit length (L'), use `L' = μ / (2π) * ln(GMD / GMR)`, with permeability (μ). GMD is the geometric average of conductor spacings, while GMR represents the geometric mean of conductor radii. These calculations provide insights into electrical parameters based on conductor geometry, aiding in designing efficient power systems.

### Code

```Matlab
% SINGLE PHASE LINE
clc;
clear all;
D=input('distance between two conductors = ');
r=input('radius of conductor = ');
E0=8.854187817*10^-12;
GMD=D;GMR=0.7788*r;
L=4*(10^-7)*log(GMD/GMR);
disp('SINGLE PHASE LINE INDUCTANCE AND CAPACITANCE');
L
C=2*pi*E0/(log(GMD/GMR));

C
```

### Result

```Matlab
distance between two conductors = 56
radius of conductor = 1.7
SINGLE PHASE LINE INDUCTANCE AND CAPACITANCE
L = 1.4979e-06
C = 1.4856e-11

```

## (ii) Three phase symmetrical lines

### Aim : To find inductance and capacitance using matlab code.

### Code

```Matlab
% THREE PHASE LINE
clc;
clear all;
D=input('distance between any two conductors = ');
r=input('radius of conductor = ');
E0=8.854187817*10^-12;
GMD=D;GMR=0.7788*r;
L=2*(10^-7)*log(GMD/GMR)*(10^3);    % H/Km per phase
disp('THREE PHASE LINE INDUCTANCE AND CAPACITANCE');
L
C=2*pi*E0/(log(GMD/GMR));
C
```

### Result

```Matlab
distance between any two conductors = 34
radius of conductor = 1.6
THREE PHASE LINE INDUCTANCE AND CAPACITANCE
L =   6.6127e-04
C = 1.6826e-11

```

## (iii) Three phase asymmetrical lines

### Aim : To find inductance and capacitance using matlab code.

### Code

```Matlab
% ASYMETRECAL SPACING
clc;
clear all;
r=1.81*10^-2;
E0=8.854187817*10^-12;
Dab=6;Dac=12;Dbc=6;Dba=Dab;Dca=Dac;Dcb=Dbc;
GMD=(Dab*Dac*Dbc*Dba*Dca*Dcb)^(1/6);
GMR=0.7788*r;
L=2*(10^-7)*log(GMD/GMR)*(10^3);    % H/Km per phase
disp('ASYMETRICAL SPACING INDUCTANCE AND CAPACITANCE');
L
C=2*pi*E0/(log(GMD/GMR));
C
```

### Result

```Matlab
ASYMETRICAL SPACING INDUCTANCE AND CAPACITANCE
L =    0.0013
C =   8.8521e-12

```

## (iii) Bundled Conductors

### Aim : To find inductance and capacitance using matlab code.

### Code

```Matlab
% BUNDLED CONDUCTOR
clc;
clear all;
E0=8.854187817*10^-12;
Daa=0.016*0.7788;
Da1a1=Daa;
Daa1=0.45;Da1a=0.45;
GMR=(Daa*Daa1*Da1a1*Da1a)^(1/4);
dab=12;dab1=12.45;da1b=11.55;da1b1=12;
Dab=(dab*dab1*da1b*da1b1)^(1/4);
Dbc=Dab;
dca=24;dca1=23.55;dc1a=24.45;dc1a1=24;
Dca=(dca*dca1*dc1a*dc1a1)^(1/4);
GMD=(Dab*Dbc*Dca)^(1/3);
L=2*(10^-7)*log(GMD/GMR)*(10^3);    % H/Km per phase
disp('BUNDLED CONDUCTOR INDUCTANCE AND CAPACITANCE');
L
C=2*pi*E0/(log(GMD/GMR));
C
r=sqrt(2)*0.016;r1=0.7788*r;
GMR=r1;
Dab=12;Dbc=12;Dca=24;Dba=12;Dcb=12;Dac=24;
GMD=(Dab*Dbc*Dca*Dba*Dcb*Dac)^(1/6);
L=2*(10^-7)*log(GMD/GMR)*(10^3);    % H/Km per phase
disp('INDUCTANCE AND CAPACITANCE WITH ONLY ONE CONDUCTOR PER
PHASE');
L
C=2*pi*E0/(log(GMD/GMR));
C
```

### Result

```Matlab
distance between any two conductors = 34
radius of conductor = 1.6
THREE PHASE LINE INDUCTANCE AND CAPACITANCE
L =   6.6127e-04
C = 1.6826e-11

```

## (iii) Three phase asymmetrical lines

### Aim : To find inductance and capacitance using matlab code.

### Code

```Matlab
% ASYMETRECAL SPACING
clc;
clear all;
r=1.81*10^-2;
E0=8.854187817*10^-12;
Dab=6;Dac=12;Dbc=6;Dba=Dab;Dca=Dac;Dcb=Dbc;
GMD=(Dab*Dac*Dbc*Dba*Dca*Dcb)^(1/6);
GMR=0.7788*r;
L=2*(10^-7)*log(GMD/GMR)*(10^3);    % H/Km per phase
disp('ASYMETRICAL SPACING INDUCTANCE AND CAPACITANCE');
L
C=2*pi*E0/(log(GMD/GMR));
C
```

### Result

```Matlab
BUNDLED CONDUCTOR INDUCTANCE AND CAPACITANCE
L =    0.0011
C =   1.0482e-11

INDUCTANCE AND CAPACITANCE WITH ONLY ONE CONDUCTOR PER PHASE
L =   0.0014
C =   8.2363e-12

```

## (iv) Double circuit vertical configuration

### Aim : To find inductance and capacitance using matlab code.

### Code

```Matlab
% DOUBLE CIRCUIT VERTICAL CONFIGURATION
clc;
clear all;
E0=8.854187817*10^-12;
r=input('enter radius of conductor = ');
h=input('enter the distance between b and b1 = ');
m=input('enter distance between a and b1 = ');
n=input('enter distance between a and a1 or c and c1 = ');
D=input('enter the distance between a and b1 = ');
r1=0.7788*r;
Dsa=sqrt(r1*n);Dsb=sqrt(r1*h);Dsc=Dsa;
GMR=(Dsa*Dsb*Dsc)^(1/3);
Dab=sqrt(D*m);
Dbc=Dab;Dca=sqrt(2*D*h);
GMD=(Dab*Dbc*Dca)^(1/3);
L=2*(10^-7)*log(GMD/GMR)*(10^3);    % H/Km per phase
disp('INDUCTANCE AND CAPACITANCE OF DOUBLE CIRCUIT VERTICAL
CONFIGURATION');
L
C=2*pi*E0/(log(GMD/GMR));
C
```

### Result

```Matlab
enter radius of conductor = 1.6
enter the distance between b and b1 = 12
enter distance between a and b1 = 12
enter distance between a and a1 or c and c1 = 12
enter the distance between a and b1 = 12
INDUCTANCE AND CAPACITANCE OF DOUBLE CIRCUIT VERTICAL
CONFIGURATION
L =  2.4960e-04
C =  4.4578e-11

```
