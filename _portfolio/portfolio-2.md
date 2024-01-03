---
title: "Design of a Tower Crane for construction use"
excerpt: "<br/><img src='/images/complessivo.PNG' width='400px'>"
collection: portfolio
---

*Disclaimer: Everything below was done during my time at university, so it should be understood for educational purposes only. The following material has no real design purpose.*  

*As you will notice very often some calculations are omitted for matters of brevity, however I hold all the documentation on the calculations performed, feel free to contact me for clarification or curiosity, glad to answer if I can.*  
 
## 0. Technical Specifications  

![assieme-gru-01](/images/assieme-gru-01.png){:.align-left width="350px"}  
![assieme-gru-02](/images/assieme-gru-02.png){:.align-right width="350px"}  
![assieme-gru-05](/images/assieme-gru-05.png){:.align-left width="250px"}  
![assieme-gru-03](/images/assieme-gru-03.png){:.align-right width="350px"}  


![schema-gru](/images/schema-gru.jpg){:.align-center width="500px"}  

| Symbol | Description                         | Value  |
|--------|-------------------------------------|--------|
| H      | Maximum Height                      | 50 m   |
| h      | Maximum Load Lifting                | 40 m   |
| L      | Length of Arm + Counter-boom        | 60 m   |
| P      | Load at Maximum Extension           | 9800 N |

## 1. Introduction  

The project consists of the realization of a tower crane for construction use, the ideal configuration in such cases is that of a grafted-element crane, characterized by considerable heights, very long booms, and high load capacities. Therefore, the crane will consist of a vertical structure (**tower**) that consists of a metal truss that performs a static function of supporting the girder, the horizontal part is divided into the part intended for load distribution (**boom** / **arm**) and that for load balancing (**counter-boom**).  

## 2. Counter-boom  

![Blocchi di cemento](/images/Blocchidicemento.PNG){:.align-center width="300px"}  
![calcoli-gru02](/images/calcoli-gru02.jpeg){:.align-center width="400px"}  

| Component             | Symbol | Mass (kg) |
|-----------------------|--------|-----------|
| Arm Mass              | m_b    | 4600      |
| Counter-boom Mass     | m_c    | 4700      |
| Upper Structure Mass  | m_s    | 5200      |
| Trolley Mass          | -      | 76        |
| Block Mass            | -      | 28        |  

The mass of concrete blocks `𝑚_R` is calculated so as to minimize the distance of the center of mass from the axis of symmetry of the vertical crane structure so as to have a low overturning moment.  

The start and end positions of the carriage are considered: `𝑥_𝑄𝑖 = 2.5 𝑚` ; `𝑥_𝑄𝑓 = 42 𝑚` to find the coordinates of the center of mass:  

`x_G = (1 / m_tot) * (m_b * x_b + m_Q * x_Q - m_c * x_c - m_R * x_R)`  

A mass `𝑚_𝑅 = 10000 𝑘𝑔` is assumed, and by iteration `𝑥_𝐺` is kept as close to the origin as possible in the two configurations.  

After a few iterations, `𝑚_𝑅 = 9000 kg` is obtained as the distance in the two minimum configurations, resulting in a low overturning moment.  

`x_Gi = -0.88 m` 
`x_Gf = 0.89 m` 

## 3. Basement  

![assieme-gru-07](/images/assieme-gru-07.png){:.align-center width="200px"}  
![calcoli-gru06](/images/calcoli-gru06.jpeg){:.align-center width="400px"}  

Calculation of center of mass:  

`x_G = (1 / m_tot) * (m_b * x_b + m_Q * x_Q - m_c * x_c - m_R * x_R)`  

with m_tot = 43300 kg is obtained:  

`x_Gi = -0.5 m`   
`x_Gf = 0.5 m`   

Therefore, the overturning moment on the base is:  

`M_f,rot = 43300 kg x 9.81 m/s² x 0.5 m = 214.4 kN m`  

The resulting compression force transmitted to the ground is:  

`F_tot = 43300 kg x 9.81 m/s² = 424.8 kN`  

