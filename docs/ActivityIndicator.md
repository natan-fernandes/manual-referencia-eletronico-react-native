---
sidebar_position: 4
---

# ActivityIndicator
Exibe um indicador circular de carregamento.

## Exemplo
```tsx
import React from "react";
import { ActivityIndicator, StyleSheet, Text, View } from "react-native";

const App = () => (
  <View style={[styles.container, styles.horizontal]}>
    <ActivityIndicator />
    <ActivityIndicator size="large" />
    <ActivityIndicator size="small" color="#0000ff" />
    <ActivityIndicator size="large" color="#00ff00" />
  </View>
);

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center"
  },
  horizontal: {
    flexDirection: "row",
    justifyContent: "space-around",
    padding: 10
  }
});

export default App;
```

# Referência
## Props
### View Props
Herda de View Props.

---

### `animating`

Mostra o indicador (`true`) ou esconde (`false`).

TIPO | PADRÃO
-----|-------
bool | `true`

---

### `color`

A cor do indicador.

TIPO|PADRÃO
----|------
color|`null` (cor padrão Android) <br/> `#999999` (iOS)

---

### `hidesWhenStopped`

Oculta o indicador se não estiver animado.

TIPO|PADRÃO
----|------
bool | `true`

---

### `size`

Tamanho do indicador.

TIPO|PADRÃO
----|------
enum(`'small'`, `'large'`) <br/> number | `'small'`




eaoueaoea|eqweq
-|-
1|4