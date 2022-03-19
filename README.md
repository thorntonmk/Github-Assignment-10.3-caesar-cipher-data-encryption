# Github-Assignment-3-caesar-cipher-data-encryption.py
# importing sys
import sys

# This is the main function
def main():
    # get the shift value after checking
    k = check(sys.argv)
    plain = input("plaintext: \n")
    print()
    print("Caesar Cipher output text: \n")

    caesar_txt = caesar(plain, k)

    # This first for loop returns the first index value of the line, which is 5 x 10 = 50.
    for line_start in range(0, len(caesar_txt), 50):
        # This list contains all of the constituents of a line.
        current_line = caesar_txt[line_start : line_start + 50]
        # This list comprises all of the components of a line.
        for block_start in range(0, len(current_line), 5):
            block = caesar_txt[line_start + block_start : line_start + block_start + 5]
            # End="" prevents this from happening because a standard print function puts a n or an enter after it.
 that
            # We can instruct the print function to use " " space as the last line rather than n
            # we also join the list into a string
            print("".join(block), end=" ")
        # This print inserts an enter after each line.
        print()


def caesar(plain, k):
    # As directed, convert the plain text to uppercase.
    plain = plain.upper()
    # a list for storing the caesar txt
    caesar_txt = []
    for letter in plain:
        # check if the letters are alphabets else move forward
        if not letter.isalpha():
            continue
        # the ascii value of A is 65
        offset = 65
        # ord() gives the ascii of a letter
        # ord('A') = 65 so we can make A value to 0
        pi = ord(letter) - offset
        # We add the shift value to the pi value and divide by 26 to ensure that the value does not exceed 26.
        # It has the ability to go back and forth between 0 and 26.
        ci = (pi + k) % 26
        # attach the shifted text while replacing the ascii value that was removed
        # here chr() gives the ascii characted corresponding to its number
        caesar_txt.append(chr(ci + offset))
    return caesar_txt


# Whether the CLI parameter for the Caesar key K is given or not is checked by this function.
def check(arg):
    # Exit if there are no more than two parameters or if the second argument, K, is not an integer.
    if len(arg) != 2 or arg[1].isalpha():
        exit("Usage is as follows ==>  python caesar.py k")
    # if exits correctly then return K value
    return int(arg[1])


# call main function
if name == "main":
    main()
    [Github Assignment 3. Caesar.py.docx](https://github.com/thorntonmk/Github-Assignment-3-caesar-cipher-data-encryption/files/8308752/Github.Assignment.3.Caesar.py.docx)
[Github Assignment 3. Caesar.py.docx](https://github.com/thorntonmk/Github-Assignment-3-caesar-cipher-data-encryption/files/8308754/Github.Assignment.3.Caesar.py.docx)
[Github Assignment 3. Caesar.py.docx](https://github.com/thorntonmk/Github-Assignment-3-caesar-cipher-data-encryption/files/8308755/Github.Assignment.3.Caesar.py.docx)
