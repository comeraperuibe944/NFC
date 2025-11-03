
# NFC Access

**NFC Access** é uma aplicação web interativa que utiliza o sensor **NFC (Near Field Communication)** do navegador para simular um sistema de controle de acesso.  
O projeto permite cadastrar, editar, excluir e gerenciar usuários identificados por meio de cartões NFC, com interface moderna, animações suaves e persistência de dados via **LocalStorage**.

---

## Sumário
- [Descrição Geral](#descrição-geral)
- [Funcionalidades Principais](#funcionalidades-principais)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Como Funciona](#como-funciona)
- [Estrutura de Armazenamento](#estrutura-de-armazenamento)
- [Interface e Interatividade](#interface-e-interatividade)
- [Como Executar](#como-executar)
- [Melhorias Futuras](#melhorias-futuras)


---

## Descrição Geral

O **NFC Access** foi desenvolvido para demonstrar o uso prático da **API Web NFC**, simulando um sistema de portaria ou controle de entrada.  
O aplicativo detecta cartões NFC (ou simula leituras quando o dispositivo não possui suporte) e permite:

- Exibir mensagens de acesso permitido ou negado
- Cadastrar novos usuários
- Registrar o histórico de acessos
- Editar e excluir cadastros existentes
- Excluir todos os registros de uma vez

Todas as informações são armazenadas localmente no navegador, sem necessidade de servidor.

---

## Funcionalidades Principais

- Leitura de cartões NFC (via `NDEFReader`)
- Cadastro de novos usuários diretamente pela leitura do cartão
- Histórico de acessos com data e hora
- Edição e exclusão de usuários
- Exclusão total dos dados armazenados
- Feedback visual e sonoro em cada ação
- Animação de fundo em canvas
- Persistência de dados local (LocalStorage)
- Design moderno e responsivo

---

## Tecnologias Utilizadas

| Categoria | Ferramenta / API |
|------------|------------------|
| Linguagem  | HTML5, CSS3, JavaScript (ES6+) |
| API        | Web NFC (`NDEFReader`) |
| Armazenamento | LocalStorage (JSON) |
| Efeitos Visuais | Canvas API, animações CSS |
| UI/UX | Layout minimalista com gradientes e transparência |

---

## Como Funciona

1. Ao abrir o site, o usuário vê uma tela inicial pedindo permissão para acessar o NFC.
2. Após conceder a permissão, o sistema entra em modo de leitura e exibe a mensagem: "Aproxime seu cartão NFC".
3. Quando um cartão é detectado:
   - Se o cartão já estiver cadastrado, exibe uma mensagem de boas-vindas, registra o acesso e reproduz um som.
   - Se o cartão não estiver cadastrado, mostra "Acesso Negado" e oferece a opção de cadastrar o novo cartão com um nome.
4. O menu lateral permite:
   - Visualizar e editar os cadastros
   - Excluir usuários individualmente
   - Excluir todos os registros
5. Os dados são salvos e carregados automaticamente via `localStorage`.

---

## Estrutura de Armazenamento

Os dados são gravados na chave `nfc_users_v2` do LocalStorage, com o formato abaixo, sinta-se livre para modificar conforme seu banco de dados de escolha:

```json
{
  "idDoCartaoNFC": {
    "name": "Nome do Usuário",
    "lastAccess": "2025-11-03T14:22:05.123Z",
    "accessHistory": [
      "2025-11-03T14:22:05.123Z",
      "2025-11-01T09:45:22.510Z"
    ]
  }
}
````

---

## Interface e Interatividade

Principais elementos da interface:

| Elemento              | Função                                 |
| --------------------- | -------------------------------------- |
| Tela inicial (splash) | Solicita permissão para o NFC          |
| Leitor NFC principal  | Exibe o status da leitura e instruções |
| Mensagens de status   | Mostram sucesso, erro ou alerta        |
| Tela de boas-vindas   | Exibe acesso permitido ou negado       |
| Menu lateral          | Acesso às opções do sistema            |
| Modal de usuários     | Lista e gerenciamento dos cadastros    |
| Som e vibração        | Feedbacks para leitura e erro          |

---

## Como Executar

Acesse em:  https://comeraperuibe944.github.io/NFC/

---

## Melhorias Futuras

* Autenticação e sincronização com banco de dados remoto
* Integração com servidor para registros centralizados
* Relatórios de estatísticas de acesso completa
* Interface administrativa completa
* Suporte total a desktop com simulação visual de tags

---
