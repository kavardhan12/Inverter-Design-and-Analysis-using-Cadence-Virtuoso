>*Design of Inverter using NMOS and PMOS and their detailed analysis along with the Characteristics of NMOS and PMOS*

This basic project acts as a bridge and a guide for the usage of EAD tool Cadence Virtuoso and also gives us an insight about the Inverter properties, NMOS characteristics, PMOS characteristics. In the initial stages we will go for the characteristics of NMOS transistor, then PMOS transistor and later the Inverter. This project is performed fully in Cadence Virtuoso with instantiation of a new user created library in gpdk 090 technology.
# *Contents*
## 1. NMOS Characteristics
	1.1 Creating a Schematic
	1.2 DC Analysis - Id vs Vds plot (constant Vgs)
	1.3 DC Analysis - Id vs Vds plot (varying Vgs)
	1.4 DC Analysis - Id vs Vgs plot (constant Vds)
	1.5 DC Analysis - Id vs Vgs plot (varying Vds)
	1.6 Giving most negative voltage to body to reduce body effect
	1.7 Variation for voltages less than Vth
	1.8 Variation of Id and Vgs plot on parametrically varying Vsb
## **2. PMOS Characteristics**
	2.1 Creating a Schematic
	2.2 DC Analysis - Id vs Vsd plot (constant Vsg)
	2.3 DC Analysis - Id vs Vsd plot (varying Vsg)
	2.4 DC Analysis - Id vs Vsg plot (constant Vsd)
	2.5 DC Analysis - Id vs Vsg plot (varying Vsd)
	2.6 Giving most positive voltage to body to reduce body effect
	2.7 Variation for voltages less than Vth
	2.8 Variation of Id and Vsg plot on parametrically varying Vsb
## **3. NMOS Pass Transistor Logic**
	3.1. Creating a Schematic
	3.2. Transient Analysis of Vin and Vout
## **4. PMOS Pass Transistor Logic**
	4.1. Creating a Schematic
	4.2. Transient Analysis of Vin and Vout
## **5. NMOS Propagation Delay (tpHL)**
	5.1. Creating a schematic
	5.2. Transient Analysis of Vin and Vout
	5.3. Calculating the mathematical value of Delay (tpHL)
## **6. PMOS Propagation Delay (tpLh)**
	6.1. Creating a schematic
	6.2. Transient Analysis of Vin and Vout
	6.3. Calculating the mathematical value of Delay (tpLH)
## **7. Transmission Gate**
	7.1. Creating a Schematic
	7.2. Creating a Symbol
	7.3. Creating a Symbol’s Testbench
	7.4 Analysis of the gate
	7.5 Delay of Tx Gate
## 8. INVERTER Characteristics
	8.1 Creating the Schematic
	8.2 Creating the Symbol of Inverter
	8.3 Creating the symbol’s testbench
	8.4 Analysis of Inverter (Transient, DC analysis)
## 9. Switching Threshold of Inverter (for same mid voltage for Vin=Vout=(Vdd/2))
## 10. Inverter same rise time and fall time (wpn for same rise time and fall time)
## 11. Noise Margin of Inverter




## 1. NMOS Characteristics

### **1.1. Creating a Schematic**

Add the instances like NMOS, 2 Vdc voltages for Vgs and Vds and add ground to all 4 terminals.

![](New%20folder/Pasted%20image%2020231022125842.png)

![[New%20folder/Pasted image 20231022125859.png]]
### **1.2. DC Analysis - Id vs Vds plot (constant Vgs)**

With constant Vgs as 1v and varying Vds to produce Id (one plot only).
For current choose node and for voltage choose wire in schematic.

![[New folder/Pasted image 20231022130337.png]]
### **1.3 DC Analysis - Id vs Vds plot (varying Vgs)**

With varying Vgs (changing it to Vgs in edit properties of Vgs symbol), giving it as a parameter by initializing it in the variable box in the ADE L window and giving it some parametric values.

![[Pasted image 20231022130529.png]]

![[Pasted image 20231022130543.png]]
### **1.4 DC Analysis - Id vs Vgs plot (constant Vds)**

With constant Vds as 1v and varying Vgs to produce Id (one plot only).

![[Pasted image 20231022130620.png]]
### **1.5 DC Analysis - Id vs Vgs plot (varying Vds)**

Changing the value of Vds=1v to parametric Vds value and adding it in the ADE L window variable part, initializing it and then giving it some parametric points to produce multiple Id vs Vgs plots for varying Vds for different plots by varying Vgs in each plot.

![[Pasted image 20231022130650.png]]
### **1.6 Giving most negative voltage to body to reduce body effect**

