# Задача

Напишите интерпретатор простого императивного языка со следующей грамматикой:
    
```
    <Program>     ::= read <Var>, ..., <Var>; <BasicBlock>+
    <BasicBlock>  ::= <Label>: <Assignment>* <Jump>
    <Assignment>  ::= <Var> := <Expr>;
    <Jump>        ::= goto <Label>;
                      if <Expr> goto <Label> else <Label>;
                      return <Expr>;
    <Expr>        ::= <Constant>
                      <Op> <Expr>, ..., <Expr>
    <Label>       ::= любой идентификатор или число
    <Op>          ::= базовые операции, такие как сложение и сравнение
```
К примеру, реализация алгоритма Евклида будет выглядить следующим образом:

```
    read x, y;
    1: if x = y goto 7 else 2;
    2: if x < y goto 5 else 3;
    3: x := x - y;
       goto 1;
    5: y := y - x;
       goto 1;
    7: return x;
```
Интерпретатор должен работать не c кодом программы, а прямо с абстрактным синтаксическим деревом, 
таким образом, лексер и парсер реализовывать не надо.

Языки реализации:
* Java
* Kotlin
* Python
