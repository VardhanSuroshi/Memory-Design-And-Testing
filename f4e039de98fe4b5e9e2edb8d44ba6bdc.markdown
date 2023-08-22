**PES UNIVERSITY**

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image1.png){width="1.5916666666666666in"
height="2.6805555555555554in"}

> **MEMORY DESIGN AND TESTING**

**UE20EC343**

**PROJECT REPORT**

**DESIGN OF 4X4 SRAM MEMORY ARRAY**

**Using Cadence Virtuoso**

**Submitted by :**\
Vardhan Suroshi PES2UG20EC163 Varun S N PES2UG20EC107

**Project guide :**

> Prof. Mahesh Awati\
> Department of Electronics and Communication Engineering PES UNIVERSITY
> Electronic City, Bangalore-560100\
> 2023
>
> **1.1 Introduction :**
>
> SRAM, or Static Random Access Memory, is a widely used type of
> volatile memory in computer systems, microprocessors, and hand held
> devices due to its high speed and low power\
> consumption. At the heart of SRAM technology lies the SRAM cell, also
> known as the 6T SRAM cell. Comprising six MOSFETs, the SRAM cell uses
> latching circuitry, or flip-flops, to store each bit of data. This
> innovative storage approach makes SRAM cells ideal for use in cache
> memories, where fast access to frequently used data is critical. In
> this context, SRAM cells offer an advantage over other types of
> volatile memory, such as Dynamic Random Access Memory (DRAM), which is
> slower and requires periodic refresh cycles. This makes SRAM cells a\
> fundamental building block of modern computing systems and a key
> technology for achieving high-speed data processing..

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image2.png){width="2.85in"
height="2.25in"}

> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image3.png){width="2.5833333333333335in"
> height="1.9583333333333333in"}

+-----------------------+-----------------------+-----------------------+
| fig1.                 | 6T                    | > SRAM                |
+=======================+=======================+=======================+
+-----------------------+-----------------------+-----------------------+

cell

**The two basic requirements which dictate the W/L ratios are:**\
a) **Read upset :** The data-read operation should not destroy the
stored information in SRAM cell.

> The cell ratio (beta) should be less than 1.5 to for proper
> functioning of SRAM cell b) **Write upset** :The cell should allow the
> modification of the stored information during the data-writephase.
>
> These conflicting requirements for read and write operations are
> satisfied by sizing the bit cell transistors to provide stable read
> and write operation.
>
> To satisfy requirement (a), we come up with the cell ratio, β for the
> read operation which is given by,

+-----------------------------------+-----------------------------------+
| > W\                              |                                   |
| > ( \_) pull down transistors     |                                   |
+===================================+===================================+
| Cell ratio, β =                   | > W\                              |
|                                   | > ( L )access transistor          |
+-----------------------------------+-----------------------------------+

To satisfy requirement (b), we come up with the pull-up ratio, PR for
the write operation whichis given by,

+-----------------------------------------------------------------------+
| > W\                                                                  |
| > ( L )pull up transistors Pull-up ratio, PR =                        |
| >                                                                     |
| > W\                                                                  |
| > ( L )access transistor                                              |
+=======================================================================+
+-----------------------------------------------------------------------+

**Implementation and Simulation Results**

> **1. We have implemented a 6T SRAM with CR=1.25 and PR=0.85 using
> 180nm technology by keeping the length of all devices as 180nm. We
> verified the Read and Write operation and also plotted the Butterfly
> curve for Hold state and Read state.**

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image4.png){width="6.131944444444445in"
height="3.3875in"}

> Circuit diagram of SRAM cell (Width of pull up transistors Wp= 400nm,
>
> Width of access transistors Wa= 470nm,
>
> Width of pulldown transistors Wn= 590nm)
>
> **2.Write operation :**

 Initially word line WL is high and hence bit lines BL and Bl' are
connected to the SRAM cell.

 Thenthe write driver circuit provides the required voltage to BL and
BL' ( For write 0, BL = 0, BL' = 1 and for write 1, BL=1, BL' = 0).

 The corresponding data will be then written into the cell (Q = 0 for
write 0 and Q = 1 for write 1).

For a successful write operation, access transistors should be stronger
than the pull up transistors which is taken care by the pull-up ratio.

