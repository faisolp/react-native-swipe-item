# React Native Swipe Item

A swipe item for react-native. Supports both iOS and Android.

<img src="/ios-demo.gif" width="310">&nbsp;&nbsp;<img src="/android-demo.gif" width="310">

## Installation

```sh

npm i --save react-native-swipe-item

```

## Usage

You can use the `SwipeButtonsContainer` to wrap buttons that you want to show when user swipe the item, and pass it to props.

```javascript
import { SwipeItem, SwipeButtonsContainer } from 'react-native-swipe-item';

export default function SwipeButtonCustom() {

    const leftButton = (
        <SwipeButtonsContainer
            style={{
                alignSelf: 'center',
                aspectRatio: 1,
                flexDirection: 'column',
                padding: 10,
            }}
            
        >
            <TouchableOpacity
                onPress={() => console.log('left button clicked')}
            >
                <Text>Click me !</Text>
            </TouchableOpacity>
        </SwipeButtonsContainer>
    );
  
    return (
        <SwipeItem
            style={styles.button}
            swipeContainerStyle={styles.swipeContentContainerStyle}
            leftButtons={leftButton}
        >
            <Text>
                Swipe me!
            </Text>
        </SwipeItem>
    );
}

const styles = StyleSheet.create({
    button: {
        width: '80%',
        height: 100,
        alignSelf: 'center',
        marginVertical: 5,
    },
    swipeContentContainerStyle: {
        justifyContent: 'center',
        alignItems: 'center',
        backgroundColor: '#ffffff',
        borderRadius: 10,
        borderColor: '#e3e3e3',
        borderWidth: 1,
    }
});

```

### `SwipeItem` Props

* [style](#style)

* [swipeContainerStyle](#swipeContainerStyle)

* [leftButtons](#leftButtons)

* [rightButtons](#rightButtons)

* [containerView](#containerView)

<a id="style">**`style`**</a>

These styles will be applied to the swipe item layout.

| TYPE | REQUIRED |
| --- | --- |
| style | No |

---

<a id="swipeContainerStyle">**`swipeContainerStyle`**</a>

These styles will be applied to the swipe item container which user swipe.

Example:

```js
return (
        <SwipeItem swipeContainerStyle={styles.swipeContentContainerStyle} >
        </SwipeItem>
    );
}

const styles = StyleSheet.create({
    swipeContentContainerStyle: {
        justifyContent: 'center',
        alignItems: 'center',
        backgroundColor: '#ffffff',
        borderRadius: 10,
        borderColor: '#e3e3e3',
        borderWidth: 1,
    }
});
```

| TYPE | REQUIRED |
| --- | --- |
| style | No |

---

<a id="leftButtons">**`leftButtons`**</a>

Buttons that want to show on the left when the item swipe to right.

| TYPE | REQUIRED |
| --- | --- |
| `SwipeButtonsContainer` | No |

---

<a id="rightButtons">**`rightButtons`**</a>

Buttons that want to show on the right when the item swipe to left.

| TYPE | REQUIRED |
| --- | --- |
| `SwipeButtonsContainer` | No |

---

<a id="containerView">**`containerView`**</a>

The component for the swipe item.

*   *Before RN 0.57.0 the child view would be clipped by parent view when the child view layout out of the parent. Recommend to use [ViewOverflow](https://github.com/entria/react-native-view-overflow) plugin to solve this problem.*

Example:

```js
import ViewOverflow from 'react-native-view-overflow';
...
...
export default function SwipeButtonCustom() {  
    return (
        <SwipeItem
            style={styles.button}
            swipeContainerStyle={styles.swipeContentContainerStyle}
            containerView={ViewOverflow}
        >
            <Text>
                Swipe me!
            </Text>
        </SwipeItem>
    );
}
...
```

| TYPE | REQUIRED | PLATFORM |
| --- | --- | --- |
| `ViewOverflow` | Yes | Android |



## License

MIT