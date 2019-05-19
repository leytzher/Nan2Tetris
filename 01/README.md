# Logical Gates - Implementation Notes


*Every Boolean function* can be expressed using three Boolean operators only: *And*, *Or* and *Not*

Now, if we can implement "And","Or" and "Not" using a logical gate, then this logical gate is "universal". Well, it turns out that "Nand" and "Nor" gates are universal.

## Building NOT, OR and AND from NAND gates:
![Nand](img/img1.png)

## Building a XOR gate
The XOR function returns 1 when its 2 inputs have opposing values, otherwise returns 0.
This can be built with 4 Nand gates.

![XOR](img/img2.png)

## Building a Multiplexor (Mux)
This is a three-input gate that uses one of its inputs , called "selection bit", to select and outputs one of the other two inputs called "data bits".

This can be summarized as:

```
    if sel = 0 :
        out=a
    else:
        out=b
```

![MUX](img/img3.png)

## Building a Demultiplexor (DMux)
This performs the opposite function of a Mux. It takes a single input and channels it to one of 2 possible outputs according to a selector bit that specifies which output to choose.

we can build a DMux using 5 Nand gates:

![DMUX](img/img4.png)


