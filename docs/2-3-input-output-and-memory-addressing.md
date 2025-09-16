* [Página inicial](https://openplcproject.com/ "Página inicial")
* [Docs](https://autonomylogic.com/docs/ "Docs")
* [2. OpenPLC Runtime](https://autonomylogic.com/docs-category/openplc-runtime/ "2. OpenPLC Runtime")
* 2.3 Input, Output and Memory Addressing


2.3 Input, Output and Memory Addressing
=======================================

 

PLC applications interact with the external world through Input and Output modules and/or SCADA communication protocols. When designing your PLC applications, you decide which variables should be attached to I/O and communication modules by labeling the variable with a PLC address.

OpenPLC Runtime uses the IEC 61131-3 nomenclature to address input, output and memory locations. The addressing of I/O locations is done through the use of special character sequences. These sequences are a concatenation of the percent sign “%”, a location prefix, a size prefix and one or more natural numbers separated by blank spaces. The following location prefixes are supported:

* **I**for input
* **Q** for output
* **M** for memory

The following size prefixes are supported:

* **X** for bit (1 bit)
* **B**for byte (8 bits)
* **W** for word (16 bits)
* **D**for double word (32 bits)
* **L**for long word (64 bits)

For example, if you want to read the state of the first digital input into a BOOL variable, you must declare your variable located at: **%IX0.0**. If you want to write the contents of a UINT variable into the second analog output, you should declare your UINT variable located at **%QW2.**

*Note: PLC to physical I/O mapping is platform dependent. For more information on PLC I/O mapping for every supported platform, check: 2.4 Physical Addressing*

As you probably have noticed, bit (X) PLC addresses have a two-part hierarchical address. The least significant part (right-most) can be interpreted as a position in a byte and must be in the range 0 to 7. The most significant part (left-most) must be no more than 1023. Parts are separated by a single period. Data sizes other than X have a one-part hierarchical address. They must not contain a period (.) and must be no more than the maximum memory location address for your platform.

The following are *invalid* examples of PLC addresses in OpenPLC for the stated reason:

* **%IX0.8** The least significant index is greater than 7.
* **%QX0.0.1** Three part hierarchy is not permitted address.
* **%IB1.1** Two part hierarchy is only permitted for X data size.

##### What are your Feelings

Updated on 2022-12-28

Leave a Reply [Cancel reply](/docs/2-3-input-output-and-memory-addressing/#respond)
-----------------------------------------------------------------------------------

You must be [logged in](https://autonomylogic.com/wp-login.php?redirect_to=https%3A%2F%2Fautonomylogic.com%2Fdocs%2F2-3-input-output-and-memory-addressing%2F) to post a comment.