There are 4 supports for the tower, so the force on each beam is thus:  

`F = 424.8 kN / 4 = 106.2 kN`    

### Slewing ring   

![rallaruotadentata](/images/rallaruotadentata.PNG){:.align-center width="300px"}  

The slewing ring was selected from a manufacturers' catalog code: 'EB2.35.1249.400-1SPPN' with the characteristics shown in the table:  

| De   | de   | di   | Di   | Dx   | He   | Hi   | Ht   | Hd   | Fe   | Fi   | N    | V    | L    | W    | m    | Z    | Dp   |
|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|
| [mm] | [mm] | [mm] | [mm] | [mm] | [mm] | [mm] | [mm] | [mm] | [mm] | [-]  | [-]  |[mm]  | [-]  | [-]  | [mm] | [-]  | [mm] |
|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|
| 1472 | 1252 | 1246 | 1085 | 1406 | 134  | 134  | 144  | 115  | 1350 | 1150 | 36   | 28   | 41   | 27   | 14   | 102  | 1428 |  

Material of the ring: steel 42CrMo4 (`𝜎_𝑅 = 900 N/mm^2`)  

- Starting torque: `C_d = C_rv + C_rc`  
`C_rv` = idle resistance torque with compressed bearing components  
`C_rc` = constant rotation torque due to loads  

- Torque with acceleration: `C_g = C_rv + C_rc + C_a`  
`C_a` = acceleration torque  

*The calculations performed are omitted here for brevity*  

Resulting in:  
`C_rc = 3.7 kN m`  

From technical specifications the maximum rotational speed is equal to:  
`𝜔 = 0.7 rad/min = 0.01167 rad/s`  

For the moment of inertia, all the weight concentrated at the center of gravity of the entire structure is considered  
`I = m x d^2 = 19486 kg m^2`

Resulting in:  
`C_a = 0.227 kN m`

From a graph is obtained that:   
`C_rv = 0.5 kN m`  

So, finally:  
`C_d = 4.3 kN m` `C_g = 4.5 kN m`  

### Check   

Lastly a check was made of the slewing ring & drive wheel teeth, where the maximum torque to be transmitted is `C_g = 4.5 kN m`  

(*The calculations performed are omitted here for brevity*)  

### Check of the shaft of the drive wheel  

![Albero](/images/Albero.PNG){:.align-center width="250px"}  
![calcoli-gru13](/images/calcoli-gru13.jpeg){:.align-center width="300px"}  

Material of the shaft: steel 42CrMo4 (`𝜎_𝑅 = 900 N/mm^2`)  

(*The calculations performed are omitted here for brevity*)   

`M_f,max = 4250 kN mm`  
`M_t = 4760 kN mm`  

### Check of the screws   

![Bulloniralla](/images/Bulloniralla.PNG){:.align-center width="200px"}  

36 screws M27 x 155 - 8.8 (`𝜎_𝑅 = 800 N/mm^2`)  

A check was made both on compression and traction.  
(*The calculations performed are omitted here for brevity*)  

### Check of the rope for the trolley movement   

![carrello](/images/carrello.PNG){:.align-center width="300px"}  
![calcoli-gru09](/images/calcoli-gru09.jpeg){:.align-center width="450px"}  
![calcoli-gru07](/images/calcoli-gru07.jpeg){:.align-center width="300px"}  

A maximum carriage travel speed equal: `v = 40 m/min = 0.667 m/s` was choosen.  

The maximum force to be applied to move the trolley when the load is maximum:  

`F = 𝜇_𝑆 * 𝑃 = 0.4 * 10.8 kN = 4.32 kN`   

The rope is then chosen from a supplier's catalog that states the following:  

| Diameter of the rope [mm] | External wire diameter [mm] | Weight per meter [g] | Minimum breaking load [kN] |
|---------------------------|-----------------------------|----------------------|----------------------------|
| 5                         | 1.68                        | 125                  | 24.8                       |  

### Choice of the winch for the trolley movement

![Arganocarrellolungox](/images/Arganocarrellolungox.PNG){:.align-center width="450px"}  

### Check of the rope for the load lifting  

