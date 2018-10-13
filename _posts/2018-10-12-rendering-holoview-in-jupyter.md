---
published: false
layout: post
category: Dev
tags:
  - python
  - workflow
  - visualization
---
## Rendering Holoviews in Jupyter

For some unknown reason, I could not get holoview visualizations to render in Jupyter Notebook for the longest time. I finally found the solution here: https://github.com/ioam/holoviews/issues/2587 by explicitly using hv.ipython.display.

    def render(obj):
        plot = hv.renderer('bokeh').get_plot(obj)
        hv.ipython.display(plot)