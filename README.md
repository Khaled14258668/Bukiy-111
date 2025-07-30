# Bukiy-111
// Bukiy 111 App Entry (App.js) import React from 'react'; import { NavigationContainer } from '@react-navigation/native'; import { createNativeStackNavigator } from '@react-navigation/native-stack'; import LoginScreen from './screens/LoginScreen'; import HomeScreen from './screens/HomeScreen'; import ResultHistory from './screens/ResultHistory'; import UploadResult from './screens/UploadResult';

const Stack = createNativeStackNavigator();

export default function App() { return ( <NavigationContainer> <Stack.Navigator initialRouteName="Login"> <Stack.Screen name="Login" component={LoginScreen} /> <Stack.Screen name="Home" component={HomeScreen} /> <Stack.Screen name="History" component={ResultHistory} /> <Stack.Screen name="UploadResult" component={UploadResult} /> </Stack.Navigator> </NavigationContainer> ); }

// --- screens/LoginScreen.js --- import React, { useState } from 'react'; import { View, Text, TextInput, Button, StyleSheet } from 'react-native';

export default function LoginScreen({ navigation }) { const [username, setUsername] = useState(''); const [password, setPassword] = useState('');

const handleLogin = () => { if (username === 'admin' && password === '123456') { navigation.navigate('UploadResult'); } else { navigation.navigate('Home'); } };

return ( <View style={styles.container}> <Text style={styles.title}>Bukiy 111 Login</Text> <TextInput
style={styles.input}
placeholder="Username"
value={username}
onChangeText={setUsername}
/> <TextInput
style={styles.input}
placeholder="Password"
value={password}
secureTextEntry
onChangeText={setPassword}
/> <Button title="Login" onPress={handleLogin} /> </View> ); }

const styles = StyleSheet.create({ container: { flex: 1, justifyContent: 'center', padding: 20, }, title: { fontSize: 24, textAlign: 'center', marginBottom: 20, }, input: { borderWidth: 1, borderColor: '#ccc', padding: 10, marginBottom: 15, borderRadius: 5, }, });

