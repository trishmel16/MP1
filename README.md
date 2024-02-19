import React, { useState } from "react";
import { View, Switch, Image, StyleSheet, Text } from "react-native";

const LightSwitch = () => {
  const [isEnabled, setIsEnabled] = useState(false);
  const toggleSwitch = () => setIsEnabled(previousState => !previousState);

  return (
    <View style={[styles.container, {backgroundColor: isEnabled ? 'yellow' : 'black'}]}>
      <Switch
        trackColor={{ false: "#767577", true: "#81b0ff" }}
        thumbColor={isEnabled ? "#f5dd4b" : "#f4f3f4"}
        ios_backgroundColor="#3e3e3e"
        onValueChange={toggleSwitch}
        value={isEnabled}
      />
      <Image 
        source={isEnabled ? require('lightbulb y.png') : require('white.png')} 
        style={styles.image}
      />
      <Text style={[styles.text, {color: isEnabled ? 'black' : 'white'}]}>
        Light is {isEnabled ? 'On' : 'Off'}
      </Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: "center",
    justifyContent: "center",
  },
  image: {
    width: 100,
    height: 100,
  },
  text: {
    fontSize: 20,
    fontWeight: 'bold',
  },
});

export default LightSwitch;
