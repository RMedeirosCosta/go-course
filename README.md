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

Variáveis de ambiente do pacote `runtime`

**GOOS**: Sistema operacional (android, darwin, dragonfly, netbsd, linux)
**GOARCH**: Arquitetura: 386, amd64, arm

### String type

- É possível declarar com aspas duplas e com acento grave (crase, backtick/backquote). Acento grave serve para declara raw string literals (Java 12, String Templates ECMAScript 2015) 
- String é um *alias* para slice of bytes, algo como array de bytes;
- String é imutável;

``` go
package main

import "fmt"

func main() {
	montanas_quote := `Say hello to my little,
 friend!`
	fmt.Println(montanas_quote)
	fmt.Printf("%T\n", montanas_quote)

	byte_string := []byte(montanas_quote)
	fmt.Println(byte_string)
	fmt.Printf("%T\n", byte_string)

	for i := 0; i < len(montanas_quote); i++ {
		fmt.Printf("%#U ", montanas_quote[i])
	}

	fmt.Println("")

	for i, v := range montanas_quote {
		fmt.Printf("na posição %d nós temos o hexadecimal %#x\n", i, v)
	}
}
```

``` shell
Say hello to my little,
 friend!
string
[83 97 121 32 104 101 108 108 111 32 116 111 32 109 121 32 108 105 116 116 108 101 44 10 32 102 114 105 101 110 100 33]
[]uint8
U+0053 'S' U+0061 'a' U+0079 'y' U+0020 ' ' U+0068 'h' U+0065 'e' U+006C 'l' U+006C 'l' U+006F 'o' U+0020 ' ' U+0074 't' U+006F 'o' U+0020 ' ' U+006D 'm' U+0079 'y' U+0020 ' ' U+006C 'l' U+0069 'i' U+0074 't' U+0074 't' U+006C 'l' U+0065 'e' U+002C ',' U+000A U+0020 ' ' U+0066 'f' U+0072 'r' U+0069 'i' U+0065 'e' U+006E 'n' U+0064 'd' U+0021 '!' 
na posição 0 nós temos o hexadecimal 0x53
na posição 1 nós temos o hexadecimal 0x61
na posição 2 nós temos o hexadecimal 0x79
na posição 3 nós temos o hexadecimal 0x20
na posição 4 nós temos o hexadecimal 0x68
na posição 5 nós temos o hexadecimal 0x65
na posição 6 nós temos o hexadecimal 0x6c
na posição 7 nós temos o hexadecimal 0x6c
na posição 8 nós temos o hexadecimal 0x6f
na posição 9 nós temos o hexadecimal 0x20
na posição 10 nós temos o hexadecimal 0x74
na posição 11 nós temos o hexadecimal 0x6f
na posição 12 nós temos o hexadecimal 0x20
na posição 13 nós temos o hexadecimal 0x6d
na posição 14 nós temos o hexadecimal 0x79
na posição 15 nós temos o hexadecimal 0x20
na posição 16 nós temos o hexadecimal 0x6c
na posição 17 nós temos o hexadecimal 0x69
na posição 18 nós temos o hexadecimal 0x74
na posição 19 nós temos o hexadecimal 0x74
na posição 20 nós temos o hexadecimal 0x6c
na posição 21 nós temos o hexadecimal 0x65
na posição 22 nós temos o hexadecimal 0x2c
na posição 23 nós temos o hexadecimal 0xa
na posição 24 nós temos o hexadecimal 0x20
na posição 25 nós temos o hexadecimal 0x66
na posição 26 nós temos o hexadecimal 0x72
na posição 27 nós temos o hexadecimal 0x69
na posição 28 nós temos o hexadecimal 0x65
na posição 29 nós temos o hexadecimal 0x6e
na posição 30 nós temos o hexadecimal 0x64
na posição 31 nós temos o hexadecimal 0x2
```

