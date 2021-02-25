---
id: select
title: Select
---

Creates a dropdown list of items with the selected item in closed view.

## Implements

- `Button` from native-base.

## Import

```jsx
import { Select } from 'native-base';
```

## Example

```SnackPlayer name=Select%20Example
import React from 'react';
import { Icon, Select, NativeBaseProvider } from 'native-base';

function SelectComponent () {
  let [language, setLanguage] = React.useState('');
  return (
    <Select
      placeholder="Pick language"
      _placeholder={{ color: 'teal.500' }}
      selectedValue={language}
      width={150}
      onValueChange={(itemValue: string) => setLanguage(itemValue)}
      selectedItemBg={'blue.500'}
      _selectedItem={{ color: 'white' }}
      dropdownOpenIcon={
        <Icon name="arrow-drop-up" type="MaterialIcons" size={6} />
      }
      dropdownCloseIcon={
        <Icon name="arrow-drop-down" type="MaterialIcons" size={6} />
      }
      _item={{ color: 'red.500' }}
    >
      <Select.Item label="JavaScript" value="js" />
      <Select.Item label="TypeScript" value="ts" />
      <Select.Item label="Java" value="java" />
    </Select>
  );
}
export default function () {
  return (
    <NativeBaseProvider>
      <SelectComponent />
    </NativeBaseProvider>
  );
}
```

## Props

### Select

| Name              | Type        | Description                                                                                           | Default  |
| ----------------- | ----------- | ----------------------------------------------------------------------------------------------------- | -------- |
| placeholder       | string      | The placeholder attribute specifies a short hint that describes the expected value of an select field | -        |
| \_placeholder     | TextProps   | Text props to be applied to placeholder                                                               | -        |
| selectedValue     | string      | The default value which is selected                                                                   | -        |
| onValueChange     | function    | Callback for on change on input value.                                                                | -        |
| itemStyle         | stylesheet  |                                                                                                       | -        |
| selectedItemBg    | string      | Background color for selected item                                                                    | blue.500 |
| \_selectedItem    | TextProps   | Text props to be applied to the selected item                                                         | white    |
| isDisabled        | boolean     | If true, the button will be disabled.                                                                 | -        |
| dropdownIcon      | JSX.Element | If given, updates the dropdown Icon.                                                                  | -        |
| dropdownOpenIcon  | JSX.Element | If given, updates the dropdown Icon, when opened.                                                     | -        |
| dropdownCloseIcon | JSX.Element | If given, updates the dropdown Icon, when closed.                                                     | -        |

### Select Item

| Name       | Type      | Description                                                                                    | Default |
| ---------- | --------- | ---------------------------------------------------------------------------------------------- | ------- |
| label      | string    | The label which will be displayed.                                                             | -       |
| value      | string    | The value to be used for the item. This is the value that will be returned on form submission. | -       |
| isDisabled | boolean   | If true, the item will be disabled.                                                            | -       |
| \_label    | TextProps | TextProps to be applied to label                                                               | -       |