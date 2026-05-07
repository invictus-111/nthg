1a

#include <stdio.h>
#include <string.h>
#include <conio.h>

void main()
{
    char username[15];
    char password[12];

    clrscr();

    printf("Enter your username:\n");
    scanf("%s", username);

    printf("Enter your password:\n");
    scanf("%s", password);

    if(strcmp(username, "admin") == 0)
    {
        if(strcmp(password, "admin") == 0)
        {
            printf("\nWelcome. Login Success!");
        }
        else
        {
            printf("\nWrong password");
        }
    }
    else
    {
        printf("\nUser doesn't exist");
    }

    getch();
}






1b

#include <stdio.h>
#include <conio.h>

int main()
{
    char password[10], username[10], ch;
    int i;

    clrscr();

    printf("Enter username : ");
    gets(username);

    printf("Enter password : ");

    for(i = 0; i < 8; i++)
    {
        ch = getch();
        password[i] = ch;
        printf("*");
    }

    password[i] = '\0';

    printf("\nYour password is : %s", password);

    getch();
    return 0;
}



#include <stdio.h>
#include <conio.h>

int main()
{
    char password[10], username[10];
    int i;

    clrscr();

    printf("Enter User name: ");
    scanf("%s", username);

    printf("Enter the password (any 8 characters): ");
    scanf("%8s", password);

    printf("********");

    printf("\nYour password is : ");

    for(i = 0; i < 8 && password[i] != '\0'; i++)
    {
        printf("%c", password[i]);
    }

    getch();
    return 0;
}
..

..
.
.
.
.
.



2
.
.
.
.

..
.
.
..

i = 0
x = 0
text = ""

text = input("\nPlease enter a string: ")

print("\nPlease choose following options:")
print("1 = Encrypt the string.")
print("2 = Decrypt the string.")

x = int(input("Option: "))

if x == 1:

    result = ""

    for i in text:
        result = result + chr(ord(i) + 3)

    print("\nEncrypted string:", result)

elif x == 2:

    result = ""

    for i in text:
        result = result + chr(ord(i) - 3)

    print("\nDecrypted string:", result)

else:
    print("\nError")
.
..
.\\.
.
.
.

*3*
.
.
.
.
.
.
.
.
..
..


dc = "QWERTYUIOPASDFGHJKLZXCVBNM"
ec = "abcdefghijklmnopqrstuvwxyz"

def encrypt(text):

    result = ""

    for ch in text:

        if ch.islower():

            index = ord(ch) - 97
            result += dc[index]

        else:
            result += ch

    return result


def decrypt(text):

    result = ""

    for ch in text:

        if ch.isupper():

            index = dc.index(ch)
            result += ec[index]

        else:
            result += ch

    return result


plain = input("Enter plain text: ")

encrypted = encrypt(plain)

print("\nAfter Encryption:")
print(encrypted)

decrypted = decrypt(encrypted)

print("\nAfter Decryption:")
print(decrypted)

4

import math

p = int(input("Enter first prime number: "))
q = int(input("Enter second prime number: "))

msg = input("Enter message: ")

def prime(n):

    for i in range(2, int(math.sqrt(n)) + 1):

        if n % i == 0:
            return 0

    return 1


if prime(p) == 0 or prime(q) == 0 or p == q:

    print("Wrong Input")
    exit()


n = p * q
phi = (p - 1) * (q - 1)


for e in range(2, phi):

    if math.gcd(e, phi) == 1:
        break


d = 1

while (d * e) % phi != 1:
    d += 1


print("\nPublic Key:", (e, n))
print("Private Key:", (d, n))


enc = []

for ch in msg:

    m = ord(ch) - 96

    c = (m ** e) % n

    enc.append(c)

print("\nEncrypted Message:")
print(enc)


dec = ""

for c in enc:

    m = (c ** d) % n

    dec += chr(m + 96)

print("\nDecrypted Message:")
print(dec)

or


import math

p = int(input("\nENTER FIRST PRIME NUMBER\n"))
q = int(input("\nENTER ANOTHER PRIME NUMBER\n"))
msg = input("\nENTER MESSAGE\n")

e = []
d = []
temp = []
m = []
en = []


def prime(pr):

    j = int(math.sqrt(pr))

    for i in range(2, j + 1):

        if pr % i == 0:
            return 0

    return 1



if prime(p) == 0:
    print("\nWRONG INPUT")
    exit()

if prime(q) == 0 or p == q:
    print("\nWRONG INPUT")
    exit()


for ch in msg:
    m.append(ord(ch))


n = p * q
t = (p - 1) * (q - 1)



def cd(x):

    k = 1

    while True:

        k = k + t

        if k % x == 0:
            return k // x


def ce():

    k = 0

    for i in range(2, t):

        if t % i == 0:
            continue

        if prime(i) == 1 and i != p and i != q:

            e.append(i)

            val = cd(i)

            if val > 0:

                d.append(val)

                k += 1

            if k == 99:
                break


ce()


print("\nPOSSIBLE VALUES OF e AND d ARE")

for i in range(len(e)):
    print(e[i], "\t", d[i])



key = e[0]

for i in range(len(msg)):

    pt = m[i]

    pt = pt - 96

    k = 1

    for j in range(key):
        k = k * pt

    k = k % n

    temp.append(k)

    ct = k + 96

    en.append(chr(ct))


print("\nTHE ENCRYPTED MESSAGE IS")

for ch in en:
    print(ch, end="")



key = d[0]

dec = []

for i in range(len(en)):

    ct = temp[i]

    k = 1

    for j in range(key):
        k = k * ct

    k = k % n

    pt = k + 96

    dec.append(chr(pt))


print("\nTHE DECRYPTED MESSAGE IS")

for ch in dec:
    print(ch, end="")

.
.
.
.
.
.

5

p = 23
g = 7

a = 3
b = 6


A = pow(g, a, p)
B = pow(g, b, p)

print("Public values:")
print("A (Alice sends):", A)
print("B (Bob sends):", B)


shared_secret_alice = pow(B, a, p)
shared_secret_bob = pow(A, b, p)

print("\nShared secrets:")



.
.
.
..

...
.
.
..
..
.
.
.
.
p = 23;
g = 7;

a = 3;
b = 6;

// Public values
A = modulo(g^a, p);
B = modulo(g^b, p);

disp("Public values:");
disp("A (Alice sends):");
disp(A);

disp("B (Bob sends):");
disp(B);

// Shared secrets
shared_secret_alice = modulo(B^a, p);
shared_secret_bob = modulo(A^b, p);

disp("Shared secrets:");

disp("Alice's secret:");
disp(shared_secret_alice);

disp("Bob's secret:");
disp(shared_secret_bob);

disp("Match:");
disp(shared_secret_alice == shared_secret_bob);
print("Alice's secret:", shared_secret_alice)
print("Bob's secret:", shared_secret_bob)

print("\nMatch:", shared_secret_alice == shared_secret_bob)


