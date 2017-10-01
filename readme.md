# Regular Expressions - The Black Magic of Text Manipulation

## Demo Material
The Demo material is based on searching the files PhoneNumbers.txt and JennysInfo.txt

An example of how to call and get results using powershell: 
    Select-String -path PhoneNumbers.txt -Pattern 'Waldo'

1. Match name Waldo
    - `Waldo`
2. Use of `.`.  The `.` is a wild card and can represent any character.
    - `W.ldo`
3. `^`
    - We don't want to include "Sir Waldo" in the result set, so we need to use an anchor `^`
    - `^Waldo`
4. `+` and `*`.  
    - The `+` matches one or more instances of the previous character.  For example, `Wa+ldo` will mactch instances of Waldo, Waaldo, and Waadlo but not Wldo.  
    - The `*` matches 0 or more instances of the previous character.  `W*aldo` will match all of the above examples and also `aldo`
    - `^W+aldo` matches WWaldo, Waldo
    - `^W*aldo` matches WWaldo, Waldo, aldo
5. `$`
    - This anchors the end of the line.  
    - This allows us to specify that the matching expression must be at the end of the line and not some other position. 
    - If we know the Waldo phone entry we are looking for end with an 8, we can use the following expression: `^Waldo.*8$`
    - This gives us the following entry: Waldo Gosse                 (383) 950-2918
