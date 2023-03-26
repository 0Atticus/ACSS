# ACSS

> A CSS precompiler written in Ruby.

> This project is a work in progress.


## Installation

>Make suere [Ruby](https://www.ruby-lang.org/en/) is installed.

> Clone this repository.
```bash
git clone https://github.com/0Atticus/acss

```

>Then run this command to set up the acss function:
```bash
acss(){ bash ~/acss/acss.sh $1 $2 $3; }
```

## Usage & Documentation


>To compile a text file to a css file, run this command
```bash
acss source.txt destination.css
```
>or use this to compile continuously:
```bash
acss --watch  source.txt destination.css
```

>this program is whitespace sensitive, so use spaces where shown and write one statement per line

### Variable Definition and "Printing"

> To define a variable use "name = value"

> To "print" a variable, which writes it to the output file, use "!name"

>Here's an example of an input and output file:

```css
string = "Hello, World!"
array = [1, 2, 3]

!string
!array
```

```css
Hello, World!
["1", "2", "3"]
```

## Iterating

>to iterate over a range or array, use "for variable in range ... end"

>Here's an example of an input and output file

```css
for i in 3
!i
end
```

```css
0
1
2
```

> you can also iterate over arrays, using "!ix" as the index

> Here's an example of an input and output file

```css
array = [a, b, c]

for i in array
!ix : !i
end
```

```css
0 : a
1 : b
2 : c
```

## Usage Examples

>Using acss to apply a color scheme to many elements

```css
colors = background: #FFF; color: #000; border-color: #000;

p {
    !colors
}

h1 {
    !colors
}

```

>Using acss to create a simple color-changing background

```css
@keyframes color-change {
for i in 100

!i% {background: linear-gradient(to right, red !i%, black 0%);}

end
}
```
