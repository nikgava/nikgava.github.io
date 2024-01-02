---
title: "Design of a Tower Crane for construction use"
excerpt: "<br/><img src='/images/complessivo.PNG' width='400px'>"
collection: portfolio
---

*Disclaimer: Everything below was done during my time at university, so it should be understood for educational purposes only. The following material has no real design purpose.*

## 1. Technical Specifications  

![schema-gru](/images/schema-gru.jpg){:.align-center width="500px"}  

| Symbol | Description                         | Value  |
|--------|-------------------------------------|--------|
| H      | Maximum Height                      | 50 m   |
| h      | Maximum Load Lifting                | 40 m   |
| L      | Length of Arm + Counter-boom        | 60 m   |
| P      | Load at Maximum Extension           | 9800 N |

## 1. Introduction  

The project consists of the realization of a tower crane for construction use, the ideal configuration in such cases is that of a grafted-element crane, characterized by considerable heights, very long booms, and high load capacities. Therefore, the crane will consist of a vertical structure (**tower**) that consists of a metal truss that performs a static function of supporting the girder, the horizontal part is divided into the part intended for load distribution (**boom**) and that for load balancing (**counter-boom**).  

### 2. Counter-boom  

![Blocchi di cemento](/images/Blocchidicemento.PNG){:.align-center width="300px"}  
![calcoli-gru02](/images/calcoli-gru02.jpeg){:.align-center width="400px"}  

| Component             | Symbol | Mass (kg) |
|-----------------------|--------|-----------|
| Arm Mass              | m_b    | 4600      |
| Counter-boom Mass     | m_c    | 4700      |
| Upper Structure Mass  | m_s    | 5200      |
| Trolley Mass          | -      | 76        |
| Block Mass            | -      | 28        |  

The mass of concrete blocks 𝑚_R is calculated so as to minimize the distance of the center of mass from the axis of symmetry of the vertical crane structure so as to have a low overturning moment.  

The start and end positions of the carriage are considered: 𝑥_𝑄𝑖=2.5 𝑚 ; 𝑥_𝑄𝑓=42 𝑚 to find the coordinates of the center of mass:  

`x_G = (1 / m_tot) * (m_b * x_b + m_Q * x_Q - m_c * x_c - m_R * x_R)`  

A mass 𝑚_𝑅=10000 𝑘𝑔 is assumed, and by iteration 𝑥_𝐺 is kept as close to the origin as possible in the two configurations.  

After a few iterations, 𝑚𝑅=9000 kg is obtained as the distance in the two minimum configurations, resulting in a low overturning moment.  

x_Gi = -0.88 m 
x_Gf = 0.89 m 

### 2. Basement  

![assieme-gru-07](/images/assieme-gru-07.png){:.align-center width="300px"}  
![calcoli-gru06](/images/calcoli-gru06.jpeg){:.align-center width="400px"}  

Calculation of center of mass:  

`x_G = (1 / m_tot) * (m_b * x_b + m_Q * x_Q - m_c * x_c - m_R * x_R)`  

with m_tot = 43300 kg is obtained:  

x_Gi = -0.5 m   
x_Gf = 0.5 m   

Therefore, the tipping moment on the base is:  

`M_f,rot = 43300 kg x 9.81 m/s² x 0.5 m = 214.4 kN m`  

The resulting compression force transmitted to the ground is:  

`F_tot = 43300 kg x 9.81 m/s² = 424.8 kN`  

There are 4 supports for the tower, so the force on each beam is thus:  

`F = 424.8 kN / 4 = 106.2 kN`  













