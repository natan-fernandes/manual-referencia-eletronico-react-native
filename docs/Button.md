---
sidebar_position: 5
---

# Button
Um componente básico de botão que deve renderizar de boas em qualquer plataforma. Suporta uma quantidade mínima de customização.

Se o botão não ficar legal no seu app, você pode construir o seu próprio botão usando o TouchableOpacity ou o TouchableWithoutFeedback. Para se inspirar, dê uma olhadinha no [código fonte do componente de botão](https://github.com/facebook/react-native/blob/master/Libraries/Components/Button.js) ou nos [botões criados pela comunidade](https://js.coach/?menu%5Bcollections%5D=React%20Native&page=1&query=button).

```tsx
<Button
  onPress={onPressLearnMore}
  title="Learn More"
  color="#841584"
  accessibilityLabel="Learn more about this purple button"
/>
```

## Exemplo
```tsx
import React from 'react';
import { StyleSheet, Button, View, SafeAreaView, Text, Alert } from 'react-native';

const Separator = () => (
  <View style={styles.separator} />
);

const App = () => (
  <SafeAreaView style={styles.container}>
    <View>
      <Text style={styles.title}>
        The title and onPress handler are required. It is recommended to set accessibilityLabel to help make your app usable by everyone.
      </Text>
      <Button
        title="Press me"
        onPress={() => Alert.alert('Simple Button pressed')}
      />
    </View>
    <Separator />
    <View>
      <Text style={styles.title}>
        Adjust the color in a way that looks standard on each platform. On  iOS, the color prop controls the color of the text. On Android, the color adjusts the background color of the button.
      </Text>
      <Button
        title="Press me"
        color="#f194ff"
        onPress={() => Alert.alert('Button with adjusted color pressed')}
      />
    </View>
    <Separator />
    <View>
      <Text style={styles.title}>
        All interaction for the component are disabled.
      </Text>
      <Button
        title="Press me"
        disabled
        onPress={() => Alert.alert('Cannot press this one')}
      />
    </View>
    <Separator />
    <View>
      <Text style={styles.title}>
        This layout strategy lets the title define the width of the button.
      </Text>
      <View style={styles.fixToText}>
        <Button
          title="Left button"
          onPress={() => Alert.alert('Left button pressed')}
        />
        <Button
          title="Right button"
          onPress={() => Alert.alert('Right button pressed')}
        />
      </View>
    </View>
  </SafeAreaView>
);

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    marginHorizontal: 16,
  },
  title: {
    textAlign: 'center',
    marginVertical: 8,
  },
  fixToText: {
    flexDirection: 'row',
    justifyContent: 'space-between',
  },
  separator: {
    marginVertical: 8,
    borderBottomColor: '#737373',
    borderBottomWidth: StyleSheet.hairlineWidth,
  },
});

export default App;
```

---

## Referência

### Props

### `onPress`*
Handler que é chamado quando o usuário aperta no botão.

TIPO |
---- |
function(PressEvent) |

---

### `title`*
Texto que vai aparecer dentro do botão. No Android o texto vai ser convertido pra caixa alta.

TIPO |
---- |
string |

---

### `accessibilityLabel`
Cor do texto no iOS ou do fundo do botão no Android.

TIPO | PADRÃO
---- | ------
color | `'#2196F3'` (Android) <br/> `'#007AFF'` (iOS)

---

### `disabled`
Se `true`, desabilita todas as interações desse componente.

TIPO | PADRÃO
---- | ------
bool | `false`

---

### `hasTVPreferredFocus` (TV)
Isso aqui eu acho que é pra ver se tem foco preferido em TVs.

TIPO | PADRÃO
---- | ------
bool | `false`

---

### `nextFocusDown` (Android e TV)
Escolhe a próxima view a receber o foco quando o usuário navegar para baixo. [Veja a documentação do Android.](https://developer.android.com/reference/android/view/View.html#attr_android:nextFocusDown)

TIPO |
---- |
number |

---

### `nextFocusForward` (Android e TV)
Escolhe a próxima view a receber o foco quando o usuário navegar para frente. [Veja a documentação do Android.](https://developer.android.com/reference/android/view/View.html#attr_android:nextFocusForward)

TIPO |
---- |
number |

---

### `nextFocusLeft` (Android e TV)
Escolhe a próxima view a receber o foco quando o usuário navegar para a esquerda. [Veja a documentação do Android.](https://developer.android.com/reference/android/view/View.html#attr_android:nextFocusLeft)

TIPO |
---- |
number |

---

### `nextFocusRight` (Android e TV)
Escolhe a próxima view a receber o foco quando o usuário navegar para a direita. [Veja a documentação do Android.](https://developer.android.com/reference/android/view/View.html#attr_android:nextFocusRight)

TIPO |
---- |
number |

---

### `nextFocusUp` (Android e TV)
Escolhe a próxima view a receber o foco quando o usuário navegar para cima. [Veja a documentação do Android.](https://developer.android.com/reference/android/view/View.html#attr_android:nextFocusUp)

TIPO |
---- |
number |

---

### `testID`
Usado pra localizar esta view em testes de ponta-a-ponta.

TIPO |
---- |
string |

---

### `touchSoundDisabled` (Android)
Se `true`, não toca o som do sistema quando aperta o botão.

TIPO | PADRÃO
---- | ------
string | `false`