![calcoli-gru08](/images/calcoli-gru08.jpeg){:.align-center width="450px"}  

To verify the choice of rope used to lift the load, the maximum stresses acting on it are sought.    

(*The calculations performed are omitted here for brevity*)  

The same rope chosen for trolley movement is choosen.  

### Choice of the winch for the load lifting  

![Arganocarrellolungoz](/images/Arganocarrellolungoz.PNG){:.align-center width="450px"}  

### Check of the following shaft   

(*The calculations performed are omitted here for brevity*)  

![pernocatenabozzello](/images/pernocatenabozzello.PNG)<!--{:.align-left width="200px"}  
![pernopuleggiabozzello](/images/pernopuleggiabozzello.PNG)<!--{:.align-center width="200px"}  
![pernoruota](/images/pernoruota.PNG)<!--{:.align-right width="200px"}  

### Check of the bearing  

(*The calculations performed are omitted here for brevity*)  

![ruota](/images/ruota.PNG){:.align-center width="200px"}  

## 4. Study of the arm structure  

![braccio](/images/braccio.PNG){:.align-center width="300px"}  
![calcoli-gru19](/images/calcoli-gru19.jpeg){:.align-center width="300px"}  

The standard: UNI-EN 13001-2:2015 it was taken as a reference.  

This part required a lot of calculation. The structure was divided into elementary structures and equilibrium was made at each node. Some design assumptions were made.  

The wind force is neglected as a first approximation.  

Finally, the forces transmitted to the next part of the arm are calculated.   

To find the value of the tie-rod forces, equilibrium of moments is imposed on the complete boom structure with center of reduction at the attachment of the vertical structure.  

A better evaluation of the forces that also considers the effects of wind and different positions of the trolley along the boom can be done through a finite element analysis.  

Laslty a check on the weld of the arm connection plate was done.  

## 5. Study of the counter-boom

![Controbraccio](/images/Controbraccio.PNG){:.align-center width="300px"}  
![calcoli-gru20](/images/calcoli-gru20.jpeg){:.align-center width="300px"}  

A procedure similar to the previous arm but much more streamlined due to the lack of the triangle structure is carried out. Force distribution easier to understand.  

Laslty a check on the weld of the counter-boom connection plate was done.  

## 6. Bill of material  

