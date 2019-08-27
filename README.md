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

### Numeric Types
> uint8       the set of all unsigned  8-bit integers (0 to 255)
> uint16      the set of all unsigned 16-bit integers (0 to 65535)
> uint32      the set of all unsigned 32-bit integers (0 to 4294967295)
> uint64      the set of all unsigned 64-bit integers (0 to 18446744073709551615)
> 
> int8        the set of all signed  8-bit integers (-128 to 127)
> int16       the set of all signed 16-bit integers (-32768 to 32767)
> int32       the set of all signed 32-bit integers (-2147483648 to 2147483647)
> int64       the set of all signed 64-bit integers (-9223372036854775808 to 9223372036854775807)
> 
> float32     the set of all IEEE-754 32-bit floating-point numbers
> float64     the set of all IEEE-754 64-bit floating-point numbers
> 
> complex64   the set of all complex numbers with float32 real and imaginary parts
> complex128  the set of all complex numbers with float64 real and imaginary parts
> 
> byte        alias for uint8
> rune        alias for int32

Tipos numéricos predeclarados que serão decididos pelo compilador dependendo da arquitetura que esta sendo feito a compilação.

> uint     either 32 or 64 bits
> int      same size as uint
> uintptr  an unsigned integer large enough to store the uninterpreted bits of a pointer value

uintptr: é um tipo para tratar um ponteiro com um inteiro positivo, para facilitar uma operação aritmética específica. Pode-se pensar como a tradução de um ponteiro para o índice que ele representa no espaço de memória virtual

``` go
package main

import "fmt"

func main() {
	pi := 3.14159265358979323846264
	fmt.Printf("PI %v is a %T", pi, pi)
}
```
``` shell
PI 3.141592653589793 is a float64
```

