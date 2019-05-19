# Logical Gates - Implementation Notes


*Every Boolean function* can be expressed using three Boolean operators only: *And*, *Or* and *Not*

Now, if we can implement "And","Or" and "Not" using a logical gate, then this logical gate is "universal". Well, it turns out that "Nand" and "Nor" gates are universal.

## Building NOT, OR and AND from NAND gates:
![Nand](img/img1.png)

## Building a XOR gate
The XOR function returns 1 when its 2 inputs have opposing values, otherwise returns 0.
This can be built with 4 Nand gates.

![XOR](img/img2.png)

## Building a Multiplexor
This is a three-input gate that uses one of its inputs , called "selection bit", to select and outputs one of the other two inputs called "data bits".


