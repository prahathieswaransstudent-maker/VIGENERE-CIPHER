# EX. NO: 4 – IMPLEMENTATION OF VIGENERE CIPHER

## AIM

To implement the Vigenere Cipher substitution technique using a C program.

---

#### Name: **Prahathieswaran S** 
#### Reg No: **212225240107**


## DESCRIPTION

The Vigenere Cipher is a polyalphabetic substitution cipher that uses a repeating keyword to encrypt plaintext. A 26 × 26 matrix called the **Vigenere Table** (or **Tabula Recta**) is constructed, where each row is a cyclic left shift of the alphabet.

During encryption, each plaintext letter is combined with the corresponding keyword letter. The row is selected using the keyword character, and the column is selected using the plaintext character. The character at their intersection becomes the ciphertext character.

For example, if the plaintext is **ATTACKATDAWN** and the keyword is **LEMON**, the keyword is repeated to match the plaintext length:

Plaintext : ATTACKATDAWN

Keyword   : LEMONLEMONLE

Ciphertext: LXFOPVEFRNHR

---

## ALGORITHM

**STEP-1:** Arrange the alphabets in a 26 × 26 matrix.

**STEP-2:** Cyclically shift each row of alphabets to the left by one position.

**STEP-3:** Construct the complete Vigenere table.

**STEP-4:** Read the plaintext and keyword from the user.

**STEP-5:** Repeat the keyword sequentially until its length matches the plaintext length.

**STEP-6:** For each plaintext character, choose the corresponding keyword character as the row index.

**STEP-7:** Use the plaintext character as the column index.

**STEP-8:** The character at the intersection of the selected row and column forms the ciphertext character.

**STEP-9:** Repeat the process for all characters to generate the final ciphertext.

---

## PROGRAM

```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char plaintext[100], keyword[100], ciphertext[100];
    int i, j = 0;

    printf("Enter the Plain Text (Capital Letters): ");
    scanf("%s", plaintext);

    printf("Enter the Keyword (Capital Letters): ");
    scanf("%s", keyword);

    int textLen = strlen(plaintext);
    int keyLen = strlen(keyword);

    for(i = 0; i < textLen; i++)
    {
        ciphertext[i] = ((plaintext[i] - 'A') + (keyword[j] - 'A')) % 26 + 'A';

        j++;
        if(j == keyLen)
            j = 0;
    }

    ciphertext[textLen] = '\0';

    printf("\nPlain Text : %s", plaintext);
    printf("\nKeyword    : %s", keyword);
    printf("\nCipher Text: %s\n", ciphertext);

    return 0;
}
```

---

## INPUT

```
Enter the Plain Text (Capital Letters): PRAHATHIESWARAN
Enter the Keyword (Capital Letters): POWER

Plain Text : PRAHATHIESWARAN
Keyword    : POWER
```

---

## OUTPUT

<img width="1840" height="636" alt="image" src="https://github.com/user-attachments/assets/916feb8a-e131-41c9-a39a-2a0776e37fdc" />

```
Cipher Text: EFWLRIVEIJLONEE
```

---

## RESULT

Thus, the C program to implement the Vigenere Cipher substitution technique was successfully executed, and the corresponding ciphertext was generated.
