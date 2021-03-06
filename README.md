# mplanimations

A module I created that works with matplotlib to create some simple transitions that can be easily applied to various aspects of a plot. The documentation for each function currently available is available below.

Below are a few examples of animations I have made using this module paired with matplotlib. The code is available in the folders along with a brief explanation of what is being shown.

<img src="HuygensPrinciple/HuygensPrinciple.gif" width="45%" title="Huygen's Principle"/> <img src="UncertaintyPrinciple/UncertaintyPrinciple.gif" width="45%" title="Uncertainty Principle"/>

<img src="SnellsLaw/SnellsLaw.gif" width="45%" title="Snell's Law"/> <img src="SphereRefraction/SphereRefraction.gif" width="45%" title="Sphere Refraction"/>

## Requirements:

- matplotlib and NumPy must be installed.
- Interval in FuncAnimation must match interval used by mplanimations; default is 20, but it can be changed by changing `mplanimations.interval`.
- An object oriented approach must be used. For example, the axes should be created as `fig, ax = plt.subplots()`.
- To use the functions of mplanimations, you must place mplanimations in the folder of the file you are trying to use mplanimations in. This means if you download this repository and try to run one of the animations, you must place mplanimations in the same folder as the animation you are trying to run.


## Transition Functions:


### Alpha Transition
Creates a smooth transition between two alpha values.

`alpha_transition(i, starttime, alpha1, alpha2, transitionline, transition_time=1, transition_type=sine)`
- `i`: the index required by the FuncAnimation method
- `starttime`: the time at which the transition should start, in seconds
- `alpha1`: the initial alpha value
- `alpha2`: the final alpha value
- `transitionline`: the line for which the data will be updated; must be created before use of this function
- `transition_time`: the amount of time the transition will take, in seconds; default value is 1 second
- `transition_type`: the type of transition that will be displayed; options are `mplanimations.sine` and `mplanimations.linear`; default is `mplanimations.sine`

### Axis Transition
Creates a smooth transition for the axis limits.

`axis_transition(i, starttime, xlim1, xlim2, ylim1, ylim2, axis, transition_time=1, transition_type=sine)`
- `i`: the index required by the FuncAnimation method
- `starttime`: the time at which the transition should start, in seconds
- `xlim1`: a list that contains the starting x limits; e.g. `[-2, 2]`
- `xlim2`: a list that contains the ending x limits; e.g. `[-4, 4]`
- `ylim1`: a list that contains the starting y limits
- `ylim2`: a list that contains the ending y limits
- `axis`: the axis the transition should take place on; e.g. if `fig, ax = plt.subplots()` is used, axis should be `ax`
- `transition_time`: the amount of time the transition will take, in seconds; default value is 1 second
- `transition_type`: the type of transition that will be displayed; options are `mplanimations.sine` and `mplanimations.linear`; default is `mplanimations.sine`


### Color Transition
Creates a smooth transition between two colors.

`color_transition(i, starttime, cmap, c1, c2, transitionline, transition_time=1, transition_type=sine)`
- `i`: the index required by the FuncAnimation method
- `starttime`: the time at which the transition should start, in seconds
- `cmap`: the color map to be used; e.g. `plt.cm.jet` is a valid option
- `c1`: a float between 0 and 1 inclusive that indicates the starting color
- `c2`: a float between 0 and 1 inclusive that indicates the ending color
- `transitionline`: the line for which the data will be updated; must be created before use of this function; e.g. `tline = ax.plot(x, y)` gives the valid option `tline` for object
- `transition_time`: the amount of time the transition will take, in seconds; default value is 1 second
- `transition_type`: the type of transition that will be displayed; options are `mplanimations.sine` and `mplanimations.linear`; default is `mplanimations.sine`


### Dot Transition
Creates a smooth transition for changing the dot size on a scatter plot.

