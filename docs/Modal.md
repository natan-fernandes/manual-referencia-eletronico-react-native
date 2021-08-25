---
sidebar_position: 6
---

# Modal
O componente do Modal é uma forma básica de mostrar um conteúdo sobre outro.

## Exemplo
```tsx
import React, { useState } from "react";
import { Alert, Modal, StyleSheet, Text, Pressable, View } from "react-native";

const App = () => {
  const [modalVisible, setModalVisible] = useState(false);
  return (
    <View style={styles.centeredView}>
      <Modal
        animationType="slide"
        transparent={true}
        visible={modalVisible}
        onRequestClose={() => {
          Alert.alert("Modal has been closed.");
          setModalVisible(!modalVisible);
        }}
      >
        <View style={styles.centeredView}>
          <View style={styles.modalView}>
            <Text style={styles.modalText}>Hello World!</Text>
            <Pressable
              style={[styles.button, styles.buttonClose]}
              onPress={() => setModalVisible(!modalVisible)}
            >
              <Text style={styles.textStyle}>Hide Modal</Text>
            </Pressable>
          </View>
        </View>
      </Modal>
      <Pressable
        style={[styles.button, styles.buttonOpen]}
        onPress={() => setModalVisible(true)}
      >
        <Text style={styles.textStyle}>Show Modal</Text>
      </Pressable>
    </View>
  );
};

const styles = StyleSheet.create({
  centeredView: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
    marginTop: 22
  },
  modalView: {
    margin: 20,
    backgroundColor: "white",
    borderRadius: 20,
    padding: 35,
    alignItems: "center",
    shadowColor: "#000",
    shadowOffset: {
      width: 0,
      height: 2
    },
    shadowOpacity: 0.25,
    shadowRadius: 4,
    elevation: 5
  },
  button: {
    borderRadius: 20,
    padding: 10,
    elevation: 2
  },
  buttonOpen: {
    backgroundColor: "#F194FF",
  },
  buttonClose: {
    backgroundColor: "#2196F3",
  },
  textStyle: {
    color: "white",
    fontWeight: "bold",
    textAlign: "center"
  },
  modalText: {
    marginBottom: 15,
    textAlign: "center"
  }
});

export default App;
```

---

## Referência
### Props

#### `animationType`
A propriedade `animationType` controla como o modal é animado.
  
Valores possíveis:
- `slide` escorrega de baixo pra cima,
- `fade` esmaece na tela,
- `none` aparece sem animação.

TIPO | PADRÃO
-----|--------
enum(`'none'`, `'slide'`, `'fade'`) | `none`

---

#### `hardwareAccelerated` (Android)
A propriedade `hardwareAccelerated` controla quando vai ou não forçar aceleração de hardware na janela que está debaixo do modal.

TIPO | PADRÃO
-----|--------
booleano | `false`

---

#### `onDismiss` (iOS)
A propriedade `onDismiss` permite passar uma função que vai ser disparada quando o modal for fechado.

TIPO |
-----|
function |

---

#### `onOrientationChange` (iOS)
O callback `onOrientationChange` é chamado quando a orientação é alterada enquanto o modal está na tela. As orientações fornecidas são somente 'portrait' (retrato) ou 'landscape' (paisagem). Esse callback também é chamado na primeira renderização, independente da orientação atual.

TIPO |
-----|
function |

---

#### `onRequestClose`
O callback `onRequestClose` é chamado quando o usuário aperta no botão de voltar do android ou no botão do menu da Apple TV. Note que, no android, essa propriedade é obrigatória, então os eventos `BackHandler` não vão ser disparados se o modal estiver aberto.

TIPO |
-----|
function* (Android, TV) |
function (iOS) |

---

#### `onShow`
A propriedade `onShow` permite passar uma função que vai ser chamada quando o modal aparecer.

TIPO |
-----|
function |

---

#### `presentationStyle` (iOS)
A propriedade `presentationStyle` controla como o modal vai aparecer (geralmente nos aparelhos grandes como iPad ou iPhones Plus). Para mais detalhes da uma olhada aqui: [https://developer.apple.com/reference/uikit/uimodalpresentationstyle](https://developer.apple.com/reference/uikit/uimodalpresentationstyle)

Valores possíveis:
- `fullscreen` preenche a tela toda
- `pageSheet` preenche a largura de retrato centralizada (somente em dispositivos grandes) (nem eu entendi isso aqui)
- `formSheet` preenche a largura estreita centralizada (somente em dispositivos grandes)
- `overFullScreen` preenche a tela toda mas permite transparência

TIPO | PADRÃO
-----|-------
enum(`'fullScreen'`, `'pageSheet'`, `'formSheet'`, `overFullScreen`) | `fullScreen` se `transparent={false}`,  `overFullScreen` se `transparent={true}`

---

#### `statusBarTranslucent` (Android)
A propriedade `statusBarTranslucent` determina quando o seu modal deve ir debaixo da barra de status do sistema.

TIPO | PADRÃO
-----|-------
booleano | `false`

---

#### `supportedOrientations` (iOS)
A propriedade `supportedOrientations` permite qe o modal seja rotacionado para qualquer orientação. No iOS, o modal ainda é restrito pelo o que está especificado no Info.plist do seu aplicativo no campo UISupportedInterfaceOrientations.

> Se estiver usando `presentationStyle` com `pageSheet` ou `formSheet`, essa propriedade vai ser ignorada pelo iOS.

TIPO | PADRÃO
-----|-------
vetor de enums(`'portrait'`, `'portrait-upside-down'`, `'landscape'`, `'landscape-left'`, `'landscape-right'`) | `['portrait']`

---

#### `transparent`
A propriedade `transparent` determina quando o modal deve preencher toda a tela. Se setar pra `true`, vai renderizar o modal por cima de um fundo transparente.

TIPO | PADRÃO
-----|-------
booelano | `false`

---

#### `visible`
A propriedade `visible` determina quando o modal vai estar visível.

TIPO | DEFAULT
-----|--------
booleano | `true`