# aula 42

## Comentários de mudança nos dois códigos

- Código da aula

```Dart
import 'package:flutter/material.dart';

class Questao extends StatelessWidget {

  const Questao({super.key});

  final String texto;

  Questao(this.texto);

  @override
  Widget build(BuildContext context) {
    return Text(texto);
  }
}
```

- Código CORRETO

```Dart
import 'package:flutter/material.dart';

class Questao extends StatelessWidget {
  
final String texto;

  const Questao(this.texto, {super.key});

  @override
  Widget build(BuildContext context) {
    return Text(texto);
  }
}
```

A principal diferença entre os dois é a posição do parametro `{super.key}` no construtor da classe `Questao`.

Ao passar tanto `this.texto` quanto `super.key`, você está garantindo que o construtor da widget seja chamado com todos os argumentos necessários, tanto para inicializar a própria widget quanto para conectá-la à árvore de widgets. (_Fonte: Gemini_).
