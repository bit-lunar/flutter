# Aula 48

## Problema

O widget `RaisedButton` foi alterado na versão 2 do flutter e agora se chama `ElevatedButton`. Além da mudança de nome, o mesmo não possui mais os mesmos argumentos que seu antecessor. No caso, o argumento `textColor`.

## Solução

É preciso adicionar um Widget `TextColor` dentro de `Text` para alterar diretamente o seu estilo. Com:

```dart
ElevatedButton(
    onPressed: null,
    child: Text(
        texto,
        style: const TextStyle(
            color: Colors.grey,
        ), // TextStyle
    )); // Text // ElevatedButton
```
