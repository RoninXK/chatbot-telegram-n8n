# 🤖 Chatbot no Telegram com n8n e API de Inteligência Artificial

## 📌 Sobre o projeto

Este projeto foi desenvolvido como parte de uma atividade prática com o objetivo de criar um chatbot funcional no Telegram, utilizando o n8n como ferramenta de automação e uma API de Inteligência Artificial para gerar respostas automáticas.

A ideia principal foi construir um fluxo simples, mas funcional, capaz de receber mensagens enviadas pelo usuário no Telegram, processar essas mensagens dentro do n8n e retornar uma resposta automaticamente.

Além do funcionamento básico, também foram adicionados comandos personalizados para deixar o bot mais organizado e fácil de usar.

---

## 🎯 Objetivo

O objetivo do projeto é demonstrar, na prática, como diferentes ferramentas podem se comunicar por meio de APIs.

Com esse chatbot, foi possível aplicar conceitos de:

- Automação de processos;
- Integração entre sistemas;
- Criação de bots no Telegram;
- Uso de APIs externas;
- Fluxo de dados entre plataformas;
- Respostas automáticas com Inteligência Artificial.

---

## 🛠️ Ferramentas utilizadas

Para desenvolver o projeto, foram utilizadas as seguintes ferramentas:

- **Telegram**: usado como interface de conversa com o usuário;
- **BotFather**: ferramenta utilizada para criar e configurar o bot no Telegram;
- **n8n**: plataforma usada para montar o fluxo de automação;
- **API de Inteligência Artificial**: responsável por gerar respostas automáticas;
- **Groq**: utilizada como API de IA durante os testes do projeto;
- **GitHub**: usado para armazenar a documentação e os arquivos da atividade.

---

## ⚙️ Como o chatbot funciona

O funcionamento do chatbot acontece em etapas:

1. O usuário envia uma mensagem para o bot no Telegram.
2. O n8n recebe essa mensagem pelo nó **Telegram Trigger**.
3. O nó **Edit Fields** organiza as principais informações recebidas, como:
   - ID do chat;
   - texto enviado pelo usuário;
   - comando digitado.
4. O nó **Switch** verifica se a mensagem enviada é um comando específico.
5. Se for um comando, o bot envia uma resposta pronta.
6. Se for uma pergunta comum, a mensagem é enviada para a API de Inteligência Artificial.
7. A resposta gerada pela IA é enviada automaticamente de volta para o usuário no Telegram.

---

## 🔁 Fluxo criado no n8n

O fluxo foi organizado da seguinte forma:

```text
Telegram Trigger
↓
Edit Fields
↓
Switch
├── /start  → Responder /start
├── /help   → Responder /help
├── /sobre  → Responder /sobre
└── mensagem comum → Groq → Send a text message
```

Esse fluxo permite que o chatbot responda tanto comandos específicos quanto perguntas abertas feitas pelo usuário.

---

## 💬 Comandos implementados

Foram criados alguns comandos para melhorar a experiência de uso do bot.

### `/start`

Inicia o bot e exibe uma mensagem de boas-vindas.

### `/help`

Mostra os comandos disponíveis e explica como o usuário pode interagir com o chatbot.

### `/sobre`

Apresenta uma breve explicação sobre o projeto e sobre o funcionamento do fluxo no n8n.

---

## 🧪 Exemplo de uso

O usuário pode enviar uma mensagem comum, como:

```text
O que é inteligência artificial?
```

Nesse caso, a mensagem passa pelo fluxo do n8n, é enviada para a API de IA e o bot retorna uma resposta automática no Telegram.

Também é possível utilizar comandos, como:

```text
/start
/help
/sobre
```

Nesses casos, o bot responde com mensagens prontas configuradas no próprio fluxo.

---

## 🚧 Dificuldades encontradas

Durante o desenvolvimento, algumas dificuldades apareceram, principalmente na configuração dos nós e no tratamento das mensagens.

As principais dificuldades foram:

- Criar e configurar corretamente o bot no Telegram;
- Conectar o token do Telegram ao n8n;
- Configurar corretamente o corpo JSON da requisição;
- Ajustar a chamada para a API de Inteligência Artificial;
- Entender como o n8n trata expressões e variáveis;
- Configurar o nó **Switch** para separar comandos de mensagens comuns;
- Ajustar os campos de `chat_id` para garantir que o bot respondesse ao usuário correto.

Essas dificuldades ajudaram a entender melhor como funciona a comunicação entre plataformas e como os dados passam de um nó para outro dentro do n8n.

---

## 🔐 Cuidados de segurança

Por segurança, nenhuma chave de API ou token de acesso foi colocado neste repositório.

É importante não compartilhar publicamente:

- Token do bot do Telegram;
- Chave da API de Inteligência Artificial;
- Credenciais do n8n;
- Informações sensíveis usadas no fluxo.

Caso alguma chave seja exposta acidentalmente, o ideal é revogar a chave antiga e criar uma nova.

---

## 📝 Observação sobre a API utilizada

A proposta original da atividade previa o uso de uma API de Inteligência Artificial integrada ao fluxo do n8n. Durante o desenvolvimento e testes, foi utilizada a API da **Groq** como alternativa para gerar as respostas automáticas.

Mesmo com essa adaptação, o projeto manteve a ideia central da atividade: criar um chatbot no Telegram, integrado ao n8n, com chamada HTTP para uma API externa de IA.

---

## ✅ Resultado final

Ao final do desenvolvimento, foi criado um chatbot funcional no Telegram, capaz de:

- Receber mensagens do usuário;
- Responder comandos específicos;
- Encaminhar perguntas comuns para uma API de IA;
- Retornar respostas automaticamente;
- Demonstrar um fluxo completo de automação no n8n.

---

## 📚 Conclusão

Este projeto permitiu compreender, na prática, como sistemas diferentes podem ser integrados por meio de APIs.

O Telegram funcionou como canal de comunicação com o usuário, o n8n foi responsável pela automação do fluxo, e a API de Inteligência Artificial foi utilizada para gerar respostas automáticas.

A atividade ajudou a visualizar como soluções semelhantes podem ser aplicadas em situações reais, como atendimento automatizado, suporte ao usuário, assistentes virtuais e integração entre serviços digitais.
