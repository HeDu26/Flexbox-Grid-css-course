# Learning Flexbox CSS

- Basics and terminology

![Basics and terminology](https://css-tricks.com/wp-content/uploads/2018/11/00-basic-terminology.svg)

## Flexbox Properties

### Properties for the Parent

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

### Properties for the Children (flex items)

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
