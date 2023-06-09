---
Type: framework
Language: ☕ javaScrpit
---

# React Native
deadline: besok

---
common library
1.  `react-native-app-intro-slider`
2.  `@react-navigation/native`
## 🐤 Navigation
📃 pagination routing
```ts
const App = () => {
  return (
    <NavigationContainer initialRouteName="login">
      <Stack.Navigator screenOptions={{ headerShown: false }}>
        <Stack.Screen name="Onboarding" component={Onboarding} />
        <Stack.Screen name="Product" component={Product} />
        <Stack.Screen name="Dashboard" component={Dashboard} />
      </Stack.Navigator>
    </NavigationContainer>
  );
};
```
📃 Page biasa
```js
const Order = ({ navigation }) => {
  return (
		<View>
			...
		</View>
		)
```
📃 data binding
```js
<TouchableOpacity onPress={() => navigation.navigate('Product', {
          data:
          {
            nama: 'peternakan ikan',
            harga: 1500
          }
        })}>
```
📃 Buttonnya
```js
const Product = ({ navigation, route }) => {
  const { data } = route.params;

  return (<View>

		<Text>{data.nama}</Text>
		<Text>{data.harga}</Text>
			...
		</View>
		)
```