### Numeral Systems
#### Os mais comuns
- Binário: ![](https://i.imgur.com/YGGVzt3.gif)
- Octal: ![](https://i.imgur.com/sy2eTTU.gif)
- Decimal: ![](https://i.imgur.com/lOusGOZ.gif)
- Hexadecimal: ![](https://i.imgur.com/TUSWQKT.gif)

``` go
package main

import "fmt"

func main() {
	shinobi := "Uchiha, Susuke"
	fmt.Println(shinobi)

	byte_slice := []byte(shinobi)
	fmt.Println(byte_slice)

	n := byte_slice[0]
	fmt.Println(n)
	fmt.Printf("%T\n", n)
	fmt.Printf("%b\n", n)
	fmt.Printf("%#X\n", n)
}
```

``` shell
Uchiha, Susuke
[85 99 104 105 104 97 44 32 83 117 115 117 107 101]
85
uint8
1010101
0X55
``` 

### Constants

``` go
package main

import "fmt"

const (
	beast_number          = 666
	typed_constant string = "My typed constant"
)

func main() {
	fmt.Println(beast_number)
	fmt.Println(typed_constant)
}
```
 
``` shell
666
My typed constant
```

## Iota

Incrementa automaticamente

``` go
package main

import "fmt"

const (
	a = iota
	b = iota
	c = iota
)

const (
	d = iota
	e
	f
)

func main() {
	fmt.Println(a)
	fmt.Println(b)
	fmt.Println(c)
	fmt.Println(d)
	fmt.Println(e)
	fmt.Println(f)
}
```

```shell
0
1
2
0
1
2
```

### Bit Shifting

> Bitwise operation
> In digital computer programming, a bitwise operation operates on one or more bit patterns or binary numerals at the level of their individual bits. It is a fast, simple action directly supported by the processor, and is used to manipulate values for comparisons and calculations.
> 
Operadores: `<< left shift`, `>> right shif`

##### Primeiro exemplo
``` go
package main

import "fmt"

func main() {
	x := 4
	fmt.Printf("%d\t\t%b\n", x, x)

	y := x << 1
	fmt.Printf("%d\t\t%b", y, y)
}
```

``` shell
4		100
8		1000
```
##### Segundo exemplo
``` go
package main

import "fmt"

func main() {
	kb := 1024
	mb := 1024 * kb
	gb := 1024 * mb

	fmt.Printf("%d\t\t\t%b\n", kb, kb)
	fmt.Printf("%d\t\t\t%b\n", mb, mb)
	fmt.Printf("%d\t\t%b\n", gb, gb)
}
```

``` shell
1024			10000000000
1048576			100000000000000000000
1073741824		1000000000000000000000000000000
```

##### Terceiro exemplo
``` go 
package main

import "fmt"

const (
	_  = iota
	kb = 1 << (iota * 10)
	mb = 1 << (iota * 10)
	gb = 1 << (iota * 10)
)

func main() {
	fmt.Printf("%d\t\t\t%b\n", kb, kb)
	fmt.Printf("%d\t\t\t%b\n", mb, mb)
	fmt.Printf("%d\t\t%b\n", gb, gb)
}
```

``` shell
1024			10000000000
1048576			100000000000000000000
1073741824		1000000000000000000000000000000
```

# Section 8 Control flow
## For
* O único laço de repetição é o `for` (não existe o `while`)
	```go
	i := 0
	// usando for como while
		for {
			if i > 5 {
				break
			}
			fmt.Println("Value: ", i)
			i++
		}
	```
* Estrutura: 
	```go
	for init; condition; post{
	}
	```
* For statement (a iteração pode ser controlada de 3 formas)
```go
ForStmt = "for" [ Condition | ForClause | RangeClause ] Block .
Condition = Expression .
```
  * condição única (Condition): https://play.golang.org/p/zBoGpA2h6lz
	```go
	i := 0
	for i < 5 {
		fmt.Println("Value: ", i)
		i++
	}
	```
  * com clausula for (ForClause): https://play.golang.org/p/hZkGG6DhED6
	```go
	for i := 0; i < 5; i++ {
		fmt.Println("Value: ", i)
	}
	```
  * com range (RangeClause): https://play.golang.org/p/sWXkcrJDMtz
	```go
	i := []string{"Pipoca", "doce"}
	for _, x := range i {
		fmt.Println("Value: ", x)
	}
	```