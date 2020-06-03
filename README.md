# Sheet Modal

A simple and super lightweight React component to display customizable action sheets and modals with few lines of code.

## Getting started

### Installing

```bash
$ npm i sheet-modal --save
```

or

```bash
$ yarn add sheet-modal
```

### Exports

The default export is `<SheetModal />` component. Also need the `useToggle()` hook to work.

```js
import SheetModal, { useToggle } from 'sheet-modal'
```

### Quick Example

```js
import React from 'react'
import SheetModal, { useToggle } from 'sheet-modal'

export default function Home() {
    const [isShowing, toggle] = useToggle()

    return (
        <>
            <header>My web page with action modals!</header>

            <SheetModal
                position="bottom"
                title="Hello, World!"
                body={(<p>Lorem Ipsum</p>)}
                isShowing={isShowing}
                toggle={toggle}
            />
        </>
    ) // return
} // Home
```

## `useToggle()` hook

The `useToggle()` hook returns an `array` with `isShowing` state and the `toggle()` function used to change `isShowing` value.

```js
const [isShowing, toggle] = useToggle()
```

### `isShowing` state

`isShowing ` is required as a prop in `<SheetModal />` component and can be used to know the action sheet actual state.

```js
<SheetModal
    ...
    isShowing={isShowing}
    ...
/>
```

```js
isShowing ? 'The action sheet is showing.' : 'The action sheet is not showing.'
```

## `toggle()` function

The `toggle()` function is used to switch `isShowing` value to `true` or `false` when called.

```jsx
<button onClick={toggle}>Toggle modal</button>
```

## Props

|Property|Type|Default|Options|Description|
|--------|----|-------|-------|-----------|
|`position`|`String`|`'center'`|`center`, `top`, `bottom`, `left`, `right`|Defines the positioning on the screen.|
|`title`|`string`|`''`||String to display the action sheet title on the header.|
|`body`|`ReactNode`|||React object to display on the body of the action sheet.|
|`footer`|`ReactNode`|`<></>`||React object to display on the footer of the action sheet.|
|`isClosablle`|`bool`|`true`|`true`, `false`|Define if the user can close the actions sheet with de default close button or clicking out. Calling `toggle()` function is the only way to close the action sheet.|
|`isShowing`|`bool`||`true`, `false`|Define the action sheet visibility. Only can be changed using the `toggle()` function. |
|`toggle`|`function`|||Required function to change the action sheet visibility.|

## :memo: License

This project is under MIT license. See [LICENSE](LINCENSE) for more details.

Made with ❤️ by **GustavoEklund**