We give the body terminal the most negative voltage that is produced by the same Vdc block to reduce the body effect and naming it Vsb. Now we find the same above Id vs Vgs plot.

![[Pasted image 20231022130748.png]]

![[Pasted image 20231022130804.png]]

![[Pasted image 20231022130833.png]]

### **1.7 Variation for voltages less than Vth**

Before the threshold voltage is reached there will be slight variation in current and that slight variation can be observed changing the Y-axis scale to log scale.

![[Pasted image 20231022130941.png]]

![[Pasted image 20231022130950.png]]

**Note:** In Cadence Virtuoso tool there will be an error shown if we declare a parameter as variable in schematics and doesn’t instantiate it in the ADE L window.
### **1.8 Variation of Id and Vgs plot on parametrically varying Vsb**

Parametrically varying the value of Vsb for each graph to produce Id and Vgs plot. As the Vsb increases the curve shifts towards right.

![[Pasted image 20231022131428.png]]

## **2. PMOS Characteristics**
## **2.1. Creating a Schematic**

Add the instances like PMOS, 2 Vdc (one Vsg and other Vsd) voltages and ground. We note that for PMOS source should have most positive terminal and body should be connected as so.
![[Pasted image 20231022131951.png]]

![[Pasted image 20231022132005.png]]
## **2.2. DC Analysis - Id vs Vsd plot (constant Vsg)**

With constant Vsg as 1v and varying Vsd to produce Id (one plot only), the graph will generally be reverse i.e., in 3rd quadrant. So, we take the reference point to check output current as source. This gives a normal NMOS type graph in 1st quadrant but for PMOS parameters.
![[Pasted image 20231022132038.png]]

![[Pasted image 20231022132048.png]]
## **2.3 DC Analysis - Id vs Vsd plot (varying Vsg)**

With varying Vsg (changing value to Vsg in edit properties of Vsg symbol), giving it as a parameter by initializing it in the variable box in the ADE L window and giving it some parametric values.

![[Pasted image 20231022132116.png]]

![[Pasted image 20231022132123.png]]
## **2.4 DC Analysis - Id vs Vsg plot (constant Vsd)**

With constant Vsd as 1v and varying Vsg to produce Id (one plot only).

![[Pasted image 20231022132215.png]]

## **2.5 DC Analysis - Id vs Vsg plot (varying Vsd)**

Changing the value of Vsd=1v to parametric Vsd value and adding it in the ADE L variable part i.e., initializing it and then we give it some parametric points to produce multiple Id vs Vsg plots for varying Vsd for different plots by varying Vsg in each plot.

![[Pasted image 20231022132309.png]]

## **2.6 Giving most positive voltage to body to reduce body effect**

We give the body terminal the most positive voltage that is produced by the same Vdc block to reduce the body effect and naming it Vbs. And now we find the same above plot.

![[Pasted image 20231022132338.png]]


## **2.7 Variation for voltages less than Vth**

Before the threshold voltage only there will be slight variation in current and that slight variation can be observed changing the Y-axis scale to log scale.

![[Pasted image 20231022132706.png]]

## **2.8 Variation of Id and Vsg plot on parametrically varying Vsb**

On parametrically varying the value of Vsb for each graph to produce Id and Vsg plot. As the Vsb increases the curve shifts towards right.

## **3. NMOS Pass Transistor Logic**          
### 3.1. Creating a Schematic

Add the instances like NMOS, 1 Vdc for Vgs and other Vpulse for Vss voltages and add ground.  We note that for NMOS source should have most negative terminal and body should be connected as so.
!![[Pasted image 20231022134512.png]]

### 3.2. Transient Analysis of Vin and Vout

Here in the ADE L window, we provide a transient analysis giving the outputs as voltages selecting wires in the schematics (Vin and Vout).

![[Pasted image 20231022134523.png]]

![[Pasted image 20231022134545.png]]

## **4. PMOS Pass Transistor Logic**

### **4.1. Creating a Schematic**

Add the instances like NMOS, 1 Vdc for Vsg and other Vpulse for Vss voltages and add ground.  We note that for PMOS source should have most positive terminal and body should be connected as so.

![[Pasted image 20231022135209.png]]

### 4.2. Transient Analysis of Vin and Vout 

Here in the ADE L window, we provide a transient analysis giving the outputs as voltages selecting wires in the schematics (Vin and Vout).

![[Pasted image 20231022135221.png]]

## 5. NMOS Propagation Delay (tpHL)

![[Pasted image 20231022135234.png]]
### 5.1. Creating a schematic

