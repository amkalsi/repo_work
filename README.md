# repo\_work

Use MG5_aMC_v2_6_7  version should be linked with following versions of 

Delphes: Delphes-3.4.2

Pythia : 8.244

Madgraph version  : https://drive.google.com/file/d/1H-Kj0y29RlA2NVm1Fo59JpZ_ovQlLvnK/view?usp=sharing

These versions should be downloaded from the official pages ( they are present here for record purposes)

Also note : https://answers.launchpad.net/mg5amcnlo/+question/697789


instructions to make samples


The signal samples must generated in grid of lambda1 and lambda2 , change mass of X1 and mX2 too in param_card.dat


(  Here in param_card.dat file 

Block np 
    
    1 1.000000e+00 # lam1Norm 
    
    2 1.000000e+00 # lam2Norm 

)
    

One needs to edit four files param\_card.dat, run\_card.dat, delphes\_card.dat , pythia8_card.dat


Commands to generate signal samples; 

Signal
-------------------------------------------------------------------------------------

import model sm

define p = g u c d s u~ c~ d~ s~

define j = g u c d s u~ c~ d~ s~

define l+ = e+ mu+

define l- = e- mu-

define vl = ve vm vt

define vl~ = ve~ vm~ vt~

import model BaryogenX2N1Maj\_withLeft

define p = 21 2 4 1 3 -2 -4 -1 -3 5 -5 # pass to 5 flavors

define j = p

define bot = b b~

define x = x1 x1~ x2 x2~

generate p p > x bot, x > n j

add process p p > x bot j, x > n j

add process p p > x bot j j, x > n j

output SignalDirName



----------------------------------------------------------------------------------------------------
--- ZZ -----



import model sm-no_b_mass

define p = 21 2 4 1 3 -2 -4 -1 -3 5 -5 # pass to 5 flavors

define j = p

define l+=e+ mu+ ta+

define l-= e- mu- ta-

generate p p > z z, z > l+ l-, z > l+ l- $$ t t~ h @0

add process p p > z z, z > l+ l-, z > j j $$ t t~ h @1

add process p p > z z, z > j j, z > j j $$ t t~ h @2

output ZZ\_new


-------------------------------------------------------------------------------------------------------

WW2L2Nu




import model sm-no_b_mass

define p = 21 2 4 1 3 -2 -4 -1 -3 5 -5 # pass to 5 flavors

define j = p

define l+=e+ mu+ ta+

define l-= e- mu- ta-

generate p p > w+ w-, w+ > l+ vl, w- > l- vl~ $$ t t~ h @0

output WW2Lvv_new



-------------------------------------------------------------------------------------------------------

WZ3LNu



import model sm-no_b_mass

define p = 21 2 4 1 3 -2 -4 -1 -3 5 -5 # pass to 5 flavors

define j = p

define l+=e+ mu+ ta+

define l-= e- mu- ta-

generate p p > w+ z, w+ > l+ vl, z > l+ l-

add process p p > w- z, w- > l- vl~, z > l+ l-

output WZ3Lv


-------------------------------------------------------------------------------------------------------
WWLvQQ




import model sm-no_b_mass

define p = 21 2 4 1 3 -2 -4 -1 -3 5 -5 # pass to 5 flavors

define j = p

define l+=e+ mu+ ta+

define l-= e- mu- ta-

generate p p > w+ w-, w+ > l+ vl, w- > j j $$ t t~ h@0

add process p p > w+ w-, w+ > j j, w- > l- vl~ $$ t t~ h@1

output WWLvQQ


-------------------------------------------------------------------------------------------------------
WZ2L2Q



import model sm-no_b_mass

define p = 21 2 4 1 3 -2 -4 -1 -3 5 -5 # pass to 5 flavors

define j = p

define l+=e+ mu+ ta+

define l-= e- mu- ta-

define V = w+ w-

generate p p > V z, V > j j, z > l+ l-

output WZ2L2Q

------------------------------------------------------------------------------------------------------
WZLvQQ


import model sm-no_b_mass

define p = 21 2 4 1 3 -2 -4 -1 -3 5 -5 # pass to 5 flavors

define j = p

define l+=e+ mu+ ta+

define l-= e- mu- ta-

generate p p > w+ z, z > j j, w+ > l+ vl $$ t t~ h@0

add process p p > w- z, z > j j, w- > l- vl~ $$ t t~ h@1

output WZLvQQ

-------------------------------------------------------------------------------------------------------
TT3Jets


import model sm-no_b_mass

define p = 21 2 4 1 3 -2 -4 -1 -3 5 -5

define j = p

define l+=e+ mu+ ta+

define l-= e- mu- ta-

generate p p > t t~ @0

add process p p > t t~ j @1

add process p p > t t~ j j @2

add process p p > t t~ j j j @3

output Feb24_ttjets_v1

-------------------------------------------------------------------------------------------------------
Z3Jets


import model sm-no_b_mass

define p = 21 2 4 1 3 -2 -4 -1 -3 5 -5 # pass to 5 flavors

define j = p

define l+ = e+ mu+ ta+

define l- = e- mu- ta-

generate p p > z, z > vl vl~ @0

add process p p > z j, z > vl vl~ @1

add process p p > z j j, z > vl vl~ @2

add process p p > z j j j, z > vl vl~ @3

output Z_3Jets
-------------------------------------------------------------------------------------------------------

W3Jets


import model sm-no_b_mass

define p = 21 2 4 1 3 -2 -4 -1 -3 5 -5 # pass to 5 flavors

define j = p

define l+=e+ mu+ ta+

define l-= e- mu- ta-

generate p p > w+, w+ > l+ vl @0

add process p p > w+ j, w+ > l+ vl @1

add process p p > w+ j j, w+ > l+ vl @2

add process p p > w- , w- > l- vl~ @3

add process p p > w- j, w- > l- vl~ @4

add process p p > w- j j, w- > l- vl~ @5

add process p p > w+ j j j, w+ > l+ vl @6

add process p p > w- j j j, w- > l- vl~ @7

output W_3Jets



-------------------------------------------------------------------------------------------------------



