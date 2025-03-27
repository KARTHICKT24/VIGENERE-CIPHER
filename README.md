# VIGENERE-CIPHER
## EX. NO: 1(D)
 

## IMPLEMETATION OF VIGENERE CIPHER

## NAME : KARTHICK KISHORE T
## REG NO : 212223220042
## DATE 27-03-2025

## AIM:

To implement the Vigenere Cipher substitution technique using Python program.

## DESCRIPTION:

To encrypt, a table of alphabets can be used, termed a tabula recta, Vigenère square,or Vigenère table. It consists of the alphabet written out 26 times in differnt rows, each
 
alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses adifferent alphabet from one of the rows. The alphabet used at each point repeating keyword.depends on a Each row starts with a key letter. The remainder of the row holds the letters A to Z. Although there are 26 key rows shown, you will only use as many keys as there are unique letters in the key string, here just 5 keys, {L, E, M, O, N}. For successive letters of the message, we are going to take successive letters of the key string, and encipher each message letter using its corresponding key row. Choose the next letter of the key, go along that row to find the column heading that	atches the message character; the letter at the intersection of
[key-row, msg-col] is the enciphered letter.


## ALGORITHM:
```
STEP-1: Arrange the alphabets in row and column of a 26*26 matrix.
STEP-2: Circulate the alphabets in each row to position left such that the first letter is attached to last.
STEP-3: Repeat this process for all 26 rows and construct the final key matrix.
STEP-4: The keyword and the plain text is read from the user.
STEP-5: The characters in the keyword are repeated sequentially so as to match with that of the plain text.
STEP-6: Pick the first letter of the plain text and that of the keyword as the row indices and column indices respectively.
STEP-7: The junction character where these two meet forms the cipher character.
STEP-8: Repeat the above steps to generate the entire cipher text.
```


## PROGRAM

```
def vigenere_cipher_encrypt(text, key):
    encrypted_text = ""
    key_length = len(key)
    
    for i, char in enumerate(text):
        if char.isalpha():
            shift = ord(key[i % key_length].lower()) - ord('a')
            if char.islower():
                encrypted_text += chr((ord(char) - ord('a') + shift) % 26 + ord('a'))
            else:
                encrypted_text += chr((ord(char) - ord('A') + shift) % 26 + ord('A'))
        else:
            encrypted_text += char
    
    return encrypted_text

def vigenere_cipher_decrypt(ciphertext, key):
    decrypted_text = ""
    key_length = len(key)
    
    for i, char in enumerate(ciphertext):
        if char.isalpha():
            shift = ord(key[i % key_length].lower()) - ord('a')
            if char.islower():
                decrypted_text += chr((ord(char) - ord('a') - shift) % 26 + ord('a'))
            else:
                decrypted_text += chr((ord(char) - ord('A') - shift) % 26 + ord('A'))
        else:
            decrypted_text += char
    
    return decrypted_text

# Example usage
text = input("Enter text to encrypt: ")
key = input("Enter key: ")

encrypted = vigenere_cipher_encrypt(text, key)
print(f"Encrypted Text: {encrypted}")

decrypted = vigenere_cipher_decrypt(encrypted, key)
print(f"Decrypted Text: {decrypted}")
```

## OUTPUT

![crypto 4 py](https://github.com/user-attachments/assets/fdbb87ba-e98e-437a-8a7b-09da533966a7)

## RESULT

THE VIGENERE CIPHER PROGRAM WAS IMPLEMENTED BY USING PYTHON PROGRAM