> **2.1 Write '0' operation**

Now lets consider writing a "0" to a cell that is storing a "1".

 The write driver makes BL=0V and BL'= VDD as '0' is written into the
cell.

 Now the address decoder makes WL=1.

 Q' side of the cell cannot be pulled high enough to ensure the writing
of '1' due to sizing constraint

 imposed by the read stability. It ensures that this voltage is kept
below 0.4V.

 Hence the new value of the cell has to be written through transistor
M6 . Data '0' will be written into the

> cell if node Q is pulled down, below the threshold voltage of M1 to
> turn it OFF
>
> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image5.png){width="5.718055555555556in"
> height="2.966666666666667in"}

Timing diagram for Write '0'

> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image6.png){width="5.322222222222222in"
> height="3.993054461942257in"}

**2.2 Write '1' operation**

> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image7.png){width="5.831944444444445in"
> height="3.2847222222222223in"}

Timing diagram for Write '1'

> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image8.png){width="6.331944444444445in"
> height="4.748611111111111in"}

**Read operation**\
 To perform read operation, the memory cell should have some value.
Consider, '1' is stored in the memory cell (Q =1 and Q' = 0).

 Initially the bit lines BL and BL' are pre-charged to Vdd. Thenthe
word line WL is made high. So the transistors M1, M4, M5 and M6 (From
Fig 1) will turn ON.

Therefore BL' gets discharged through the series transistors M5-M1 and
BL will remain at its\
pre-charged state.

 As the difference between the two bit lines build up, the sense
amplifier is activated which gives output i.e. '1' is read from the
memory cell.

> **Read '1' operation**

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image9.png){width="6.183333333333334in"
height="3.3472222222222223in"}

Timing diagram for Read '1'

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image10.png){width="6.458333333333333in"
height="3.0888877952755904in"}

> **Read '0' operation**

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image11.png){width="6.25in"
height="3.470833333333333in"}

> Timing diagram for Read '0'
>
> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image12.png){width="6.5527766841644794in"
> height="3.2875in"}
>
> **Stability of SRAM cell**
>
> The stability of the SRAM cell can be described by the 'Butterfly
> curve' which is obtained by superimposing the voltage transfer curves
> (VTC) of the two inverters of the memory cell. Stability of the SRAM
> cell can be analyzed by measuring the Static Noise Margin (SNM). SNM
> is the measure of stability of the SRAM cell to hold its data against
> noise. The Stability of the cell is given by the size of the maximum
> square box that can fit inside the Butterfly wing.

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image13.png){width="2.873611111111111in"
height="2.1944444444444446in"}

> Butterfly curve for the SRAM cell
>
> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image14.png){width="2.486111111111111in"
> height="1.9805555555555556in"}
>
> Butterfly plot for read stability
>
> **Hold state**

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image15.png){width="5.918055555555555in"
height="3.3180544619422574in"}

Butterfly curve for Hold state

> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image16.png){width="5.0in"
> height="3.75in"}
>
> WL = 0 and hence access transistors are OFF. Therefore, the cell is
> isolated from BL and BL' and hence there is no possibility of state
> changing since there will be less of noise getting added. Since there
> is no noise getting added, the inverters are working with the perfect
> VTC and hence Hold state Static noise margin is expected to be
> maximum.
>
> **SNM = min (max(SNM1),max( SNM2) )**\
> = min (578.869mV, 585.075mV)\
> **= 578.869mV**
>
> **Read state**

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image17.png){width="6.113888888888889in"
height="3.5347222222222223in"}

> Butterfly curve for Read state

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image18.png){width="5.430555555555555in"
height="4.073611111111111in"}

> WL = 1 and hence access transistors are ON. Therefore, the cell is
> connected to BL and BL' and hence there is a possibility of noise
> getting added. Therefore, the curve flattens during the read operation
> hence reducing the box size. Hence, the stability reduces.
>
> **SNM = min (max(SNM1),max( SNM2) )**\
> = min (225.417mV, 218.623mV)\
> **= 218.623 mV**
>
> **2. We have designed a pre-charge circuit to charge a BL and BL' with
> capacitance of 120f** **in 0.5n Seconds**

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image19.png){width="7.479166666666667in"
height="3.188888888888889in"}

