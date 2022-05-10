# ParameterFiddler

The parameterfiddler allows to modify parameters and compare results. It was written to improve bots on [CodinGame](https://www.codingame.com/).

Note: making a bot stronger against itself doesn't necessarily mean, that it performs better in the arena as well.

## How it works

This program will modify one parameter at a time: for a given delta, it will test the outcome of multiplying the parameter by
(1+delta) and (1-delta). With these 3 points (together with not changing the parameter at all, what is assumed to give a 50%
winrate against itself), a parabola going through all of these points will be computed. The highest point of the parabola
will be evaluated in another run, the parameter value with the best outcome is kept.

All parameters will be changed one after another in the order of their appearence in the parameter input file.
When changing all parameters, the process with start from the beginning, until the program gets terminated.
The best parameters found so far will be in the passed parameter file, replacing original values.

It is also possible to fight against several bots. In that case the average winrate will be taken to evaluate a parameter change.

## Usage

To use this program, you first need the [cg-brutaltester](https://github.com/dreignier/cg-brutaltester)
and a referee:
* [Ghost in the Cell](https://github.com/dreignier/cg-referee-ghost-in-the-cell)
* [Coders of the Caribbean](https://github.com/kevinsandow/cg-referee-coders-of-the-caribbean)
* [Code4Life](https://github.com/kevinsandow/cg-referee-code4life)
* [Wondev Woman](https://github.com/kevinsandow/cg-referee-wondev-woman)
* [Coders Strike Back](https://github.com/robostac/coders-strike-back-referee)
* [Back To The Code, CodeBusters, Game Of Drones, HyperSonic, Smash The Code, The Great Escape, Tron](https://github.com/eulerscheZahl/RefereeCollection)

Furthermore you have to prepare your program to read variables from a file passed as command line argument (see example folder).

## Compiling

To compile this program, use maven; Installation instructions can be found [here](https://maven.apache.org/install.html)

Once maven is installed, run `mvn package`. This will create a file in  `target/` called `uber-parameterfiddler-X.Y.jar`
This can then be invoked as given in the [example](./example/readme.md) 
