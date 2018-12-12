# gird

## display
Defines the elements as a grid container and establishes a new _**grid formatting context**_ for its contents

Values:
* __grid__ - generates a block-level grid
* __inline-grid__  - generates an inline-level grid

```
.container {
    display: grid | inline-grid
}
```

## grid-template-columns  grid-template-rows
Defines the columns and rows of the grid with a space-seperated list of values. The values represent the track size, ant the space between them represents the grid line.

Values:
* track-size - can be a length, a percentage, or a fration of the free space in the grid(using the fr unit)
* line-name - an arbitrary name of your choosing

```
.container {
    grid-template-colunms: 40px 50px auto 50px 40px;
    grid-template-rows: 25% 100px auto;
}
```
explicitly name the lines

```
.container {
    grid-template-columns: [first] 40px [line2] 50px [lin3] auto [col4-start] 50px [five] 40px [end];
    grid-template-rows: [row1-start] 25% [row1-end] 100px [third-line] auto [last-line];
}
```

## grid-template-areas
Defines a grid tempalte by referencing the names of the grid areas which are specified with the grid-area property. Repeating the name of a grid area causes the contents to span those cells. A period signifies an empty cell. The syntax itself provides a visualization of the structure of the grid.

Values:
* __grid-area-name__ - the name of a grid area specified with grid area
* __.__ - a period signifies an empty grid cell
* none - no grid areas are defined

```
.container {
    overflow: hidden;
    width: 600px;
    height: 600px;
    display: grid;
    grid-template-columns: 150px 150px 150px 150px;
    grid-template-rows: auto;
    grid-template-areas:
        "header header header header" 
        "main main . sidebar"
        "footer footer footer footer";
    grid-gap: 10px 15px;
    border-radius: 50px;
}
.item-a {
    grid-area: header;
    background-color: orange;
}
.item-b {
    grid-area: main;
    background-color: lightblue;
}
.item-c {
    grid-area: sidebar;
    background-color: salmon;
}
.item-d {
    grid-area: footer;
    background-color: lightgreen;
}
```

## grid-template
A shorthand for setting ```grid-template-rows```, ```grid-template-columns```, and ```grid-template-areas``` in a single declaration.

Values:
* __none__ - sets all three properties to their initial values
* __grid-template-rows__/__grid-template-columns - sets ```grid-template-columns``` and ```grid-template-rows``` to the specified values, respectively, and sets ```grid-template-areas``` to none

```
.container {
    grid-template: none | <grid-tempalte-rows> / <grid-template-columns>;
}
```

## grid-column-gap grid-row-gap
Specifies the size of the grid lines. You can think of it like setting the width of the gutters between the columns/rows.

Values:
* __line-size__ - a length value

```
.container {
    grid-column-gap: <line-size>;
    grid-row-gap: <line-size>;
}
```

## grid-gap
A shorthand for ```grid-column-gap``` and ```grid-row-gap```
Values:
* __grid-column-gap__ __grid-row-gap__ -length values
```
.container {
    grid-gap: <grid-row-gap> <grid-column-gap>;
}
```