Add the instances like NMOS, 1 Vpulse for Vgs voltages and add ground. As we are finding the timing delays so we find the time taken by discharging and charging the capacitor and we connect it to the drain terminal initially charging to a 1pf in the case of tpHL for NMOS or leaving it uncharged in the case of tpLH for PMOS. We note that for NMOS, source should have most negative terminal and body should be connected as so.

![[Pasted image 20231022135308.png]]

### 5.2. Transient Analysis of Vin and Vout**

Here in the ADE L window, we provide a transient analysis giving the outputs as voltages selecting wires in the schematics (Vin and Vout) for only one clock cycle to observe the rise and fall of inputs and outputs respectively.

![[Pasted image 20231022135320.png]]

### 5.3. Calculating the mathematical value of Delay (tpHL)

In the calculator we find the mathematical delay between the rising input signal and falling output signal.

![[Pasted image 20231022135337.png]]

## **6. PMOS Propagation Delay (tpLh)**
### 6.1. Creating a schematic**

Add the instances like PMOS, 1 Vpulse for Vsg voltages and add ground. As we are finding the timing delays so we find the time taken by discharging and charging the capacitor and we connect it to the drain terminal initially charging to a 1pf in the case of tpHL for NMOS or leaving it uncharged in the case of tpLH for PMOS. We note that for PMOS, source should have most positive terminal and body should be connected as so.  As we are charging the capacitor so, we need to give the capacitor some charge during the process so for this we give some Vdc voltage at source terminal of PMOS.

![[Pasted image 20231022135355.png]]
### 6.2. Transient Analysis of Vin and Vout**

Here in the ADE L window, we provide a transient analysis giving the outputs as voltages selecting wires in the schematics (Vin and Vout) for only one clock cycle to observe the fall and rise of inputs and outputs respectively.

![[Pasted image 20231022135405.png]]
### 6.3. Calculating the mathematical value of Delay (tpLH)**

In the calculator we find the mathematical delay between the falling input signal and rising output signal.

![[Pasted image 20231022135426.png]]

**Here we can observe an important thing i.e., the PMOS have a great delay as compared to the NMOS. This implies that the PMOS has less mobility holes than the NMOS electrons and thus in circuits we use the physical properties of PMOS greater than or equal to twice the NMOS.  And this is the reason that NMOS is strong 0 producing and PMOS is strong 1 producing.**

## **7. Transmission Gate**

![[Pasted image 20231022135442.png]]
### 7.1. Creating a Schematic**

Add instances like NMOS, PMOS, base terminal Vdc voltage and ground. Also provide it the reference gate voltages to produce the output.

![[Pasted image 20231022135510.png]]
### 7.2. Creating a Symbol**

Create the symbol from the cell view window.

![[Pasted image 20231022135523.png]]
### 7.3. Creating a Symbol’s Testbench**

In a new cell view window create a testbench for the Txgate and give it the voltages for the input as a pulse and S, Sbar as 1 and 0 respectively with Vdc and ground voltages respectively to switch on the circuit. We put on the both because strong 1 is passed by PMOS and strong 0 is passed by NMOS.

![[Pasted image 20231022135534.png]]
### 7.4 Analysis of the gate**

**Without Capacitor:** In this case the output will be superimposed on the input.

![[Pasted image 20231022135546.png]]

**With Capacitor:** In this case the capacitor provides some delay and can be represented in the transient analysis. Although we will get the full voltage swing. If we don’t, we need to give more Vpulse period such that the cap will have time to gain the charge and lose the charge and this also depends on the capacity of the capacitor. 

![[Pasted image 20231022135617.png]]
### 7.5 Delay of Tx Gate**

In the calculator selecting the delay function and both the signal we can find the mathematical delay of the Txgate. We find both rising delay and falling delay. Rising delay is more than falling delay due to NMOS and PMOS mobility patterns. So, we prefer to use size of PMOS twice or more than that of NMOS as said earlier.

![[Pasted image 20231022135641.png]]

![[Pasted image 20231022135655.png]]

***NOTE*: If we don’t add ground, the tool doesn’t define the block what should the the other voltage range.**
## **8. INVERTER Characteristics**

![[Pasted image 20231022135716.png]]
### 8.1 Creating the Schematic**

Add instances like NMOS, PMOS, Vdc and ground joining then to form an inverter circuit.

![[Pasted image 20231022135732.png]]
### **8.2 Creating the Symbol of Inverter**

Create an inverter symbol from the schematic cell view.

![[Pasted image 20231022135746.png]]
### 8.3 Creating the symbol’s testbench**

We create a new cell view schematic and add the instance symbol of inverter and provide it with the required input voltages.

![[Pasted image 20231022135800.png]]
### 8.4 Analysis of Inverter (Transient, DC analysis)**

