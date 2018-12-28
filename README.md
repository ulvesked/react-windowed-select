# react-windowed-select

[![Travis][build-badge]][build]
[![npm package][npm-badge]][npm]
[![Coveralls][coveralls-badge]][coveralls]

An integration of `react-window` with `react-select` v2 to efficiently render large lists.

## Installation and Usage

The easiest way to use `react-windowed-select` is to install it from npm:
```
npm install react-windowed-select
```

Then use it in your app:

```javascript
import React from "react";
import WindowedSelect from "react-windowed-select";

const options = [];

for (let i = 0; i < 10000; i += 1) {
  options.push({
    label: `Option ${i}`,
    value: i
  });
}

class App extends React.Component {
  render() {
    return <WindowedSelect options={options} />;
  }
}
```
[![Edit react-windowed-select](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/n592j4l13m)


## Props
`react-windowed-select` is just a wrapper around `react-select`. All props passed to the `WindowedSelect` component are passed down to the underlying `Select` component from `react-select`.

See [react-select.com](https://www.react-select.com) for live demos and comprehensive docs on how to use this component.

## Additional Props

### windowThreshold | default = 100

The number of options beyond which the menu will be windowed.

## Known Limitations
In order to support proper scrolling and focus behavior, grouped options are flattened. This changes the component hierarchy within `MenuList` in the following way:

```
MenuList  
│
└───Group
│   │
|   └───GroupHeading
|
└───Option 1
|
└───Option 2
```

[build-badge]: https://img.shields.io/travis/user/repo/master.png?style=flat-square
[build]: https://travis-ci.org/user/repo

[npm-badge]: https://img.shields.io/npm/v/react-windowed-select.png?style=flat-square
[npm]: https://www.npmjs.com/package/react-windowed-select

[coveralls-badge]: https://img.shields.io/coveralls/user/repo/master.png?style=flat-square
[coveralls]: https://coveralls.io/github/user/repo
