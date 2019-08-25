# phila_style

A data visualization style based on the [City of Philadelphia Digital Standards](https://standards.phila.gov/guidelines/design-development/brand-elements/color-palette/). Matplotlib and Altair themes are included by default.

## Color palettes

The default color palette is slightly tweaked from the palette defined by the Digital Standards. The list of colors can be retrieved using:

```python
from phila_style import *

# default color palette with light/dark variations
default = get_default_palette()
light = get_light_palette()
dark = get_dark_palette()
```

Sequential color ramps can be constructed for any of the colors in the default color palettes. The color from the palette will be the midpoint of the color ramp.

```python
# get color ramp
ramp = get_color_ramp("blue", N=9)
```

The palette defined by the Digital Standards can also be loaded:

```python
standard = get_digital_standards()
```

## Matplotlib theme

'Dark' and 'light' mode themes are available

```python
from matplotlib import pyplot as plt
import numpy as np
from phila_style.matplotlib import get_theme

with plt.style.context(get_theme(mode="dark")):
    for i in range(7):
        plt.plot(np.random.random(size=10))
```

## Altair theme

Heavily inspired by the [LA Times Altair theme](https://github.com/datadesk/altair-latimes), but using the
recommended color palette from the City of Philadelphia's Digital Standards.

```python
from phila_style.altair as get_theme
import altair as alt

# register and enable the theme
alt.themes.register('phila', get_theme)
alt.themes.enable('phila')
```
