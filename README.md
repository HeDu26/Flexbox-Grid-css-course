# Learning Flexbox and Grid CSS

- ## Índice

  - [Flexbox CSS](#flexbox-css)
    - [Properties for the parent](#properties-for-the-parent)
    - [Properties for the Children](#properties-for-the-children-flex-items)
  - [Grid CSS](#grid-css)
    - [Explicit Grid](#1-explicit-grid)
      - [Grid lines](#11-grid-lines)
      - [Grid Areas](#12-grid-areas)
    - [Implicit Grid](#2-implicit-grid)
    - [Grid Flow](#3-grid-flow)
    - [Grid flow Dense](#4-grid-flow-dense)
    - [Superposition](#5-superposition)
    - [Ordering](#6-ordering)
    - [ item align](#7-item-align)
    - [Track align](#8-track-align)
    - [Max and min of the Grid tracks](#9-max-and-min-of-the-grid-tracks)
    - [Repeating patterns](#10-repeating-patterns)
    - [Responsive Dinamic Grids without media queries](#11-dinamic-grids-responsive-without-media-queries)
    - [Nested grid & subgrids](#12-nested-grid--subgrids)

## Flexbox CSS

- one dimensional (row or column)
- Flexbox is a tool from CSS whose main purpose helps to order the items and widgets in a user interface (Cards, Modals, Forms, Menus, etc.)

![Basics and terminology](https://css-tricks.com/wp-content/uploads/2018/11/00-basic-terminology.svg)

### Flexbox Properties

#### Properties for the Parent

| Properties       | complement        | Note                                                                                                |
| ---------------- | ----------------- | --------------------------------------------------------------------------------------------------- |
| display :        | flex              | it works in a block flexbox,                                                                        |
|                  | inline-flex       | it works in a inline flexbox                                                                        |
| flex-direction:  | row               | X direction                                                                                         |
|                  | row-reverse       |                                                                                                     |
|                  | column            | Y direction                                                                                         |
|                  | column-reverse    |                                                                                                     |
| flex-wrap :      | nowrap            | to nowrap children elements                                                                         |
|                  | wrap              | to wrap children elements                                                                           |
|                  | wrap-reverse      |                                                                                                     |
| **flex-flow:**   | **column nowrap** | It´s a shortcut from flex-direction and flex-wrap                                                   |
| justify-content: | flex-start        | it define the align from the chilfren elements regard to the main axis                              |
|                  | center            |                                                                                                     |
|                  | flex-end          |                                                                                                     |
|                  | space-between     |                                                                                                     |
|                  | space-around      |                                                                                                     |
|                  | space-evenly      |                                                                                                     |
| align-items:     | stretch           |                                                                                                     |
|                  | flex-start        |                                                                                                     |
|                  | flex-end          |                                                                                                     |
|                  | center            |                                                                                                     |
|                  | baseline          |                                                                                                     |
| align-content:   | flax-start        | This property only takes effect on multi-line flexible containers, with **:nowarp** It doesn´t work |
|                  | flex-end          |                                                                                                     |
|                  | center            |                                                                                                     |
|                  | stretch           |                                                                                                     |
|                  | space-between     |                                                                                                     |
|                  | space-around      |                                                                                                     |
|                  | space-evenly      |                                                                                                     |

#### Properties for the Children (flex items)

| Propertie    | Complement    | Note                                                                                                                        |
| ------------ | ------------- | --------------------------------------------------------------------------------------------------------------------------- |
| flex-grow:   | 0             | This defines the ability for a flex item **to grow if necessary**. It accepts a unitless value that serves as a proportion. |
| flex-shrink: | 1             | This defines the ability for a flex item **to shrink if necessary.**                                                        |
| flex-basis   | auto          | it depends from the direction if row represents the width, if column represents the height                                  |
| **flex**:    | **0 1 auto;** | It´s a shortcut from flex-grow, flex-shrink and flex-basis                                                                  |
| order:       | 0             | All the items are order 0 but they could be -1,1,2 etc.                                                                     |
| align-self   | stretch       | Overwrite the propertie valor **align-items** jus for the specific children                                                 |
|              | flex-start    |                                                                                                                             |
|              | flex-end      |                                                                                                                             |
|              | center        |                                                                                                                             |
|              | baseline      |                                                                                                                             |

---

## Grid CSS

- two-dimensional system
- It's a tool to layout content sections where there are components (Headers, Footers, SideBars, Galleries,etc.)

![layout](https://jonmircha.com/img/blog/grid-conceptos.png)

### 1. Explicit Grid

```css
.class {
  display: grid;
  /* Columns and rows */
  /* Grid 3cx3f */
  grid-template-columns: 50% 100px 1fr;
  grid-template-rows: 2rem 20vh 30%;
  /* Grid 5cx4f */
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(4, 1fr);
  /* Grid 4cx5f */
  grid-template-columns: 20% repeat(2, 30%) 20%;
  grid-template-rows: repeat(5, auto);

  /* Space between grid cells */
  /* gap: row column*/
  gap: 100px 0px;
}
```

#### 1.1 Grid lines

```css
.class .item:nth-child(10) {
  /* item position */
  /* Shortcut */
  grid-row: 2 / 3;
  grid-column: 3/5;
  /* item area/position */
  /* grid-area: grid-row-start/grid-column-start/grid-row-end/grid-column-end */
  grid-area: 2/3/3/5;
}

.class .item:nth-child(12) {
  /* Abarcar posiciones en la grid*/
  grid-row: span 2;
  grid-column: span 3;
}

.class .item:nth-child(15) {
  /* from line to grid cell */
  grid-row: 1 / span 2;
  grid-column: 1 / span 2;
}
```

#### 1.2 Grid Areas

![Grid areas](https://css-tricks.com/wp-content/uploads/2018/11/dddgrid-template-areas.svg)

```css
.grid-areas {
  display: grid;
  /* Grid 2cx3r */
  grid-template-columns: 1fr 200px;
  grid-template-rows: 100px repeat(2, 1fr) 60px;
  /* 
  Grid-tamplate-areas: it draws our layout
  Use . for draw a empty grid cell*/
  grid-template-areas:
    "header header"
    "content sidebar"
    "content ."
    "footer footer";
}

.header {
  grid-area: header;
}

.content {
  grid-area: content;
}

.sidebar {
  grid-area: sidebar;
}

.footer {
  grid-area: footer;
}
```

### 2. Implicit Grid

- Talks about all the spaces where there aren't rows defined and how the items are layouted.

![implicit grid](https://plectrolab.com/wp-content/uploads/2021/02/css-grid-layout-implicit-grid-1024x462.png)

### 3. Grid Flow

- Like in flexbox could be rows or column.

```css
.grid-flow {
  display: grid;
  /* grid 5cx3r */
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(3, 150px);
  grid-auto-flow: row; /* default:row */
  grid-auto-rows: 100px; /* auto */
  grid-auto-flow: column;
  grid-auto-columns: 100px; /* auto */
}
```

### 4. Grid flow Dense

- Taking advantage of the spaces.

- The grid flow dense property going to search spaces to fill them with the missing ones items.

```css
.grid-flow-dense {
  display: grid;
  /* Grid 5cX4r */
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(4, 200px);
  grid-auto-flow: row dense;
  grid-auto-flow: column dense;
}
```

### 5. Superposition

- We can use grid-row and grod-column to superput the items over other items.

![superposition](https://mastery.games/img/overlapping-grid-items.jpg)

### 6. Ordering

- Like flexbox

```css
.grid-order .item:nth-child(2) {
  order: 2; /* default: 0, positive and negative valors */
}
```

### 7. item align

1.  all the items

```css
.grid-align {
  display: grid;
  /* grid 3cx2r */
  grid-template-columns: repeat(3, 200px);
  grid-template-rows: repeat(2, 200px);
  justify-items: stretch; /* default: stretch */
  justify-items: center;
  align-items: stretch; /* default: stretch */
  align-items: center;
}
```

2. independent item align

```css
.grid-align .item:nth-child(2) {
  justify-self: start;
  align-self: start;
}
```

### 8. Track align

```css
.grid-align-tracks {
  /* alignment in the X axis */
  justify-content: center;
  /* alignment in the Y axis */
  align-content: center;
}
```

### 9. Max and min of the Grid tracks

- According to the content or pixels

```css
.grid-min-max {
  display: grid;
  /* 4cx?r */
  grid-template-columns: repeat(4, 1fr);
  grid-template-columns: repeat(4, minmax(100px, 200px));
  grid-template-columns: repeat(4, minmax(100px, max-content));
  grid-template-columns: repeat(4, minmax(max-content, 200px));
  grid-template-columns: repeat(4, minmax(min-content, max-content));
}
```

### 10. Repeating patterns

```css
.grid-repeat {
  display: grid;
  grid-template-columns: repeat(4, 10% 20% 30% 40%);
  grid-template-columns: repeat(2, 10% 20% 30% 40%);
  grid-template-columns: repeat(1, 10% 20% 30% 40%);
  grid-template-rows: repeat(2, 100px 200px);
  grid-auto-rows: 150px;
}
```

### 11. Dinamic Grids Responsive without media queries

```css
.grid-dynamics {
  display: grid;
  /* Grid de 4cx?r */
  grid-template-columns: repeat(4, 100px);
  /* Dinamic generator according to existent items*/
  grid-template-columns: repeat(auto-fill, 100px);
  grid-template-columns: repeat(auto-fit, 100px);
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
}

.grid-responsive {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  /* gap: 1vw 1vh; */
}
```

### 12. Nested grid & subgrids

1. Definir explícitamente el tamaño que ocupará el elemento que aplicará subgrid dentro del contenedor padre grid, es decir definir sus propiedades grid-column y grid-row.
2. Aplicar display grid al elemento que aplicará subgrid.
3. Aplicar el valor de subgrid a las columnas, a las filas o ambas depende de cómo se requiera

```css
.grid {
  display: grid;
  /* grid 3cx4r */
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(4, 1fr);
}

.subgrid {
  grid-column: span 3;
  grid-row: 1/3;
  display: grid;
  grid-template-columns: subgrid;
  grid-template-rows: subgrid;
}
```
