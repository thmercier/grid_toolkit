A grid toolkit
===========================

This toolkit is linked to the following paper:

T. Mercier, J. Jomaux, and E. De Jaeger, “Stochastic Programming for Valuing Energy Storage Providing Primary Frequency Control”.

It implements the model described in the paper, based on Rte's 2015 grid-frequency measurements, and enables the generation of scenarios of grid-frequency deviations over 15-minute time steps.

## Installation

```console
$ pip install grid_toolkit
```

## Use

```python
import grid_toolkit as grid

scenarios = grid.generate(n, length, [start_year, start_month, start_day, start_hour])
```

## Note on arguments

All arguments are integers with `n` being the number of scenarios you want to generate, `length` the number of time steps in the generated scenarios, `[start_year, start_month, start_day, start_hour]` is the starting datetime of the scenarios.

```python
[start_year, start_month, start_day, start_hour] = [2015, 1, 1, 0]
```

corresponds to 1 January 2015 at midnight. The ability to provide standard [`datetime`](https://docs.python.org/2/library/datetime.html#datetime-objects) objects will be added soon.

Note that daylight saving time is taken into account in the model.
