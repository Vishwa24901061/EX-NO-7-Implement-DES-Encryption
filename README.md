# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```py
#include <stdio.h>
#include <string.h>

void des_encrypt(char text[], char key[]) {
    int i;
    for (i = 0; i < strlen(text); i++) {
        text[i] = text[i] ^ key[i % strlen(key)];
    }
}

void des_decrypt(char text[], char key[]) {
    int i;
    for (i = 0; i < strlen(text); i++) {
        text[i] = text[i] ^ key[i % strlen(key)];
    }
}

int main() {
    char text[100], key[20];

    printf("Enter the plaintext: ");
    fgets(text, sizeof(text), stdin);
    text[strcspn(text, "\n")] = '\0';   // remove newline

    printf("Enter the key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0';     // remove newline

    des_encrypt(text, key);
    printf("Encrypted text: %s\n", text);

    des_decrypt(text, key);
    printf("Decrypted text: %s\n", text);

    return 0;
}

```



## Output:
<img width="487" height="220" alt="image" src="https://github.com/user-attachments/assets/839d807e-e9b8-469a-ad66-b323ab57bbfd" />

## Result:
  The program is executed successfully

