---
title: Skeleton Elements for Svelte - UI for improved perceived performance
description: Svelte UI library for perceived performance
---

# Skeleton Elements for Svelte

- [Installation](#installation)
- [Styles](#styles)
  - [CSS](#css)
  - [SCSS](#scss)
  - [CSS Custom Properties (Variables)](#css-custom-properties-variables)
- [Components](#components)
  - [SkeletonBlock](#skeletonblock)
  - [SkeletonText](#skeletontext)
  - [SkeletonAvatar](#skeletonavatar)
  - [SkeletonImage](#skeletonimage)
- [Loading Effects](#loading-effects)

<iframe src="https://codesandbox.io/embed/skeleton-elements-svelte-qesvj?autoresize=1&fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" title="skeleton-elements-svelte" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-autoplay allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

## Installation

You can install Skeleton Elements for Svelte via npm:

```
npm i @skeleton-elements/svelte --save
```

## Styles

### CSS

Skeleton Elements requires stylesheet to be included:

```html
<link rel="stylesheet" href="path/to/skeleton-elements.css" />
```

Wiht bundler (like webpack) you can import styles directly from JavaScript:

```js
import '@skeleton-elements/svelte/skeleton-elements.css';
```

Or it can be included for each component separately:

- `@skeleton-elements/svelte/skeleton-avatar.css` - Avatar component
- `@skeleton-elements/svelte/skeleton-block.css` - Block component
- `@skeleton-elements/svelte/skeleton-image.css` - Image component
- `@skeleton-elements/svelte/skeleton-text.css` - Text component
- `@skeleton-elements/svelte/skeleton-effects.css` - Effects

### SCSS

`SCSS` styles are also included:

- `@skeleton-elements/svelte/skeleton-elements.scss` - All styles
- `@skeleton-elements/svelte/skeleton-avatar.scss` - Avatar component
- `@skeleton-elements/svelte/skeleton-block.scss` - Block component
- `@skeleton-elements/svelte/skeleton-image.scss` - Image component
- `@skeleton-elements/svelte/skeleton-text.scss` - Text component
- `@skeleton-elements/svelte/skeleton-effects.scss` - Effects

### CSS Custom Properties (Variables)

There are following CSS Variables available:

- `--skeleton-color` (default `#ccc`) - used as text color for skeleton text, and background color of skeleton block, avatar and image
- `--skeleton-icon-color` (default `rgba(0, 0, 0, 0.25)`) - used as icon color in skeleton avatar and image

## Components

There are following components available:

- `SkeletonBlock` - block placeholder
- `SkeletonText` - skeleton text (uses custom Skeleton font)
- `SkeletonAvatar` - responsive avatar placeholder
- `SkeletonImage` - responsive image placeholder

### SkeletonBlock

Skeleton block is just a usual block element with gray background color, that can be in any required size.

<iframe src="https://codesandbox.io/embed/skeleton-block-svelte-xx5p7?autoresize=1&fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:300px; border:0; border-radius: 4px; overflow:hidden;" title="skeleton-block-svelte" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-autoplay allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

#### SkeletonBlock Props

| Name     | Type     | Default | Description                                                           |
| -------- | -------- | ------- | --------------------------------------------------------------------- |
| `tag`    | `string` | `'div'` | HTML element tag, can be `div`, `p`, `h1`, `h2`, `h3`, `h4` or `span` |
| `width`  | `number` |         | Block CSS width                                                       |
| `height` | `number` |         | Block CSS height                                                      |
| `effect` | `string` |         | Loading effect, can be `fade` or `pulse` or `blink`                   |

### SkeletonText

Skeleton text uses custom Skeleton font for making responsive text placeholders.

Special Skeleton font renders every character as small gray rectangle. When we wrap text with `SkeletonText` component, it converts text to gray blocks/lines. Advantage over `SkeletonBlock` is that such "skeleton text" can be fully responsive and its size will reflect actual text size.

Skeleton text font supports following characters set (including "space"):

```
0 1 2 3 4 5 6 7 8 9 a b c d e f g h i j k l m n o p q r s t u v w z x y z A B C D E F G H I J K L M N O P Q R S T U V W Z X Y Z _ -   . , : ; / ! / * & ' " | ( ) { } [ ]
```

<iframe src="https://codesandbox.io/embed/skeleton-text-svelte-wetrw?autoresize=1&fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:300px; border:0; border-radius: 4px; overflow:hidden;" title="skeleton-text-svelte" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-autoplay allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

#### SkeletonText Props

| Name     | Type     | Default  | Description                                                           |
| -------- | -------- | -------- | --------------------------------------------------------------------- |
| `tag`    | `string` | `'span'` | HTML element tag, can be `div`, `p`, `h1`, `h2`, `h3`, `h4` or `span` |
| `effect` | `string` |          | Loading effect, can be `fade` or `pulse` or `blink`                   |

### SkeletonAvatar

Skeleton Avatar is designed to be used as a placeholder for avatars. It dynamically renders SVG image with "person" icon inside:

<iframe src="https://codesandbox.io/embed/skeleton-avatar-svelte-fukgi?autoresize=1&fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:300px; border:0; border-radius: 4px; overflow:hidden;" title="skeleton-avatar-svelte" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-autoplay allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

#### SkeletonAvatar Props

| Name           | Type      | Default | Description                                    |
| -------------- | --------- | ------- | ---------------------------------------------- |
| `size`         | `number`  | `48`    | Generated SVG size in px.                      |
| `color`        | `string`  |         | CSS color, e.g. `#f00`, `rgba(255, 255, 0)`    |
| `showIcon`     | `boolean` | `true`  | Defines wether to show icon or not             |
| `iconColor`    | `string`  |         | Icon CSS color                                 |
| `borderRadius` | `string`  | `50%`   | Avatar CSS border radius                       |
| `effect`       | `string`  |         | Loading effect, can be`fade`or`pulse`or`blink` |

### SkeletonImage

Skeleton Image is designed to be used as a placeholder for images. It dynamically renders rectangle SVG image with "image" icon inside:

<iframe src="https://codesandbox.io/embed/skeleton-image-svelte-e5srk?autoresize=1&fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:300px; border:0; border-radius: 4px; overflow:hidden;" title="skeleton-image-svelte" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-autoplay allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

#### SkeletonImage Props

| Name        | Type      | Default | Description                                         |
| ----------- | --------- | ------- | --------------------------------------------------- |
| `width`     | `number`  | `1200`  | SVG image width in px                               |
| `height`    | `number`  | `600`   | SVG image height in px                              |
| `color`     | `string`  |         | CSS color, e.g. `#f00`, `rgba(255, 255, 0)`         |
| `showIcon`  | `boolean` | `true`  | Defines wether to show icon or not                  |
| `iconColor` | `string`  |         | Icon CSS color                                      |
| `effect`    | `string`  |         | Loading effect, can be `fade` or `pulse` or `blink` |

## Loading Effects

There are following loading effects available:

- `pulse`
- `fade`
- `blink`

To add loading effect in Skeleton components, pass effect name in `effect` prop.
For anything else, just add `skeleton-effect-${effectName}` class to elements.

```svelte
<!-- skeleton block with "pulse" loading effect -->
<SkeletonBlock effect="pulse" />

<!-- skeleton text with "fade" loading effect -->
<SkeletonText effect="fade">...</SkeletonText>

<!-- custom block with "blink" loading effect -->
<div class="skeleton-effect-blink">
  <SkeletonText tag="h1">...</SkeletonText>
  <SkeletonText tag="h2">...</SkeletonText>
  <SkeletonText tag="p">...</SkeletonText>
  <SkeletonText tag="p">...</SkeletonText>
  <SkeletonBlock>...</SkeletonBlock>
</div>
```
