## EX: 8 IMPLEMENTATION OF ADVANCED ENCRYPTION STANDARD

## AIM:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

## ALGORITHM:
1.	Get the input plaintext and key from the user.
2.	Treat the plaintext as a single block of characters.
3.	Perform XOR operation between each character of plaintext and the corresponding character of the key (key repeats if shorter).
4.	Store the XOR result as the ciphertext.
5.	Display the ciphertext in ASCII format.
6.	Perform XOR operation again between the ciphertext and the same key to decrypt.
7.	Store and display the original message as the decrypted text.

## PROGRAM:
```
#include <stdio.h> 
#include <string.h> 

void simpleAESEncrypt(char *plaintext, char *key, char *ciphertext) 
{ 
    int i; 
    for (i = 0; i < strlen(plaintext); i++) 
    { 
        ciphertext[i] = plaintext[i] ^ key[i % strlen(key)]; 
    } 
    ciphertext[i] = '\0'; 
} 

void simpleAESDecrypt(char *ciphertext, char *key, char *decryptedText) 
{ 
    int i; 
    for (i = 0; i < strlen(ciphertext); i++) 
    {                                                                
        decryptedText[i] = ciphertext[i] ^ key[i % strlen(key)]; 
    } 
    decryptedText[i] = '\0'; 
} 

void printASCII(char *ciphertext) 
{ 
    printf("Encrypted Message (ASCII values): "); 
    for (int i = 0; i < strlen(ciphertext); i++) 
    { 
        printf("%d ", (unsigned char)ciphertext[i]); 
    } 
    printf("\n"); 
} 

int main() 
{ 
    char plaintext[100], key[100], ciphertext[100], decryptedText[100]; 
    printf("Enter the plaintext: "); 
    scanf("%s", plaintext); 
    printf("Enter the key: ");  
    scanf("%s", key);  
    simpleAESEncrypt(plaintext, key, ciphertext); 
    printASCII(ciphertext);  
    simpleAESDecrypt(ciphertext, key, decryptedText); 
    printf("Decrypted Message: %s\n", decryptedText); 
    return 0; 
}
```

## OUTPUT:
<img width="1607" height="311" alt="image" src="https://github.com/user-attachments/assets/f35eed3d-2230-4110-b86f-6d6603b3d2d7" />


## RESULT:
Hence, Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption is done successfully.
