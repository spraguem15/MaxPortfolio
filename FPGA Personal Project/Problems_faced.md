
<h1>Overview</h1>

I wanted to make a section with all the challenges I faced with this project so that I could refer back to them if I ever run into them again. I also find when I reflect on issues/challenges I remember how to solve them better for the future. 

<h2>Inout signals</h2>

Before this project I had never had the chance to work with the "inout" signal in systemverilog. This signal is very important for many systems such as I2C, because it allows the master and slave devices to communicate on the same line, decreasing complexity and saving space. Driving these signals is different from an input or output, because you essentially need an enable signal to use them. What this means is that when you know that you can use the signal you need to enable the use of it so that you are not constantly driving it. Below is a example of how a signal could be driven. 

```
    assign SDA = (SDA_en) ? SDA_out : 1'bz; // Make inout signal work
```

The off state here allows the signal to be floating, which would allow another source to modify the signal. Without this you would have two different sources driving a signal which would cause signals to be wrong. 

<h2>Synthesis Changes</h2>
