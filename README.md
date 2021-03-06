# complex plotter

This is a program not really meant for widespread use that I've written for upcoming videos on my educational YouTube channel [Guru da Ciência](https://youtube.com/danielpetri).

It renders `.mp4` animations and `.png` plots of complex functions on the real and imaginary plane using `Haskell`, `gnuplot` and `ffmpeg`.

The <b>x</b> and <b>y</b> axis correspond to the real and imaginary components of the input; the <b>z</b> axis shows the magnitude of the output. The phase of the output is shown through color.
Alternatively, in the files labeled with <b>phase</b> instead of <b>magnitude</b>, the third dimension stands for the complex argument of the resulting number and the fourth for the magnitude <b>|f(z)|</b>.

The function `z^2 + c` is used as an example in the included video files, where <b>z</b> is a complex number of the form `a + bi`. By calling `animate $ functionList 1 (-25) 25`,
the frames `z^2 - 25 ... z^2 + 25` are generated and encoded into a `.mp4` file.

Individual frames can be generated with plot by passing it a Haskell function, a certain step size and an interval [a,b]:

`plot square 0.5 0 10 -- output.png in ./pics`

By editing the gnuplot `.plt` files, borders, tics, title, point type, line width etc. can be specified.

Interactive versions can be found in the folder `./gnuplot-interactive` which use the information contained in `data.txt` created by the `plot` method.

The pics folder needs to be empty before calling animate or plot.
