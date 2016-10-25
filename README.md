## AiSD

## PYTHON w wersji 3.x

## Ćwiczenie **2**
Kod funkcji szyfrującej nie jest elegancki. Zawiera długą listę warunków if.. elif. Uprość kod stosując pętlę for. Upewnij się, że po modyfikacji funkcja przechodzi wszystkie testy.

**Pierwotny kod:** 

```
# -*- encoding: utf8 -*-

# Poniżej znajduje się funkcja szyfrująca wiadomości
# szyfrem gaderypoluki (więcej informacji tutaj: https://pl.wikipedia.org/wiki/Gaderypoluki)
# upewnij się, że funkcja działa poprawnie

def gaderypoluki(wiadomosc):
    szyfr = ''
    for i in range(len(wiadomosc)):
        if wiadomosc[i] == 'g':
            szyfr += 'a'
        elif wiadomosc[i] == 'a':
            szyfr += 'g'
        elif wiadomosc[i] == 'd':
            szyfr += 'e'
        elif wiadomosc[i] == 'e':
            szyfr += 'd'
        elif wiadomosc[i] == 'r':
            szyfr += 'y'
        elif wiadomosc[i] == 'y':
            szyfr += 'r'
        elif wiadomosc[i] == 'p':
            szyfr += 'o'
        elif wiadomosc[i] == 'o':
            szyfr += 'p'
        elif wiadomosc[i] == 'l':
            szyfr += 'u'
        elif wiadomosc[i] == 'u':
            szyfr += 'l'
        elif wiadomosc[i] == 'k':
            szyfr += 'i'
        elif wiadomosc[i] == 'i':
            szyfr += 'k'

    return szyfr
```

**Kod zmodyfikowany przeze mnie:** 

```
tuplelist = [("g", "a"), ("d", "e"), ("r", "y"), ("p", "o"), ("l" ,"u"), ("k", "i"), ("G", "A"), ("D", "E"), ("R", "Y"), ("P", "O"), ("L" ,"U"), ("K", "I")]

def gaderypoluki(wiadomosc):
    szyfr = ""
    check = 0

    for i in range(len(wiadomosc)):
        for x,y in tuplelist:
            if wiadomosc[i] == x:

                szyfr += y
                check = 1
            if wiadomosc[i] == y:

                szyfr += x
                check = 1


        if check == 0:
            szyfr += wiadomosc[i]
        check = 0


    print (szyfr)
    return szyfr

gaderypoluki('ala ma kota')
```



## Ćwiczenie **3**

Stwórz nową funkcję szyfrującą podstawieniowy, umożliwiającą zastosowanie dowolnego szyfru podstawieniowego. Funkcja być również pokryta testami. Funkcja powinna przyjmować 2 argumenty: wiadomosc i klucz, gdzie klucz to lista zawierająca krotki z podstawieniami.
Przykładowo: wywołanie podstawieniowy('galop', [('g','a'),('d','e'),('r','y'),('p','o'),('l','u'),('k','i')]) powinno zwrócić agupo.


```
def podstawieniowy(wiadomosc, kod):
    szyfr = ""
    check = 0
    tuplelist = kod

    for i in range(len(wiadomosc)):
        for x,y in tuplelist:
            if wiadomosc[i] == x:
                szyfr += y
                check = 1
            if wiadomosc[i] == y:
                szyfr += x
                check = 1
        if check == 0:
            szyfr += wiadomosc[i]
        check = 0


    print (szyfr)
    return szyfr





podstawieniowy ('galop', [('g','a'),('d','e'),('r','y'),('p','o'),('l','u'),('k','i')])
```
