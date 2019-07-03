<h1 align="center">
  <a href="https://github.com/manjiz/react-native-swiper">
    @manjiz/react-native-swiper
  </a>
</h1>

<p align="center">
  <a href="https://github.com/Manjiz/react-native-swiper/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="React Native Swiper is released under the MIT license." />
  </a>
  <a href="https://www.npmjs.com/package/@manjiz/react-native-swiper">
    <img src="https://badge.fury.io/js/%40manjiz%2Freact-native-swiper.svg" alt="Current npm package version." />
  </a>
</p>

This swiper is modified based on [leecade/react-native-swiper](https://github.com/leecade/react-native-swiper). Not the best Swiper component for React Native.

- Fixed some remained bugs.
- Both iOS and android use ScrollView.
- Removed some inessentials.
- Used typescript.
- Be Tested in one online project (lack of test...need more...)
- Dependencies Versions:
  - react-native@^0.55.4
  - react@^16.3.1

## Example

- [Taro Components RN](https://github.com/NervJS/taro/blob/master/packages/taro-components-rn/src/components/Swiper/index.tsx)
  - 京東拼購 [iOS](https://apps.apple.com/us/app/%E4%BA%AC%E4%B8%9C%E6%8B%BC%E8%B4%AD-%E7%9C%81%E9%92%B1%E7%9C%81%E5%BF%83/id1453661340?from=groupmessage&isappinstalled=0) and android. The Swiper is locate in the index.

## Installation

```bash
npm i @manjiz/react-native-swiper --save
```

## Basic Usage

```jsx
import React, { Component } from 'react'
import {
  View,
  Text
} from 'react-native'
import Swiper from '@manjiz/react-native-swiper'

class Example extends Component {
  onIndexChanged = (index: number) => {
  }

  onMomentumScrollEnd = (e, state) => {
  }

  render () {
    const slideStyle = { flex: 1, justifyContent: 'center', alignItems: 'center' }

    return (
      <Swiper
        autoplay={true}
        autoplayTimeout={6}
      >
        <View style={[slideStyle, { backgroundColor: 'red' }]}>
          <Text>Red</Text>
        </View>
        <View style={[slideStyle, { backgroundColor: 'green' }]}>
          <Text>Green</Text>
        </View>
        <View style={[slideStyle, { backgroundColor: 'blue' }]}>
          <Text>Blue</Text>
        </View>
      </Swiper>
    )
  }
}

export default Example
```

## Properties

### Basic

| Prop              | Type    | Default | Description |
| ----------------- | ------- | ------- | ----------- |
| horizontal        | boolean | true    | If true, the scroll view's children are arranged horizontally in a row instead of vertically in a column |
| loop              | boolean | true    | Set to false to disable continuous loop mode |
| autoplay          | boolean | false   | Set to true enable auto play mode |
| index             | number  | 0       | Index number of initial slide. And real index would be sync as it changed |
| loadMinimal       | boolean | false   | Only load current index slide , loadMinimalSize slides before and after |
| loadMinimalSize   | number  | 1       | see loadMinimal |
| showsPagination   | boolean | true    | Set to false make pagination invisible. |
| autoplayTimeout   | number  | 2.5     | Delay between auto play transitions (in second) |
| autoplayDirection | boolean | true    | Cycle direction control |


### Element

| Prop              | Type    | Default | Description |
| ----------------- | ------- | ------- | ----------- |
| loadMinimalLoader | Element | <ActivityIndicator /> | Custom loader to display when slides aren't loaded |
| dot               | Element | <View ... /> | Allow custom the dot element |
| activeDot         | Element | <View ... /> | Allow custom the active-dot element |
| renderPagination  | (index: number, total: number, swiper: any) => JSX.Element | see source code |

### Styleus

| Prop              | Type      | Default | Description |
| ----------------- | --------- | ------- | ----------- |
| width             | number    | -       | If no specify default enable fullscreen mode by flex: 1 |
| height            | number    | -       | If no specify default fullscreen mode by flex: 1 |
| dotColor          | string    | -       | Allow custom the dot element |
| activeDotColor    | string    | -       | Allow custom the active-dot element |
| containerStyle    | ViewStyle | -       | See default container style in source |
| scrollViewStyle   | ViewStyle | -       | Style set to ScrollView |
| style             | ViewStyle | -       | Style set to ScrollView contentContainerStyle |
| paginationStyle   | ViewStyle | -       | pagination wrapper style |
| dotStyle          | ViewStyle | -       | Allow custom the dot element |
| activeDotStyle    | ViewStyle | -       | Allow custom the active-dot element |

### Native ScrollView Props

No need to change them.

### Event

| Prop           | Type | Description | 
| -------------- | ---- | ----------- |
| onIndexChanged | index | Called with the new index when the user swiped |

**Supported ScrollResponder**

| Prop           | Type | Description | 
| -------------- | ---- | ----------- |
| onScrollBeginDrag | e / state / context | When animation begins after letting up |
| onMomentumScrollEnd | e / state / context | Makes no sense why this occurs first during bounce |
| onTouchStartCapture | e / state / context | Immediately after onMomentumScrollEnd |
| onTouchStart | e / state / context | Same, but bubble phase |
| onTouchEnd | e / state / context | You could hold the touch start for a long time |
| onResponderRelease | e / state / context | You could hold the touch start for a long time |

> Note: each ScrollResponder be injected with two params: state and context, you can get state and context(ref to swiper's this) from params.

## Methods

### scrollBy

Scroll by relative index.

Parameters:

| Name | Type | default | Description |
| ---- | ---- | ------- | ----------- |
| index | number | undefined | offset index |
| animated | bool | true | offset index |

## Contribution

### Local Development

```bash
rsync -avr ~/react-native-swiper/dist ~/MyApp/node_modules/@manjiz/react-native-swiper
```
