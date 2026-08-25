## a)

- Ensin tein **C++** kielellä simppelin Hello World ohjelman

```c++
#include <iostream>

int main() {
    std::cout << "Hello World!";
    return 0;
}
```

- Sitten käänsin c++ ohjelman g++ kääntäjällä suoritettavaksi binääritiedostoksi nimeltä **hello**

```co
$ g++ hello.cpp -o hello
```

- Tarkistin, että ohjelma toimii ajamalla sen

```bash
$ ./hello
Hello World!
```

- Seuraavaksi tarkastelin **hello** tiedostoa **file** komennolla ja sain selville, että tiedosto on **ELF 64-bit** tiedosto tarkoitettu Linuxille

![[h0_1.png]]

- Tarkastelin tiedostoa vielä HEX-muodossa komennolla **xxd**

![[h0_2.png]]

## Lähteet

- [terokarvinen.com](terokarvinen.com)
- [C++ "Hello, World!" Program](https://www.programiz.com/cpp-programming/examples/print-sentence)