`dot_transition(i, starttime, size1, size2, dot, transition_time=1, duration='inf', transition_type=sine)`
- `i`: the index required by the FuncAnimation method
- `starttime`: the time at which the addition should start, in seconds
- `size1`: the initial size of the dot
- `size2`: the final size of the dot
- `dot`: the scatter plot for which the dot size will be updated (e.g. `dot = ax.scatter(0, 0)`)
- `transition_time`: the amount of time the transition will take, in seconds; default value is 1 second
- `duration`: the amount of time, in seconds, the dot will be on the screen before the exit transition begins; default is `inf` for infinity, but any other must be integers or floats
- `transition_type`: the type of transition that will be displayed; options are `mplanimations.sine` and `mplanimations.linear`; default is `mplanimations.sine`


### Line Transition
Creates a smooth transition between two functions of x.

`line_transition(i, starttime, yvals1, yvals2, transitionline, transition_time=1, transition_type=sine)`
- `i`: the index required by the FuncAnimation method
- `starttime`: the time at which the transition should start, in seconds
- `yvals1`: the y values of the initial function in a numpy array; in the form of some function performed on xvals (e.g. xvals**2)
- `yvals2`: the y values of the final function in a numpy array; in the form of some function performed on xvals (e.g. `xvals**3`)
- `transitionline`: the line for which the data will be updated; must be created before use of this function
- `transition_time`: the amount of time the transition will take, in seconds; default value is 1 second
- `transition_type`: the type of transition that will be displayed; options are `mplanimations.sine` and `mplanimations.linear`; default is `mplanimations.sine`


### Parametric Transition
Creates a smooth transition between two sets of parametric equations.

`par_transition(i, starttime, xvals1, xvals2, yvals1, yvals2, transitionline, transition_time=1, transition_type=sine)`
- `i`: the index required by the FuncAnimation method
- `starttime`: the time at which the transition should start, in seconds
- `xvals1`: the numpy array that contains the initial x values; must be linearly spaced for sinusoidal transition
- `xvals2`: the numpy array that contains the final x values; must be linearly spaced for sinusoidal transition
- `yvals1`: the y values of the initial function in a numpy array; in the form of some function performed on xvals (e.g. `xvals**2`)
- `yvals2`: the y values of the final function in a numpy array; in the form of some function performed on xvals (e.g. `xvals**3`)
- `transitionline`: the line for which the data will be updated; must be created before use of this function
- `transition_time`: the amount of time the transition will take, in seconds; default values is 1 second
- `transition_type`: the type of transition that will be displayed; options are `mplanimations.sine` and `mplanimations.linear`; default is `mplanimations.sine`


### Scatter Transition
Creates a transition between two different scatter plots.

`scatter_transition(i, starttime, xvals1, xvals2, yvals1, yvals2, scatterplot, carray1, carray2, transition_time=1, transition_type=sine)`
- `i`: the index required by the FuncAnimation method
- `starttime`: the time at which the transition should start, in seconds
- `xvals1`: the numpy array that contains the initial x values
- `xvals2`: the numpy array that contains the final x values
- `yvals1`: the y values of the initial function in a numpy array
- `yvals2`: the y values of the final function in a numpy array
- `scatterplot`: the scatter plots that will be changed
- `carray1`: the initial array that specifies the color of the scatter plot points
- `carray2`: the final array that specifies the color of the scatter plot points
- `transition_time`: the amount of time the transition will take, in seconds; default values is 1 second
- `transition_type`: the type of transition that will be displayed; options are `mplanimations.sine` and `mplanimations.linear`; default is `mplanimations.sine`

A few tips and warnings are in order for using this function. First, matplotlib scales the color based on the intial values that were plotted. This means that if the minimum and maximum of the two plots are different, then the final graph may not have the color scaled as you would like. To remedy this, I suggest using the `normalize` function that is in mplanimations so that the color scale is always the same.

### Variable Transition
Creates a variable that smoothy transitions between two values.

