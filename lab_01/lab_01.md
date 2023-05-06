# Lab 1
* ## Study VHDL and GHDL
    * VHDL stands for VHSIC Hardware Description Language and is widely used as hardware description languages for modeling and simulating circuits. On the other hand, GHDL is an open-source simulator for VHDL
* ## Install GHDL and GTKWave
    * To install GHDL I used the Windows Subsystem for Linux (WSL),Ubuntu, and followed the following commands.
    ```sh
    $ cat /etc/os-release
    $ sudo apt update
    $ sudo apt install gtkwave
    $ sudo apt install git make gnat zlib1g-dev
    $ git clone https://github.com/ghdl/ghdl
    $ cd ghdl
    $ ./configure --prefix=/usr/local
    $ make
    $ sudo make install
    ```
* ## Half Adder
    * Compile
    ![](/lab_01/Adder/Half%20Adder%20compile.PNG)
    * Result
    ![](/lab_01/Adder/Adder%20output.PNG)
* ## D Flip-Flop
    * Compile
    ![](/lab_01/D_Flip_Flop/Dff%20compile.PNG)
    * Result
    ![](/lab_01/D_Flip_Flop/Dff%20output.PNG)
* ## 4-to-1 Multiplexer
    * Compile
    ![](/lab_01/4_1_Mux/4_1_Mux%20compile.PNG)
    * Result
    ![](/lab_01/4_1_Mux/4_1_Mux%20output.PNG)
* ## Icarus Verilog
> Icarus Verilog is an implementation of the Verilog hardware description language compiler that generates netlists in the desired format (EDIF). It supports the 1995, 2001 and 2005 versions of the standard, portions of SystemVerilog, and some extensions.

* ## Problems
    * [Could not initialize GTK!  Is DISPLAY env var/xhost set?](https://askubuntu.com/questions/897846/cant-run-gtk-on-wsl-display-error)