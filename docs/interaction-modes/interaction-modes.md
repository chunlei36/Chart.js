# Interaction Modes

When configuring interaction with the graph via hover or tooltips, a number of different modes are available.

The modes are detailed below and how they behave in conjunction with the `intersect` setting.

## point
Finds all of the items that intersect the point.

```javascript
let chart = new Chart(ctx, {
    type: 'line',
    data: data,
    options: {
        tooltips: {
            mode: 'point'
        }
    }
})
```

## nearest
Gets the item that is nearest to the point. The nearest item is determined based on the distance to the center of the chart item (point, bar). If 2 or more items are at the same distance, the one with the smallest area is used. If `intersect` is true, this is only triggered when the mouse position intersects an item in the graph. This is very useful for combo charts where points are hidden behind bars.

```javascript
let chart = new Chart(ctx, {
    type: 'line',
    data: data,
    options: {
        tooltips: {
            mode: 'nearest'
        }
    }
})
```

## single (deprecated)
Finds the first item that intersects the point and returns it. Behaves like 'nearest' mode with intersect = true.

## label (deprecated)
See `'index'` mode

## index
Finds item at the same index. If the `intersect` setting is true, the first intersecting item is used to determine the index in the data. If `intersect` false the nearest item is used to determine the index. 

```javascript
let chart = new Chart(ctx, {
    type: 'line',
    data: data,
    options: {
        tooltips: {
            mode: 'index'
        }
    }
})
```

## x-axis (deprecated)
Behaves like `'index'` mode with `intersect = false`.

## dataset
Finds items in the same dataset. If the `intersect` setting is true, the first intersecting item is used to determine the index in the data. If `intersect` false the nearest item is used to determine the index.

```javascript
let chart = new Chart(ctx, {
    type: 'line',
    data: data,
    options: {
        tooltips: {
            mode: 'dataset'
        }
    }
})
```

## x
Returns all items that would intersect based on the `X` coordinate of the position only. Would be useful for a vertical cursor implementation. Note that this only applies to cartesian charts

```javascript
let chart = new Chart(ctx, {
    type: 'line',
    data: data,
    options: {
        tooltips: {
            mode: 'x'
        }
    }
})
```

## y
Returns all items that would intersect based on the `Y` coordinate of the position. This would be useful for a horizontal cursor implementation. Note that this only applies to cartesian charts.

```javascript
let chart = new Chart(ctx, {
    type: 'line',
    data: data,
    options: {
        tooltips: {
            mode: 'y'
        }
    }
})
```

# Events Configuration Property
**Type:** String[]
**Default:**  `["mousemove", "mouseout", "click", "touchstart", "touchmove", "touchend"]`
The `events` option defines the browser events that the chart should listen to for tooltips and hovering.

For example, to have the chart only respond to click events, you could do
```javascript
let chart = new Chart(ctx, {
    type: 'line',
    data: data,
    options: {
        // This chart will not respond to mousemove, etc
        events: ['click']
    }
});
```

# onClick Callback
**Type:** Function
**Default:** `null`
Called if the event is of type 'mouseup' or 'click'. Called in the context of the chart and passed the event and an array of active elements