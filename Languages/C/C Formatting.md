[[C Vars]]
- Specify decimal/character places:
	- `%{charNum}{type}`
	- `%2lf //prints to 2 characters'
	- To specify decimal places, simply add a period
	- `%.2lf`

| %c   | a single character                                 |                                                                                        |
| ---- | -------------------------------------------------- | -------------------------------------------------------------------------------------- |
| %s   | a string                                           |                                                                                        |
| %hi  | short (signed)                                     |                                                                                        |
| %hu  | short (unsigned)                                   |                                                                                        |
| %Lf  | long double                                        |                                                                                        |
| %n   | prints nothing                                     |                                                                                        |
| %d   | a decimal integer (assumes base 10)                |                                                                                        |
| %i   | a decimal integer (detects the base automatically) |                                                                                        |
| %o   | an octal (base 8) integer                          |                                                                                        |
| %x   | a hexadecimal (base 16) integer                    |                                                                                        |
| %p   | an address (or pointer)                            |                                                                                        |
| %f   | a floating point number for floats                 |                                                                                        |
| %u   | int unsigned decimal                               |                                                                                        |
| %e   | a floating point number in scientific notation     |                                                                                        |
| %E   | a floating point number in scientific notation     |                                                                                        |
| %%   | the % symbol                                       |                                                                                        |
| \a   | Alarm or Beep                                      | It is used to generate a bell sound in the C program.                                  |
| \b   | Backspace                                          | It is used to move the cursor one place backward.                                      |
| \f   | Form Feed                                          | It is used to move the cursor to the start of the next logical page.                   |
| \n   | New Line                                           | It moves the cursor to the start of the next line.                                     |
| \r   | Carriage Return                                    | It moves the cursor to the start of the current line.                                  |
| \t   | Horizontal Tab                                     | It inserts some whitespace to the left of the cursor and moves the cursor accordingly. |
| \v   | Vertical Tab                                       | It is used to insert vertical space.                                                   |
| \\   | Backlash                                           | Use to insert backslash character.                                                     |
| \’   | Single Quote                                       | It is used to display a single quotation mark.                                         |
| \”   | Double Quote                                       | It is used to display double quotation marks.                                          |
| \?   | Question Mark                                      | It is used to display a question mark.                                                 |
| \ooo | Octal Number                                       | It is used to represent an octal number.                                               |
| \xhh | Hexadecimal Number                                 | It represents the hexadecimal number.                                                  |
| \0   | NULL                                               | It represents the NULL character.                                                      |
| \e   | Escape sequence                                    | It represents the ASCII escape character.                                              |
| \s   | Space Character                                    | It represents the ASCII space character.                                               |
| \d   | Delete Character                                   | It represents the ASCII DEL character.                                                 |