`var_transition(i, starttime, initial, final, transitionline, func, transition_time=1, transition_type=sine)`
- `i`: the index required by the FuncAnimation method
- `starttime`: the time at which the transition should start, in seconds
- `initial`: the initial value of the variable that will be changing
- `final`: the final value of the variable that will be changing
- `transitionline`: the line for which the value of the variable will be changed; must be created before use of this function; e.g. `tline, = ax.plot(x, y)` gives the valid option `tline` for object
- `func`: the function that the variable will be plugged into
- `transition_time`: the amount of time the transition will take, in seconds; default values is 1 second
- `transition_type`: the type of transition that will be displayed; options are `mplanimations.sine` and `mplanimations.linear`; default is `mplanimations.sine`


### Variable Transition 2
Creates a variable that smoothy transitions between two values.

A more versatile version of the Variable Transition function above.

`var_transition2(i, starttime, initial, final, transitionline, func, transition_time=1, transition_type=sine)`
- `i`: the index required by the FuncAnimation method
- `starttime`: the time at which the transition should start, in seconds
- `initial`: the initial value of the variable that will be changing
- `final`: the final value of the variable that will be changing
- `transition_time`: the amount of time the transition will take, in seconds; default values is 1 second
- `transition_type`: the type of transition that will be displayed; options are `mplanimations.sine` and `mplanimations.linear`; default is `mplanimations.sine`



## Effect Functions:


### Tail
Creates a fading tail behind moving scatter plot points.

`tail(xcoord, ycoord, ax, color, n)`
- `xcoord`: A list containing the current x coordinates of the points
- `ycoord`: A list containing the current y coordinates of the points
- `ax`: A scatter plot that will be updated with the dots to form the tail
- `color`: The color of the tail
- `n`: A parameter tuning the length of the tail (must be divisible by the number of elements in `xcoord` and `ycoord` lists)



## Notes:

- For the transitions to function as intended, the values for the lines must be evenly spaced. Using NumPy's `linspace(a, b, c)` method is recommended. New transitions types can be created by not using linear spacing with some cleverness.
- The number of intermediate lines for a transition is set as `1000/interval`.
- The interval set in mplanimation must be the same as the interval set for FuncAnimation for the timing to work correctly; default interval is 20
- Lines defined using the matplotlib plot() function that are going to be changed with the module must have a comma after them (e.g. `line1, = ax.plot(x, y)`).
- The interval can be changed with `mplanimations.transition.interval = number`, where number is the interval you want to set.
- All transition instances must be instantiated in advance; they can not be instantiated in the FuncAnimation animation function. This can be done by, for example, typing `t1 = mplanimations.transitions()` outside of the animation function, and then using this instance in the animation function.
- All transitions act on lines, dots, etc. already created outside of the animation function; they do not create the lines, dots, etc.; this means that the lines, dots etc. must be created outside of the animation function, and then they will be changed by the mplanimations methods.
- `dot_transition()` does not function correctly when the duration is less than or equal to `transition_time`.
- Exactly how the tails fade for the `tail` function can be changed if by changing `alpha_array = [(1/(n**2))*((i-n)**2) for i in range(n)]` in the mplanimations code. If you want it to fade faster a different function is needed; beware that the function must range between 0 and 1 for the `n` values.



## Useful Tips:

- Transitions can be instantiated in a list using the `for i in range()` command. They can then be accessed for the transitions. Alternatively this can be done in one line with `ts = [mplanimations.Transitions() for i in range(n)]`, where `n` is the number of transitions needed.
- Plots can be created in a list, but they must be followed by `[0]`. For example, `for i in range(10):` can be used for iteration, and then `lines.append(ax.plot(x, y)[0])` to create the list "lines" with 10 lines created. This too can be done in one line using the method mentioned in the previous tip.
- The current time in the animation (in seconds) can be accessed with the function `mplanimations.time(i)`, where `i` is the counter that is required by `FuncAnimation`.
- `alpha_transition` and `color_transition` also work for text.
- The `FuncAnimation` method interprets the interval as milliseconds, so if you want an animation to last `x` seconds, you need `x/(interval/1000)` frames; using the default of 20ms for the interval, this is simply `x/.02` frames.
