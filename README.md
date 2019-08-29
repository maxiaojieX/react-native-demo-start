# react-native-demo-start
RN 搭建入门级Demo

#### 步骤一：https://reactnative.cn/docs/getting-started/ 创建空白项目,安装。
```
yarn install
```

#### 步骤二：安装路由依赖

```
1、yarn add react-navigation    or  npm install --save react-navigation
2、yarn add react-native-gesture-handler    or  npm install --save react-native-gesture-handler
```

#### 步骤三：App.js demo配置

```
import React from 'react';
import { View, Text, Button } from 'react-native';
import { createAppContainer, createStackNavigator, StackActions, NavigationActions } from 'react-navigation'; // Version can be specified in package.json

class HomeScreen extends React.Component {
  render() {
    return (
      <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
        <Text>Hello word</Text>
        <Button
          title="next"
          onPress={() => {
            this.props.navigation.dispatch(StackActions.reset({
              index: 0,
              actions: [
                NavigationActions.navigate({ routeName: 'Details' })
              ],
            }))
          }}
        />
      </View>
    );
  }  
}

class DetailsScreen extends React.Component {
  render() {
    return (
      <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
        <Text>Details Screen</Text>
      </View>
    );
  }  
}

const AppNavigator = createStackNavigator({
  Home: {
    screen: HomeScreen,
  },
  Details: {
    screen: DetailsScreen,
  },
}, {
    initialRouteName: 'Home',
});

export default createAppContainer(AppNavigator);
```

#### 步骤四：启动在安卓上。
```
react-native run-android
```