# @mmcxii/vs-code-snippets

## Description

A collection of snippets to assist with development.

## Examples

### React Component

```tsx
import * as React from "react";

export type MyComponentProps = {
  firstName: null | string;
};

export const MyComponent: React.FC<MyComponentProps> = (props) => {
  const { firstName } = props;

  //* State
  const [myState, setMyState] = React.useState();

  //* Refs
  const myRef = React.useRef();

  //* Variables
  const myVariable = "MY_VARIABLE";

  //* Handlers
  const myFunction = () => {};

  if (firstName == null) {
    return null;
  }

  return <div>{firstName}</div>;
};
```

### React Component Container

```tsx
import * as React from "react";
import { MyComponent, type MyComponentProps } from "./component";
import { MyStore } from "../../stores";

export type MyComponentContainerProps = Omit<MyComponentProps, "firstName">;

export const MyComponentContainer: React.FC<MyComponentContainerProps> = (
  props
) => {
  //* Stores
  const myStore = React.useContext(MyStore.Context);

  //* Variables
  const { firstName } = myStore.data;

  return <MyComponent {...props} firstName={firstName} />;
};
```
