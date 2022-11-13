# Guess-The-Number-By-IA-Script

## Getting Started

1. Clone the repository
2. Join to the correct path of the clone
3. Use `python GuessTheNumberByIA.py` to execute script

## Description

I made a Python script that allows the AI to guess `X` amount of times the number that the user provided for the AI to try to guess.

## Technologies used

1. Python

## Libraries used

1. random
2. time

## Galery

![guessthenumberbyia](https://raw.githubusercontent.com/DiegoLibonati/DiegoLibonatiWeb/main/data/projects/Python/Imagenes/guessnumberuser-0.jpg)

![guessthenumberbyia](https://raw.githubusercontent.com/DiegoLibonati/DiegoLibonatiWeb/main/data/projects/Python/Imagenes/guessnumberuser-1.jpg)

![guessthenumberbyia](https://raw.githubusercontent.com/DiegoLibonati/DiegoLibonatiWeb/main/data/projects/Python/Imagenes/guessnumberuser-2.jpg)

![guessthenumberbyia](https://raw.githubusercontent.com/DiegoLibonati/DiegoLibonatiWeb/main/data/projects/Python/Imagenes/guessnumberuser-3.jpg)

## Portfolio Link

`https://diegolibonati.github.io/DiegoLibonatiWeb/#/projects?q=Guess%20The%20Number%20By%20IA%20Script`

## Video

https://user-images.githubusercontent.com/99032604/198900547-66bc8d9a-1698-4ba3-8f3d-5e7315c864af.mp4

## Documentation

These are the imports used in this script:

```
from random import randint
from time import sleep
```

In this list will be stored all the numbers that the AI has already chosen:

```
numbers_chosen = []
```

First the user will be asked a maximum number to choose a number within that range so that the AI will know between which range to start trying to guess numbers:

```
ranged_selected = int(input("Select a max ranged: "))
random_number = int(input(f"Select a random number in range: {ranged_selected}: "))
```

If the user tries to choose a number beyond the range or less than 0, they will continue to be prompted until they choose a correct number:

```
while random_number > ranged_selected or random_number < 0:
    random_number = int(input(f"Select a random number in range: {ranged_selected}: "))
```

In this case, the computer will choose a random integer within the range that the user has set. And it will add that number to the list of played numbers so that it does not repeat it:

```
ia_number_selected = randint(0, ranged_selected)
numbers_chosen.append(ia_number_selected)
print(f"The computer plays: {ia_number_selected}")
sleep(1)

```

As long as the computer does not guess which number is hidden, it will continue playing. In case of guessing, it will exit the while and display a message on the console that it has guessed the number:

```
while ia_number_selected != random_number:
    ia_number_selected = randint(0, ranged_selected)
    if ia_number_selected not in numbers_chosen:
        numbers_chosen.append(ia_number_selected)
        print(f"Oops, you fail. Try again bot. The computer plays: {ia_number_selected}")
        sleep(1)
    else:
        pass

print("The computer finally find the secret number.")
```