| Number | Description                                   | Quantity | Material             |
|--------|-----------------------------------------------|----------|----------------------|
| 1      | Base Support                                  | 4        | steel S355           |
| 2      | Base Attachment Structure                     | 1        | steel S355           |
| 3      | Vertical Tower Structure                      | 12       | steel S355           |
| 4      | Access Platform                               | 6        | steel S355           |
| 5      | Ladder                                        | 7        | steel S355           |
| 6      | Ladder Protection                             | 7        | steel S355           |
| 7      | Roller Support Structure                      | 1        | steel S355           |
| 8      | Upper Roller Structure                        | 1        | steel S355           |
| 9      | Lower Roller Ladder                           | 1        | steel S355           |
| 10     | Upper Roller Ladder                           | 1        | steel S355           |
| 11     | Mobile Roller Ladder                          | 1        | steel S355           |
| 12     | Roller                                        | 1        | steel 42CrMo4        |
| 13     | Drive Wheel                                   | 1        | steel 42CrMo4        |
| 14     | Drive Wheel Shaft                             | 1        | steel 42CrMo4        |
| 15     | Lower Bearing Support                         | 1        | steel S355           |
| 16     | Upper Bearing Support                         | 1        | steel S355           |
| 17     | Bearing 214-Z                                 | 1        | \                    |
| 18     | Bearing 216-Z                                 | 1        | \                    |
| 19     | Motor Support Structure                       | 1        | steel S355           |
| 20     | Cabin Support Structure                       | 1        | steel S355           |
| 21     | Cabin                                         | 1        | steel S185           |
| 22     | Internal Arm Connection                       | 2        | steel S355           |
| 23     | External Arm Connection                       | 2        | steel S355           |
| 24     | Internal Counterarm Connection                | 2        | steel S355           |
| 25     | External Counterarm Connection                | 2        | steel S355           |
| 26     | Arm Locking System                            | 2        | steel S355           |
| 27     | Counterarm Locking System                     | 2        | steel S355           |
| 28     | Arm Locking Pin                               | 4        | steel 42CrMo4        |
| 29     | Counterarm Locking Pin                        | 4        | steel 42CrMo4        |
| 30     | Counterarm Coupling Plate Pin                 | 2        | steel S355           | 
| 31     | Counterarm Coupling Plate                     | 4        | steel S355           |
| 32     | Counterarm Structure                          | 1        | steel S355           |
| 33     | Counterarm Connecting Plate                   | 12       | steel S355           |
| 34     | Counterarm Tension Rod Attachment Plate       | 2        | steel S355           |
| 35     | Cement Block Bar                              | 6        | steel S355           |
| 36     | Small Cement Block                            | 2        | cement               |
| 37     | Large Cement Block                            | 4        | cement               |
| 38     | Parapet                                       | 23       | steel X 2 CrNi 12    |
| 39     | Lifting Winch                                 | 1        | \                    |
| 40     | Arm Coupling Plate                            | 4        | steel S355           |
| 41     | Arm Coupling Plate Pin                        | 2        | steel S355           |
| 42     | Initial Arm Structure                         | 1        | steel S355           |
| 43     | Arm Reticle Structure                         | 8        | steel S355           |
| 44     | Lower Arm Connecting Plate                    | 36       | steel S355           |
| 45     | Inner Arm Connecting Plate                    | 9        | steel S355           |
| 46     | Outer Arm Connecting Plate                    | 18       | steel S355           |
| 47     | Brace Connecting Plate                        | 2        | steel S355           |
| 48     | Tie Rod Support                               | 1        | steel S355           |
| 49     | Pulley Support                                | 9        | steel S355           |
| 50     | Pulley Pin                                    | 9        | steel 42CrMo4        |
| 51     | Trolley Drive Winch                           | 1        | \                    |
| 52     | Arm End Structure                             | 1        | steel S355           |
| 53     | Trolley Structure                             | 1        | steel S355           |
| 54     | Wheel                                         | 4        | cast iron S-NiCr20-3 |
| 55     | Wheel Pin                                     | 4        | steel 42CrMo4        |
| 56     | Bearing 6307-2RS1                             | 4        | \                    |
| 57     | Trolley Pulley Pin                            | 2        | steel 42CrMo4        |
| 58     | Pulley                                        | 12       | cast iron S-NiCr20-3 |
| 59     | Bearing 6005 2RSH                             | 24       | \                    |
| 60     | Block Structure                               | 1        | steel S355           |
| 61     | Block Pulley Pin                              | 1        | steel 42CrMo4        |
| 62     | Chain                                         | 1        | steel S355           |
| 63     | Chain/Block Connection                        | 1        | steel S355           |
| 64     | Hook Support                                  | 1        | steel S355           |
| 65     | Bearing 32010-X                               | 1        | \                    |
| 66     | Hook Connecting Plate                         | 1        | steel S355           |
| 67     | Hook                                          | 1        | cast iron S-NiCr20-3 |
| 68     | Traliccio Structure                           | 1        | steel S355           |
| 69     | Traliccio Platform                            | 1        | steel S355           |
| 70     | Tie Rod to Traliccio Tower Connection         | 1        | steel S355           |
| 71     | Tie Rod Connecting Plate                      | 1        | steel S355           |
| 72     | Counter-boom Tie Rod Plate                    | 1        | steel S355           |
| 73     | Short Counter-boom Tie Rod                    | 4        | steel S355           |
| 74     | Long Counter-boom Tie Rod                     | 2        | steel S355           |
| 75     | Tie Rod short (line 1) Arm                    | 2        | steel S355           |
| 76     | Tie Rod long (line 1) Arm                     | 4        | steel S355           |
| 77     | Tie Rod short (line 2) Arm                    | 2        | steel S355           |
| 78     | Tie Rod long (line 2) Arm                     | 2        | steel S355           |

