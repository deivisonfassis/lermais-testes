# Lermais — Documento de Requisitos v1.0

> **Como usar este modelo:** copie este arquivo para `entregas/REQUISITOS-<nome-do-app>.md` e preencha. Você vai descobrir os requisitos usando o app e lendo o código, como um analista faria com um sistema sem documentação. As **perguntas-guia** em cada seção ajudam a encontrar as regras. Apague as perguntas quando terminar.
>
> Use o `agendafacil/REQUISITOS-AgendaFacil.md` como exemplo de formato.

---

**Produto:** Biblioteca Digital e Reserva de Livros
**Plataformas:** Web
**Versão analisada:** 1.0
**Autor deste documento:** Deivison
**Como os requisitos foram levantados:** Uso do App

## 1. Contexto

Ler+ é um aplicativo da biblioteca municipal. para usuarios cadastrados no biblioteca. a pesquise e a locação de livros.

> **Perguntas-guia:** Quem são os usuários? Existem perfis diferentes (cliente, administrador, atendente)? O que a pessoa consegue fazer hoje que não conseguia sem o app?

## 2. Dados e tabelas de referência

Os dados que são visiveis na aplicação são as quantidade de "Exemplares"

Nos arquivo dados possui informações de locação de livros como Data, Limites de dias, Multas

> **Perguntas-guia:** Existe algum preço, prazo, limite ou lista fixa no código (por exemplo, em um arquivo de dados ou em constantes no topo de um arquivo)? Quais valores aparecem na tela sempre iguais?

## 3. Regras de negócio

Escreva uma regra por item, numerada, com valores exatos. Uma boa regra dá para testar: diz o que acontece, em qual condição e com qual limite.

**RN01 — numero de matricula.** o numero de matricula tem que ter exatamente 6 caracteres

**RN02 — nome de usuario.** o nome de ser composto somente por letras, sem numeros os sinais.

**RN03 — Busca de livros** as buscas por livros deve ser somente pelo nome e pelo autor

**RN04 — Reserva** a reserva so pode ser efeituada somente logado no sistema

**RN05 — Limite retirada** o limite de para retirada do livro e no prazo de dois dias

**RN06 — Consulta local** algums livros não pode ser locados, somente consulta na biblioteca

**RN07 — Devolução** o prazo de devolução é de 10 dias, com multa com a devolução apos a data.

**RN08 — Fila** quando chegar a vez na fila a reservar e feita automaticamente.

> **Perguntas-guia para achar regras:**
> - Que campos o app pede? Algum é obrigatório? Tem tamanho mínimo, máximo ou formato?
> - Que botões existem? O que acontece em cada um? Algum fica desabilitado em alguma situação?
> - Que mensagens de erro aparecem? Cada mensagem de erro esconde uma regra.
> - Existe algum limite de quantidade, valor, tempo ou tentativas?
> - O que muda com o tempo (prazos, expiração, datas)?
> - O que acontece quando algo acaba (estoque, vagas, saldo)?
> - No código: procure `if`, números soltos e nomes como `LIMITE`, `MAX`, `MIN`, `PRAZO`, `TAXA`.

## 4. Requisitos não-funcionais

**RNF01 — [Desempenho, segurança, privacidade, compatibilidade, acessibilidade...].** [Descrição verificável.]

**RNF01 — segurança** - o login deve ser feitos com o codigo da matricula e uma senha
**RNF02 — acessibilidade** - a cores do app deve esta adaptada para daltonismo
**RNF03 — desempenho** - o numero de livros deve ser no minimo de 10

> **Perguntas-guia:** Em que navegadores ou aparelhos o app precisa funcionar? Ele guarda dados pessoais? Onde? O app funciona só com teclado? Quanto tempo ele pode levar para carregar? Quantos usuários ao mesmo tempo?

## 5. Fora do escopo

[O que o app não faz nesta versão, mesmo que pareça que deveria.]

 - pagina com mais informaçoes do livro 
 - caso haja multas, um seção somente para isso 
 - pagamento de multas de forma online 
 - Historico de livros locados 

## 6. Dúvidas e comportamentos estranhos

| # | O que foi observado | Por que é uma dúvida | Pergunta para quem desenvolveu |
| --- | --- | --- | --- |
| 1 | Botão consulta desativado | não precisa essa botao | tem necessidade desse botao? poderia ser somente um texto? |
| 2 | Botão devolução | a devolução não é somente na bilioteca | poderia se somente o texto de status |

> **Atenção:** quando você descobre uma regra usando o app, você descobre o que o app **faz**, que nem sempre é o que ele **deveria** fazer. Se algo parecer errado, não transforme em regra: registre aqui como dúvida.

## 7. Critério de aceitação do produto


CA01 - o sistema de fazer o login 
CA02 - o painel bibliotecario de informar todos livros locados 
CA03 - a busca deve ser feita usando o nome e autor do livros 
CA04 - a deve-se confirmar a reserva, exibindo o prazo de retirada
CA05 - apos a integra uma multa deve ser aplicada, somente permitindo uma nova locação apos o pagamento
CA06 - para as filas a reserva é feita automaticamente quando chegar a vez do usuarios
