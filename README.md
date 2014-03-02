The spinwrap program reads a Spin source file and generates code to allow the methods
of the Spin object to be called from C or C++. It does this by creating a proxy program
that it loads into another COG and communicates with using wrappers generated by
spinwrap.

It takes the following options:

-c
    Generates C output. The default is C++ output.

-d
    Generates useless debugging output.

-s <stack-size>
    Lets you specify the size of the stack in longs used by the proxy program.
    
-S,<openspin-option>
    Allows you to pass options to the openspin compiler. For example, -S,-foo will pass
    the option -foo to openspin.
    
-p <path>
    Lets you specify the path where output files will be generated.

The Makefile has the following targets:

spinwrap (the default)
    Builds the spinwrap program.
    
run
    Builds and runs the C++ version of the demo program.
    
runc
    Builds and runs the C version of the demo program.
    
runcatalina
    Builds and runs the Catalina C version of the demo program.
    You need to specify PORT=<serial-port> on the make command line.
    For example:
        make PORT=/dev/cu.usbserial-A601FCST runcatalina
        
clean
    Removes all generated files.
    
zip
    Creates a zip file containing all of the sources.