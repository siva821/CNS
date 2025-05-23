## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


### PROGRAM :-
~~~
#include <stdio.h> 
#include <string.h> 
 
void encrypt(char message[], int shift) { 
    shift = shift % 26;  // Ensures shift stays within valid range 
    for (int i = 0; message[i] != '\0'; ++i) { 
        if (message[i] >= 'a' && message[i] <= 'z') { 
            message[i] = ((message[i] - 'a' + shift) % 26) + 'a'; 
        } else if (message[i] >= 'A' && message[i] <= 'Z') { 
            message[i] = ((message[i] - 'A' + shift) % 26) + 'A'; 
        } 
    } 
    printf("Encrypted message: %s\n", message); 
} 
 
void decrypt(char message[], int shift) { 
    shift = shift % 26;  // Ensures shift stays within valid range 
    for (int i = 0; message[i] != '\0'; ++i) { 
        if (message[i] >= 'a' && message[i] <= 'z') { 
            message[i] = ((message[i] - 'a' - shift + 26) % 26) + 'a'; 
        } else if (message[i] >= 'A' && message[i] <= 'Z') { 
            message[i] = ((message[i] - 'A' - shift + 26) % 26) + 'A'; 
        } 
    } 
    printf("Decrypted message: %s\n", message); 
} 
 
int main() { 
    char message[100]; 
    int shift; 
 
    printf("Enter a message: "); 
    fgets(message, sizeof(message), stdin); 
 
    // Remove newline character from fgets() 
    message[strcspn(message, "\n")] = '\0'; 
 
    printf("Enter shift amount: "); 
    scanf("%d", &shift); 
 
    // Make a copy of the message to decrypt later 
    char encrypted_message[100]; 
    strcpy(encrypted_message, message); 
 
    encrypt(encrypted_message, shift); 
    decrypt(encrypted_message, shift); 
 
    return 0;
}
~~~


### OUTPUT :-
<img width="492" alt="image" src="https://github.com/user-attachments/assets/a3dad350-f154-45a1-b729-89e2cb39f998" />

### Result:
     Hence the output is verified sucessfully
