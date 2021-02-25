---
id: input
title: Input
---

The `Input` component is a component that is used to get user input in a text field.

## Implements

- `TextInput` from [react-native](https://reactnative.dev/docs/textinput)
- `Box` from native-base.

## Import

```jsx
import {
	Input,
	InputGroup,
	InputLeftAddon,
	InputRightAddon,
} from 'native-base';
```

## Usage

```SnackPlayer name=Input%20Usage
import React from 'react';
import { Input, NativeBaseProvider } from 'native-base';

function InputComponent () {
  return <Input p={3} w="90%" placeholder="Default Input Box" />;
};
export default function () {
  return (
    <NativeBaseProvider>
      <InputComponent />
    </NativeBaseProvider>
  );
}
```

## Input Sizes

```SnackPlayer name=Image%20Example(Sizes)
import React from 'react';
import { Input, NativeBaseProvider,Stack,Center,Heading } from 'native-base';

function InputComponent () {
  return (
    <Stack alignItems="center" space={4}>
      <Center>
        <Heading>Size Input</Heading>
      </Center>
      <Input w="90%" size="xs" placeholder="xs Input" />
      <Input w="90%" size="sm" placeholder="sm Input" />
      <Input w="90%" size="md" placeholder="md Input" />
      <Input w="90%" size="lg" placeholder="lg Input" />
      <Input w="90%" size="xl" placeholder="xl Input" />
      <Input w="90%" size="2xl" placeholder="2xl Input" />
    </Stack>
  );
};
export default function () {
  return (
    <NativeBaseProvider>
      <InputComponent />
    </NativeBaseProvider>
  );
}
```

## Input Variants

```SnackPlayer name=Image%20Example(Variants)
import React from 'react';
import { Input, NativeBaseProvider,Stack,Center,Heading } from 'native-base';

function InputComponent () {
  return (
    <Stack space={4}>
      <Center>
        <Heading>Input Variants</Heading>
      </Center>
      <Input variant="outline" placeholder="Outline" />
      <Input variant="filled" placeholder="Filled" />
      <Input variant="underlined" placeholder="Underlined" />
      <Input variant="unstyled" placeholder="Unstyled" />
      <Input variant="rounded" placeholder="round" />
    </Stack>
  );
};
export default function () {
  return (
    <NativeBaseProvider>
      <InputComponent />
    </NativeBaseProvider>
  );
}
```

## Input Addons

```SnackPlayer name=Image%20Example(Addons)
import React from 'react';
import { Input, InputGroup, InputLeftAddon, InputRightAddon, NativeBaseProvider,Stack,Text } from 'native-base';

function InputComponent () {
  return (
    <Stack space={4}>
      <InputGroup>
        <InputLeftAddon children={<Text>https://</Text>} />
        <Input w="70%" placeholder="nativebase" />
        <InputRightAddon children={<Text>.io</Text>} />
      </InputGroup>
    </Stack>
  );
};
export default function () {
  return (
    <NativeBaseProvider>
      <InputComponent />
    </NativeBaseProvider>
  );
}
```

## Input Elements

```SnackPlayer name=Image%20Example(Input Elements)
import React from 'react';
import { Input, NativeBaseProvider,Icon } from 'native-base';

function InputComponent () {
  return (
    <Input
      w="90%"
      InputLeftElement={
        <Icon name="phone" fontSize="xl" type="MaterialIcons" />
      }
      InputRightElement={
        <Icon name="person" fontSize="xl" type="MaterialIcons" />
      }
      placeholder="Left and Right InputElement"
    />
  );
};
export default function () {
  return (
    <NativeBaseProvider>
      <InputComponent />
    </NativeBaseProvider>
  );
}
```

## Password Input

```SnackPlayer name=Image%20Example(Password Input)
import React from 'react';
import { Input, NativeBaseProvider,Button } from 'native-base';

function InputComponent () {
  const [show, setShow] = React.useState(false);
  const handleClick = () => setShow(!show);
  return (
    <Input
      w="70%"
      type={show ? 'text' : 'password'}
      InputRightElement={
        <Button ml={1} onPress={handleClick}>
          {show ? 'Hide' : 'Show'}
        </Button>
      }
      placeholder="Password"
    />
  );
};
export default function () {
  return (
    <NativeBaseProvider>
      <InputComponent />
    </NativeBaseProvider>
  );
}
```

## Controlled Input

```SnackPlayer name=Image%20Example(Controlled Input)
import React from 'react';
import { Input, NativeBaseProvider } from 'native-base';

function InputComponent () {
  const [value, setValue] = React.useState('');
  const handleChange = (event: any) => setValue(event.target.value);
  return (
    <Input
      value={value}
      onChange={handleChange}
      placeholder="Value Controlled Input"
    />
  );
};
export default function () {
  return (
    <NativeBaseProvider>
      <InputComponent />
    </NativeBaseProvider>
  );
}
```

## Input Focused and Error Border Colors

```SnackPlayer name=Image%20Example(Input Focused and Error Border Colors)
import React from 'react';
import { Input, NativeBaseProvider,Stack } from 'native-base';

function InputComponent () {
  return (
    <Stack space={4}>
      <Input
        placeholder="Here is a sample placeholder"
        focusBorderColor="green"
      />
      <Input
        placeholder="Here is a sample placeholder"
        focusBorderColor="pink"
      />
      <Input placeholder="Here is a sample placeholder" isInvalid />
      <Input
        placeholder="Here is a sample placeholder"
        isInvalid
        errorBorderColor="yellow"
        errorMessage="This is an Error Message"
      />
    </Stack>
  );
};
export default function () {
  return (
    <NativeBaseProvider>
      <InputComponent />
    </NativeBaseProvider>
  );
}
```

## Props

### Input

| Name              | Type                                           | Description                                                                                          | Default |
| ----------------- | ---------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ------- |
| variant           | filled, outline, rounded, underlined, unstyled | The variant of the input style to use.                                                               | outline |
| isDisabled        | boolean                                        | If true, the input will be disabled.                                                                 | -       |
| isInvalid         | boolean                                        | If true, the input will indicate an error.                                                           | -       |
| isReadOnly        | boolean                                        | If true, prevents the value of the input from being edited.                                          | -       |
| size              | 2xl, lg, md, sm, xl, xs                        | The size of the button.                                                                              | md      |
| onChange          | function                                       | Callback for on change on input value.                                                               | -       |
| placeholder       | string                                         | The placeholder attribute specifies a short hint that describes the expected value of an input field | -       |
| errorMessage      | string                                         | error message to be shown when input is invalid.                                                     | -       |
| isFullWidth       | boolean                                        | If true, the input element will span the full width of its parent                                    | -       |
| focusBorderColor  | string                                         | The border color when the input is focused.                                                          | -       |
| errorBorderColor  | string                                         | The border color when isInvalid is set to true.                                                      | -       |
| errorMessageColor | string                                         | The font color of error message.                                                                     | -       |
| ariaLabel         | string                                         | An accessible label for the input.                                                                   | -       |
| InputLeftElement  | JSX.Element                                    | If given, adds the provided element to the left of the input.                                        | -       |
| InputRightElement | JSX.Element                                    | If given, adds the provided element to the right of the input.                                       | -       |
| type              | password, string, text                         | Using the type 'password', user can mask the input.                                                  | -       |
| label             | string                                         | If given, adds a floating label to the input.                                                        | -       |