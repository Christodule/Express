
import React, { useState } from "react";

import { StyleSheet, Button, Alert,  SafeAreaView } from "react-native";

const App = () => {
  const [ setSend]=useState('')
  const [ setMontant]=useState('')
  const [ setCode]=useState('')


  const send = () => 
  Alert.prompt(
    "Envoyer au:",
    "numero du beneficiaire",
    text => setSend(text)
  );

    
const montant = () =>
Alert.prompt(
  "Entrez le montant",
  "montant:",
  text => setMontant(text)
);


const code = () =>
Alert.prompt(
  "vous voulez envoyez (setMontant) F.CFA au numero: (setSend). Frais de transaction (Frais) ",
  "Entrez votre code secret",
  text => setCode(text)
)

  const createThreeButtonAlert = () =>
    Alert.alert(
      "choisissez votre:",
      "carte sim",
      [
        
        {
          text: "Telmob",
          onPress: () => {send(montant(code()))} 
          
        },
        { text: "Airtel", 
        onpress: () => {send(montant(code()))}
        }
      ],
    );


    

  return (
    <SafeAreaView style={[styles.container, containerStyle,]}>
      <Button title={"Transfert"} onPress={createThreeButtonAlert} />
    </SafeAreaView>
    

  );

}
  

const containerStyle = {backgroundColor:"orange"}
const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
    backgroundColor:'#fff',
    width:"100%",
    height:"30%",
  },
});

export default App;
