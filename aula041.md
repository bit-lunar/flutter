# aula 41

## OBS 01

Apesar de que não era o foco da aula:

Detalhe do código feito em dart: na nova versão, o atributo precisa ter um valor atribuido antes de ser usado o objeto. Formas de resolver isso:

- inicializar os atributos dentro da propria classe. O this é como se fosse o self, tipo:

``` dart
class Pessoa {
  String nome;
  String _cpf;

  // Construtor nomeado para inicializar os atributos
  Pessoa({required this.nome, required this.cpf});
}

void main() {
  var p1 = Pessoa(nome: 'João', cpf: '12345678900'); // CPF sem formatação

  print('O ${p1.nome} tem cpf ${p1._cpf}');
}
```

- usar um valor padrao, tipo String nome = '';
- usar o late antes, significa que ele vai ser inicializado depois tipo late String nome;

## OBS 02

``` Dart
ElevatedButton(
    onPressed: _responder,
    child: const Text('Resposta 1'),
    ),
```

onPressed espera receber uma função como parametro, ao passar `_responder` sem parênteses, você está passando a própria função e não o resultado da sua execução. Isso significa que qnd pressionar o botão, o Flutter vai chamar a função para a gente. Fazendo com que o contexto correto seja chamado, por exemplo a variavel que tem o valor incrementado. Se fosse chamado como função `_responder()`, a função era executada na hora da construção do proprio widget e não quando o botão fosse pressionado.

## OBS 03 - Pendente

Dúvida pendente:

``` Dart
class PerguntaApp extends StatefulWidget {
  const PerguntaApp({super.key});

  @override
  _PerguntaAppState createState() {
    return _PerguntaAppState();
  }
}
```

O `_PerguntaAppState` está com uma notificação de problema: "Invalid use of a private type in a public API.
Try making the private type public, or making the API that uses the private type also be private.dartlibrary_private_types_in_public_api". Ainda não descobri o porque não pode ser privado dentro da classe que ficou publica!

- Não é um erro, pois o programa está sendo executado normalmente.
