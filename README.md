# IRPF Fácil — Agregador de Dados para o Imposto de Renda

> Planilha em Excel com cara de aplicativo que organiza dados pessoais, informes bancários e lançamentos de rendimentos e despesas para facilitar a declaração do Imposto de Renda (IRPF).

---

## Sobre o projeto

Este projeto foi desenvolvido para o desafio da **DIO**, que propõe criar, em Excel, uma ferramenta capaz de organizar e reunir as informações necessárias para a declaração do Imposto de Renda.

A ideia é simples: o contribuinte (ou o contador dele) preenche tudo em um só lugar, com campos guiados, listas de opções e uma conferência automática que avisa quando alguma informação está faltando.

A estrutura segue a lógica do formulário oficial da Receita Federal, mas **a planilha não é um aplicativo da Receita nem transmite a declaração**. Ela serve apenas para **organizar os dados** antes do preenchimento oficial.

---

## Objetivos

- Centralizar em um único arquivo os dados necessários para declarar o IR
- Ser fácil de usar por quem não tem conhecimento técnico, com navegação por botões (sem depender das abas do Excel)
- Evitar erros de digitação por meio de listas suspensas
- Indicar automaticamente o que ainda falta preencher
- Servir de base organizada para entregar a um contador ou para declarar sozinho

---

## Estrutura da planilha

A planilha tem **4 abas visíveis** e **1 aba de apoio oculta**. As abas do Excel ficam escondidas de propósito: a navegação é feita pelos botões da própria planilha, para dar a sensação de um aplicativo.

| Aba | Função |
|---|---|
| **INÍCIO** | Tela inicial, com botões de acesso às demais telas |
| **TITULAR** | Dados pessoais do contribuinte (nome, CPF, RG, data de nascimento, título de eleitor, cônjuge, endereço, contatos, dependentes, residência no exterior) |
| **INFORMES** | Informes de bancos e corretoras: instituição, tipo de informe, saldo em 31/12, rendimentos no ano, IR retido na fonte e arquivo de referência |
| **LANÇAMENTOS** | Recebimentos e despesas do período de 12 meses, com categoria, valor bruto/pago, IR retido e documento de comprovação |
| **TABELAS APOIO** *(oculta)* | Alimenta as listas suspensas das demais abas |

---

## Como funciona

### Navegação por botões
- A tela **INÍCIO** tem botões para **TITULAR**, **INFORMES** e **LANÇAMENTOS**.
- Nas demais telas há botões de **INÍCIO**, de acesso direto às outras abas e de **ANTERIOR / PRÓXIMO**, para percorrer o preenchimento em ordem.

### Conferência automática
- **TITULAR:** a coluna *Conferência* mostra **"Preenchido"** ou **"Faltam dados"** para cada campo, com destaque visual (formatação condicional) quando falta informação.
- **INFORMES:** a coluna *Situação* fica em branco quando a linha está vazia, mostra **"Faltam dados"** se algum campo da linha estiver sem preenchimento (instituição, tipo, saldo, rendimentos, IR retido ou arquivo) e **"Registrado"** quando a linha está completa.
- **LANÇAMENTOS:** a coluna *Situação* fica em branco quando a linha está vazia e mostra **"Faltam dados"** se tipo, descrição, categoria, valor ou IR retido estiverem vazios. Se esses campos estiverem preenchidos, mas faltar o nome do documento/arquivo, mostra **"Conferir documento"**. Com tudo preenchido, mostra **"Registrado"**. Isso vale tanto para recebimentos quanto para despesas.

### Listas suspensas (validação de dados)
- **TITULAR:** *Houve alterações da entrega anterior* (Sim/Não), *Possui dependentes* (Não, 1 a 10) e *Residente do exterior* (Sim/Não).
- **INFORMES:** *Instituição* (lista de bancos e corretoras com o código) e *Tipo de informe* (Conta corrente, Conta Poupança, Investimentos, Previdência, Outros).
- **LANÇAMENTOS:** *Tipo* (Recebimento ou Despesa) e *Categoria* (Salário, Pró-labore, Autônomo, Aluguel, 13º salário, PLR, Aplicação financeira, Isento/não tributável, Saúde, Educação, Previdência privada, Pensão alimentícia e Outro).

Todas as listas de INFORMES e LANÇAMENTOS vêm da aba de apoio e usam **intervalos nomeados** (`Bancos`, `Tipo_Informe`, `Tipo_Registro` e `Categoria`/`Categorias`). Para alterar uma lista, basta editar a aba **TABELAS APOIO**.

### Totais
- Na aba **INFORMES**, a linha de **Total** soma automaticamente saldo, rendimentos e IR retido com a função `SOMA`.

---

## Dados de exemplo

O arquivo vem com **dados fictícios** (por exemplo, "Ana Rosa Madalena Silva", CPF `000.000.000-00`) apenas para demonstrar o funcionamento. Apague-os e preencha com os seus dados antes de usar.

> **Privacidade:** a planilha reúne dados pessoais e financeiros. Evite compartilhar o arquivo preenchido sem necessidade.

---

## Como usar

1. Baixe o arquivo `agregador_irpf.xlsx`.
2. Abra no **Microsoft Excel** e, se solicitado, clique em **Habilitar edição**.
3. Na tela **INÍCIO**, clique em **TITULAR** e preencha os campos amarelos.
4. Avance para **INFORMES** e registre **um informe por linha**, conforme o documento da instituição.
5. Vá para **LANÇAMENTOS** e registre **uma linha por recebimento ou despesa**, escolhendo o tipo e a categoria.
6. Confira a coluna de **conferência / situação**: o ideal é que não reste nenhum **"Faltam dados"** ou **"Conferir documento"**.
7. Com tudo organizado, use as informações para preencher a declaração no programa oficial da Receita Federal ou entregue a planilha ao seu contador.

---

## Recursos do Excel utilizados

- Validação de dados com listas suspensas ligadas à aba de apoio
- Intervalos nomeados (`Bancos`, `Tipo_Informe`, `Tipo_Registro`, `Categoria`)
- Funções `SE`, `OU`, `CONT.VALORES` e `SOMA`
- Formatação condicional
- Formas com hiperlinks internos (botões de navegação)
- Hiperlink de e-mail (`mailto`)
- Aba oculta para tabelas de apoio

---

## Aviso importante

Esta planilha **não substitui** o programa oficial da Receita Federal, **não transmite** a declaração e **não faz cálculo de imposto**. Ela apenas ajuda na organização dos dados. A validação final e o envio das informações à Receita são de **responsabilidade do contribuinte**.

---
