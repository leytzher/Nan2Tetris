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

## Building a Multi-Bit Not (Not16)
Computer hardware is typically designed to operate on multi-bit arrays called "buses". Here we will design a 16-bit computer.

To design a 16-bit Not we need to pass a 16 bit input bus to an array of 16 binary Not gates (or 16 Nand(a,a) gates). The output will be a 16 bit output bus.
Note that the process is identical for 32-bit or 64-bit computers.

```
CHIP Not16 {
    IN in[16];
    OUT out[16];

    PARTS:
    Not(in=in[0],out=out[0]);
    Not(in=in[1],out=out[1]);
    Not(in=in[2],out=out[2]);
    Not(in=in[3],out=out[3]);
    Not(in=in[4],out=out[4]);
    Not(in=in[5],out=out[5]);
    Not(in=in[6],out=out[6]);
    Not(in=in[7],out=out[7]);
    Not(in=in[8],out=out[8]);
    Not(in=in[9],out=out[9]);
    Not(in=in[10],out=out[10]);
    Not(in=in[11],out=out[11]);
    Not(in=in[12],out=out[12]);
    Not(in=in[13],out=out[13]);
    Not(in=in[14],out=out[14]);
    Not(in=in[15],out=out[15]);
}
```


The output is:

|        in        |       out        |
|:----------------:|:----------------:|
| 0000000000000000 | 1111111111111111 |
| 1111111111111111 | 0000000000000000 |
| 1010101010101010 | 0101010101010101 |
| 0011110011000011 | 1100001100111100 |
| 0001001000110100 | 1110110111001011 |

## Building a Multi-Bit And and Or

Here we require 2 16-bit input buses, 16 binary AND (or OR gates) gates and 1 16-bit output bus.

The process is similar to the Not gate.

```
CHIP Or16 {
    IN a[16], b[16];
    OUT out[16];

    PARTS:
    Or(a=a[0], b=b[0],out=out[0]);
    Or(a=a[1], b=b[1],out=out[1]);
    Or(a=a[2], b=b[2],out=out[2]);
    Or(a=a[3], b=b[3],out=out[3]);
    Or(a=a[4], b=b[4],out=out[4]);
    Or(a=a[5], b=b[5],out=out[5]);
    Or(a=a[6], b=b[6],out=out[6]);
    Or(a=a[7], b=b[7],out=out[7]);
    Or(a=a[8], b=b[8],out=out[8]);
    Or(a=a[9], b=b[9],out=out[9]);
    Or(a=a[10], b=b[10],out=out[10]);
    Or(a=a[11], b=b[11],out=out[11]);
    Or(a=a[12], b=b[12],out=out[12]);
    Or(a=a[13], b=b[13],out=out[13]);
    Or(a=a[14], b=b[14],out=out[14]);
    Or(a=a[15], b=b[15],out=out[15]);

}
```




