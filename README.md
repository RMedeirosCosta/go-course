## go-course

### Bool type
- Zero value: `false`;
- Operators: `==`, `<=`, `>=` e etc;
- Não tem triplo igual como no Javascript (estritamente igual);
- Igual é para atribuição, duplo iguais é operator

``` go
package main

import "fmt"

func main() {
	a := 7
	b := 42
	fmt.Println(a == b)
}
```

### How Computer Works
- Computadores rodam em eletricidade;
- Eletricidade tem dois estados: **ON** e **OFF**
- Alusao com o Halloween americano (Ligado ok, desligado cai fora);
    - Comparação com o sistema binário com luz de varanda do Halloween:
        -    1 luz de varanda: 2 mensagens;
        -    2 luzes de varanda: 4 mensagens;
        -    3 luzes de varanda: 8 mensagens;
        -    4 luzes de varanda: 16 mensagens;
        -    5 luzes de varanda: 32 mensagens;
        -    6 luzes de varanda: 64 mensagens;
        -    7 luzes de varanda: 128 mensagens;
        -    8 luzes de varanda: 256 mensagens;
        ![](https://i.imgur.com/9Eo0DOB.png)

- "Coding schemes"
    - ASCII;
    - UTF-8;
    - W Europe;
    - JIS;

- Mensurando bits
    - 1 bit
    - 8 bits = byte;
    - 1000 bytes = kb;
    - 1000 kb = mb;
    - 1000 mb = gb;
    - 1000 gb  tb;
    
Primeiro bug encontrado em **1947** pela cientista da computação **Grace Hopper**, literalmente encontrou *"debugando"* a máquina;

Intel: Integrated Eletronics

**Moore's Law:** a observação que o número de transistors dobra a cada dois anos. (Isso talvez não seja válido hoje em dia)

##### Gerações de Computadores
1. Tubos a vácuo;
2. Transistores;
3. Circuitos Integrados (chips, Silicon Wafers);
4. Microprocessadores (cpu's);

Dica de filme: [Jogo da Imitação](https://www.rottentomatoes.com/m/the_imitation_game/)

