## a)

- Ensin tein **C++** kielellä simppelin Hello World ohjelman

```c++
// hello.cpp

#include <iostream>

int main() {
    std::cout << "Hello World!";
    return 0;
}
```

- Sitten käänsin c++ ohjelman g++ kääntäjällä suoritettavaksi binääritiedostoksi nimeltä **hello**

```bash
$ g++ hello.cpp -o hello
```

- Tarkistin, että ohjelma toimii ajamalla sen

```bash
$ ./hello
Hello World!
```

- Seuraavaksi tarkastelin **hello** tiedostoa **file** komennolla ja sain selville, että tiedosto on **ELF 64-bit** tiedosto tarkoitettu Linuxille

![Alt text](images/h0_images/h0_1.png)

- Tarkastelin tiedostoa vielä HEX-muodossa komennolla **xxd**

![Alt text](images/h0_images/h0_2.png)

## Lähteet

- [terokarvinen.com](terokarvinen.com)
- [C++ "Hello, World!" Program](https://www.programiz.com/cpp-programming/examples/print-sentence)