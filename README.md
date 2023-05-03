Download Link: https://assignmentchef.com/product/solved-cs2208b-assignment-3
<br>
For this assignment, only an electronic submission (<strong><em><u>attachments</u></em></strong>) at owl.uwo.ca is required.

<ul>

 <li>Attachments must include:

  <ul>

   <li><strong><em><u>ONE pdf</u></em></strong> file that has the two flowcharts, program documentations, and any related communications.</li>

   <li><strong><em><u>TWO Text</u></em></strong> files that have softcopy of the assembly programs that you wrote for each question (<em>one program per file</em>), i.e., <strong><em><u>TWO assembly</u></em></strong> program files in total.</li>

  </ul></li>

 <li>So, in total, you will submit 1 + 2 = 3 files.</li>

 <li><strong>Failure to follow the above format may cost you 10% of the total assignment mark.</strong></li>

</ul>

Late assignments are strongly discouraged

<ul>

 <li>10% will be deducted from a late assignment (up to 24 hours after the due date/time)  After 24 hours from the due date/time, late assignments will receive a zero grade.</li>

</ul>

In this assignment, you will use the <em>micro Vision ARM simulator</em> by <em>Keil</em>, which is an <strong><em>MS Windows</em></strong> based software, to develop the required programs in this assignment.  The simulator (version 4) has been installed on all PCs at SSC-1032 and HSB-14 labs.

The <em>Keil micro Vision</em> simulator may also be installed on your Windows PC. You just need to download it from OWL and install it.




Programming style is very important in assembly language. It is expected to do the following in your programs:  Using macros for the constants in your program to make it more readable.

<ul>

 <li>Applying neat spacing and code organization:

  <ul>

   <li>Assembly language source code should be arranged in three columns: <em>label</em>, <em>instruction</em>, and <em>comments</em>: the <em>label</em> field starts at the beginning of the line,</li>

   <li>the <em>instruction</em> field (opcodes + operands) starts at the next TAB stop, and § the <em>comments</em> are aligned in a column on the right.</li>

  </ul></li>

 <li>Using appropriate label names.</li>

 <li>Using EQU directive to give a symbolic name to a numeric constant</li>

 <li>Commenting each assembly line</li>

</ul>




<strong><u>Great Ways to Lose Marks</u></strong>

<ul>

 <li>Not grouping your lines into logical ideas</li>

 <li>Not using any whitespace at all</li>

 <li>Not bothering to comment</li>

 <li>Commenting the code by just stating what you’re doing, instead of why, e.g.,</li>

</ul>

MOV r0, #5    ;move 5 into r0

<ul>

 <li>Not paying attention to the programming style (see the previous paragraph)</li>

 <li>Handing it in as soon as it assembles without testing and/or trying to break your code</li>

</ul>

Copyright © 2016 Mahmoud El-Sakka.







<h1>QUESTION 1 (50 marks)</h1>

Most goods sold in U.S. and Canadian stores are marked with a Universal Product Code (UPC). The meanings of the digits underneath the bar code (from left to right) are:

<ul>

 <li>First digit: type of item,</li>

 <li>First group of five digits: manufacturer,</li>

 <li>Second group of five digits: product, and</li>

 <li>Final digit: check digit, used to help identify an error in the preceding digits.</li>

</ul>

To compute the check digit,

<ul>

 <li>Add the first, third, fifth, seventh, ninth, and eleventh digits</li>

 <li>Add the second, fourth, sixth, eighth, and tenth digits</li>

 <li>Multiply the first sum by 3 and add it to the second sum</li>

 <li>The check digit is the digit which, when added to the above sum, produces a sum that is multiple of 10 o Subtract 1 from the total o Compute the remainder when the adjusted total is divided by 10 o Subtract the remainder from 9 Example for UPC 0 13800 15073 8:</li>

 <li>First sum: 0 + 3 + 0 + 1 + 0 + 3 = 7</li>

 <li>Second sum: 1 + 8 + 0 + 5 + 7 = 21</li>

 <li>Multiplying the first sum by 3 and adding the second yields 42</li>

 <li>Subtracting 1 gives 41</li>

 <li>Remainder upon dividing by 10 is 1</li>

 <li>Remainder is subtracted from 9</li>

 <li>Result is 8</li>

</ul>

<u>Draw a <em>detailed flowchart</em> and write an ARM assembly program to determine whether a string of 12 ASCII encoded digits</u> <u>stored in memory is a valid UPC or not. If valid, you should store 1 in </u><u>r0</u><u>, if not, you should store 2 in </u><u>r0</u><u>. <strong>Your code</strong></u><strong> <u>should be highly optimized, i.e., use as little number of instructions as possible.</u></strong>




You may want to define the 12 digits UPC string as follow:

<strong>UPC    DCB “013800150738”   ;UPC string  </strong>




To test your program, you can use the following UPCs:

<strong>0 60383 75557 7 </strong>

<strong>0 65633 45471 2 </strong>

You can also get more UPC codes from your own kitchen items.




HINT 1: You can implement the division operation using repeated subtraction.

HINT 2: To calculate 3 × Z, you can do so using only one ADD instruction with LSL#1 shift. HINT 3: To load a byte to a register, use <strong>LDRB</strong> not <strong>LDR</strong><strong>. </strong>




<h1>QUESTION 2 (50 marks)</h1>

<u>Draw a <em>detailed flowchart</em> and write an ARM assembly program to determine whether a string of <strong><em>printable</em></strong> ASCII</u> <u>encoded characters stored in memory is a palindrome (i.e., the letters in the string are the same from left to right as from</u> <u>right to left) or not. If palindrome, you should store 1 in </u><u>r0</u><u>, if not, you should store 0 in </u><u>r0</u>.<strong><u> Your code should be highly</u> <u>optimized, i.e., use as little number of instructions as possible.</u></strong>




<strong><em>Ignore</em></strong> all <em>characters</em> that are <strong><em>not letters</em></strong>. You should also treat capital and small letters the same. For example, “<em>madam</em>”, “<em>deleveled</em>”, “<em>Noon</em>”, “<em>He lived as a devil, eh?</em>”, and “<em>Was it a car or a cat I saw?</em>” are palindrome strings. However, “<em>madam, I am Adam.</em>” is not a palindrome string.




A string can have <em>even</em> or <em>odd</em> number of characters and ends with character <strong>0x00</strong> (the ASCII code of the null character).




You may want to define the UPC string as follow:

<strong>STRING DCB “He lived as a devil, eh?” ;string  </strong>

<strong>EoS    DCB 0x00                       ;end of string </strong>


