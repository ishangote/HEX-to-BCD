# HEX-to-BCD
Assembly x86 program for conversion of HEX number to BCD format and vice versa.

<b>Step 1:</b> Install NASM for executing the code.(https://www.youtube.com/watch?v=ooJfdrds9Dk)<br/>

<b>Step 2:</b> Open terminal and execute following commands to run the program:<br/>
<b>nasm -f elf64 filename.asm<br/>ld -o x numadd.o<br />./x</b>
<br />

<b>Algorithm For Hex to BCD Conversion</b><br />
Step I              :    Initialize the data segment.<br />
Step II             :    Initialize BX = 0000 H and DH = 00H.<br />
Step III           :    Load the number in AX.<br />
Step IV           :    Compare number with 10000 decimal. If below goto step VII else goto step V.<br />
Step V             :    Subtract 10,000 decimal from AX and add 1 decimal to DH<br />
Step VI           :    Jump to step IV.<br />
Step VII          :    Compare number in AX with 1000, if below goto step X else goto step VIII.<br />
Step VIII        :    Subtract 1000 decimal from AX and add 1000 decimal to BX.<br />
Step IX           :    Jump to step VII.<br />
Step X             :    Compare the number in AX with 100 decimal if below goto step XIII<br />
Step XI           :    Subtract 100 decimal from AX and add 100 decimal to BX.<br />
Step XII         :    Jump to step X<br />
Step XIII        :    Compare number in AX with 10. If below goto step XVI<br />
Step XIV        :    Subtract 10 decimal from AX and add 10 decimal to BX.<br />
Step XV          :    Jump to step XIII.<br />
Step XVI        :    Add remainder in AX with result in BX.<br />
Step XVII      :    Display the result in DH and BX.<br />
Step XVIII     :    Stop.<br />

<b>Algorithm For BCD to Hex Conversion</b><br />
Step I              :   Initialize the data segment.<br />
Step II            :   Load the MSB of word in register AX.<br />
Step III           :   Compare it with 0, if zero goto step VII else goto step IV.<br />
Step IV           :   decrement AX and initialize BX = 0000.<br />
Step V             :   add 10000 decimal to BX.<br />
Step VI           :   Jump to step III.<br />
Step VII         :   Load LSB of word in register AX.<br />
Step VIII        :   Compare it with 1000, if below go to step XII else go to step IX.<br />
Step IX           :   subtract 1000 H from AX.<br />
Step X            :   Add 1000 decimal to BX.<br />
Step XI           :   Jump to step VIII<br />
Step XII         :   Compare number in AX now with 100 H, if below go to step XVI, else go to step XIII.<br />
Step XIII       :   Subtract 100 H from AX.<br />
Step XIV        :   Add 100 decimal to BX.<br />
Step XV         :   Jump to step XII.<br />
Step XVI        :   Compare number in AX with 10H, if below go to step XX, else go to step XVII.<br />
Step XVII      :   Subtract 10 H from AX<br />
Step XVIII    :   Add 10 decimal to BX<br />
Step XIX       :   Jump to step XVI<br />
Step XX         :   Add contents of AX and BX.<br />
Step XXI       :   Display the result.<br />
Step XXII      :   Stop.<br />