> Pre-charge circuit (Width of the transistors = 12um)
>
> Timing diagram
>
> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image20.png){width="6.552777777777778in"
> height="4.081944444444445in"}
>
> **3. We have a designed a 6T SRAM cell with the following
> specifications. External capacitance of 120fF is connected to BL and
> BL' to account for the parasitic capacitance of BL and BL'**

+-----------------------------------+-----------------------------------+
| > **Length of all MOS**           | > **180nm**                       |
+===================================+===================================+
| > **Width of PMOS devices (wp)**  | > **Minimum width**               |
+-----------------------------------+-----------------------------------+
| > **Access transistors width      | > **1.2 x wp**                    |
| > (wa)**                          |                                   |
+-----------------------------------+-----------------------------------+
| > **Width of Pull down NMOS       | > **1.5 x wa**                    |
| > transistors (wn)**              |                                   |
+-----------------------------------+-----------------------------------+

> **We have also designed the peripheral circuits -- Pre-charge circuit,
> Isolation circuit, Sense Amplifier and Write driver circuit**\
> **We have also performed the simulation of Read and Write operation**

**6T SRAM Cell**

> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image21.png){width="6.290277777777778in"
> height="3.3874989063867016in"}
>
> Circuit diagram of 6T SRAM cell (Width of pull up transistors = 400nm,
> Width of access transistors = 480nm, Width of pull down transistors =
> 720nm)

**1. Pre-charge circuit**\
Pre- circuit is used to pre-charge the bit lines to Vdd before the Read
operation. It consists of: a) Equalizer transistor which reduces the
required pre-charge time by ensuring that both bit lines are at nearly
equal voltages even if they are not pre-charged to Vdd.

b\) Bias transistors which pulls each of the bit lines to Vdd.

> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image22.png){width="5.783333333333333in"
> height="2.991665573053368in"}

**2. Isolation circuit**\
Isolation circuit is used to isolate the sense amplifier from the bit
lines once a small change on the bit lines is detected.

> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image23.png){width="6.376388888888889in"
> height="3.25in"}

**3.Sense Amplifier**\
The sense amplifier is responsible for detecting the value stored in the
SRAM cell during the read operation and displaying that value at the
output.

> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image24.png){width="5.195833333333334in"
> height="3.719443350831146in"}

**4. Write driver circuit**\
Write driver circuit is responsible to write the data onto the bit lines
BL and BL' during the write operation

> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image25.png){width="5.206944444444445in"
> height="3.3791655730533683in"}
>
> **a. SRAM cell along with all the peripheral devices**
>
> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image26.png){width="5.127777777777778in"
> height="5.981944444444444in"}
>
> Timing diagram (Wrtie 1 followed by read 1 , write 0 followed by read
> 0 )

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image27.png){width="7.480555555555555in"
height="3.3722222222222222in"}

> **Q.Simulate read operation and Find the time it takes to generate 200
> mV sense margin ( difference in voltage between BL and BL' after WL is
> made HIGH)**

+-----------------------------------+-----------------------------------+
| ![](vertopal_f4e039de98fe4        | > **Hjh d**                       |
| b5e9e2edb8d44ba6bdc/media/image28 |                                   |
| .png){width="7.638888888888889in" |                                   |
| height="3.841666666666667in"}     |                                   |
+===================================+===================================+
+-----------------------------------+-----------------------------------+

> **Q. Simulate write operation and Find the time it takes to generate
> the data to be written on BL and BL'**Ans : The circuit took 0.5249ns
> to generate the data to be written I.e to bring changes on BL and BL'
>
> ![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image29.png){width="6.470833333333333in"
> height="4.4125in"}
>
> **Finally, we have designed a 4X4 memory array and performed the write
> and read operation on a cell**
>
> **4x4 memory array**

![](vertopal_f4e039de98fe4b5e9e2edb8d44ba6bdc/media/image30.png){width="8.055555555555555in"
height="7.4388877952755905in"}

**Conclusion**

> In our project, we have a 6T SRAM cell along with its peripherals
> (Pre-charge circuit, Isolation Circuit, Sense amplifier and Write
> driver circuit). We have measured the Static Noise margin for the Hold
> state and Read state of SRAM cell. We have finally designed a 4x4
> Memory array and have performed the Write and Read operation on each
> cell
