# Regular Expressions - The Black Magic of Text Manipulation

## Demo Material
The Demo material is based on searching the files PhoneNumbers.txt and JennysInfo.txt

An example of how to call and get results using powershell: 
    Select-String -path PhoneNumbers.txt -Pattern 'Waldo'

1. Match name Waldo
    - `Waldo`
2. Use of `.`.  The `.` is a wild card and can represent any character.
    - `W.ldo`
3. We don't want to include "Sir Waldo" in the result set, so we need to use an anchor `^`
    - `^Waldo`
4. Explain `+` and `*`.  
    - The `+` matches one or more instances of the previous character.  For example, `Wa+ldo` will mactch instances of Waldo, Waaldo, and Waadlo but not Wldo.  
    - The `*` matches 0 or more instances of the previous character.  `Wa*ldo` will match all of the above examples and also `Wldo`
    - `^W+aldo` matches WWaldo, Waldo
    - `^W*aldo` matches WWaldo, Waldo, aldo
   
