<h1 align="left">hrnet-modal</h1>
<p>
  <a href="https://www.npmjs.com/package/@daphaz/hrnet-modal" target="_blank">
  <img alt="Version" src="https://badge.fury.io/js/@daphaz%2Fhrnet-modal.svg" />
  </a>
</p>

## Note

> This is a reference of one of the components library in [this project]("https://github.com/Daphaz/DamienBonnet_14_ui_03072022")

## Table of Contents

- [Installation](#installation)
- [API documentation](#API-documentation)

## Installation

For this project we use Nodejs `14.17.3`, we recommand to use a nodejs version manager like _nvm_ and launch `nvm use` command to get the right Nodejs version.

To install, you can use [npm]("https://www.npmjs.com/") or [yarn]("https://yarnpkg.com/"):

```sh
$ npm install --save @daphaz/hrnet-modal
$ yarn add @daphaz/hrnet-modal
```

## API documentation

> Displays a dialog with a custom content that requires attention or provides additional information.

### Default

Use `open` prop to control modal displayed

| Name             |  Description   | Default |
| ---------------- | :------------: | ------: |
| **open**         |   `boolean`    |       - |
| **preventClose** |   `boolean`    | `false` |
| **closeButton**  |   `boolean`    | `false` |
| **onOpen**       | `(() => void)` |       - |
| **onClose**      | `(() => void)` |       - |
| **className**    |    `string`    |    `""` |

### Prevent Close

With `preventClose` props you can't close the Modal by clicking on Backdrop

### Modal Components

Use can use three components already styled:

- Modal.Header
- Modal.Body
- Modal.Footer

```tsx
<Modal>
  <Modal.Header>my Header</Modal.Header>
  <Modal.Body>my Body</Modal.Body>
  <Modal.Footer>my Footer</Modal.Footer>
</Modal>
```

### Extras

Use can use a `useModal` hooks for provide already all state as you needed for modal controls

```ts
type useModal = (initialVisible: boolean) => {
  visible: boolean;
  setVisible: Dispatch<SetStateAction<boolean>>;
  currentRef: MutableRefObject<boolean>;
  controls: {
    open: boolean;
    onClose: () => void;
  };
};
```

And also if you need to close the Modal in other place use the context

```tsx
import { useModalContext, Modal } from '@daphaz/hrnet-modal';

const App = () => {
  const { close } = useModalContext();

  return <button onClick={close}>close modal</button>;
};
```