In the ADE L window, add the type of analysis and the input, output for both transient and dc analysis.

**Transient analysis:** Variation of input and output wrt time.

![[Pasted image 20231022135829.png]]

**DC analysis:** Variation of input wrt output (Vin on x-axis). For selecting the dc analysis part, we get the output but we have to select how the input should vary. This implies that x-axis has Vin plotted on it. This is why we get a y=mx type graph.

![[Pasted image 20231022135848.png]]

![[Pasted image 20231022135857.png]]

Input less than Vdd/2 considers it as logic 0 and gives us output as 1. Input greater than Vdd/2 considers it as logic 1 and gives us output as 0. An ideal inverter has switching threshold at half. i.e., we need output as Vdd/2 when input is also Vdd/2 i.e., for 0.5v we need to get output also 0.5v but here in the generated inverter we don’t have this picture.

![[Pasted image 20231022135911.png]]

Here for 500mv we are getting the output as 80.0911mv and this is very far from an ideal inverter. But we can make the inverter close to the ideal one by changing the physical parameters of the MOSFETS. Here in this normal case, we see that we have a case (multiple points on the plot) where both the transistors PMOS and NMOS in inverter are on and that is the case of problem. So here we change the parameters such that there is only one point on the plot at which both the PMOS and NMOS are on i.e., Vsp.
## **9. Switching Threshold of Inverter (for same mid voltage for Vin=Vout=(Vdd/2))**

![[Pasted image 20231022140146.png]]

There will be no effect on transient analysis. the graphs will be overlapped in the transient analysis. but in the dc analysis there will be multiple graphs producing outputs for different values of variable parameter(wpn).

![[Pasted image 20231022140254.png]]

In the graph we can see multiple outputs for different values of wpn. We break down the graph to the plots that has Vout near 500mv.

![[Pasted image 20231022140309.png]]

These two plots give the value near to the ideal 500mv values and the value of near ideal wpn will lie in between 400nm and 420nm as observed from the graph. Now we use the cross function from the calculator to verify it wrt the y-axis for that 500mv value.

![[Pasted image 20231022140325.png]]
### Steps for cross function in calculator in Cadence Virtuoso:

Select on wave and vs and then in the symbol schematic testbench, select the output wire. Then use the cross function and add the Vm to the outputs in ADE L window. We get the value of wpn as 412.6848nm to get the inverter to near ideal condition. In the previous plot we made a rough estimation b/w 400nm to 420nm and now in this plot we got the exact value.

![[Pasted image 20231022140341.png]]

So, from the graph the output is very near i.e., 500.04mv and is very close to ideal inverter.

## **10. Inverter same rise time and fall time (wpn for same rise time and fall time)**

We set the PMOS width to the value that we got above or any value and find the one plotted transient analysis and from this we use delay function two times one for input rising output falling gives the tpdf and input falling output rising gives the tpdr.

![[Pasted image 20231022140506.png]]

The observed graph is for one variable value of wpn, it plots the rise delay and fall delay. The intersection has equal value of tpdf and tpdr.

![[Pasted image 20231022140523.png]]

![[Pasted image 20231022140540.png]]

![[Pasted image 20231022140550.png]]

We find the value of wpn for which both are equal by tpdf-tpdr=0(calculate in calculator). This gives another plot of variation of the expression and we find for which wpn it is becoming zero on yaxis and xaxis respectively. and it is zero at 383.8178nm.

In calculator we can find the individual delay tpdr and tpdf. Note that the previous one i.e., switching at Vdd/2 is not possible now as the wpn value is changed. Although we can satisfy both in the same manner finding the correct value of wpn.

Plotting the transient analysis with wpn=383.8178nm

![[Pasted image 20231022140604.png]]

tpdr value in calculator = 11.21E-12 units

tpdf value in calculator = 11.2E-12 units
## **11. Noise Margin of Inverter**

Found at the points where the derivative is -1.

![](file:///C:/Users/ANANDA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

NMh = Voh-Vih = Vdd-Vih = 1-Vih

NMl = Vil-Vol = Vil

![](file:///C:/Users/ANANDA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

![](file:///C:/Users/ANANDA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image006.png)

We need to find Vil and Vih and to find them we do dc analysis and find the derivative -1(2values will be found- big value Vih and small value Vil)

***Note*:** DC analysis needs output only. Transient analysis needs input and output.

We find the derivative curve of the plot and check the values for -1.

Therefore the 2 values of Vih and Vil for inverter noise margin are

![](file:///C:/Users/ANANDA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image008.png)

Vil=397.08mv

Vih=623.43mv at 383.8178nm wpn

And from these we can find the noise margin values mathematically.










