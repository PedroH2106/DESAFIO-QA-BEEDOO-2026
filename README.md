# DESAFIO-QA-BEEDOO-2026

## 1. Análise inicial da aplicação

A aplicação disponibilizada tem como objetivo permitir o cadastro e a visualização de cursos em um sistema simples.

O usuário pode cadastrar um novo curso informando dados como:

- Nome do curso
- Descrição
- Instrutor
- URL da imagem
- Data de início
- Data de fim
- Número de vagas
- Tipo do curso (Online ou Presencial)

Após o cadastro, o curso deve ser exibido na página de listagem.

O sistema simula um módulo de gestão de cursos, permitindo validar fluxos básicos de criação e visualização de dados.

---

# 2. Principais fluxos da aplicação

## Fluxo 1 — Cadastro de curso

1. Usuário acessa a página de cadastro
2. Preenche os dados do curso
3. Clica em "Cadastrar"
4. O sistema valida os campos
5. O curso é salvo
6. Usuário é redirecionado para a listagem

---

## Fluxo 2 — Listagem de cursos

1. Usuário acessa a página de cursos
2. O sistema exibe todos os cursos cadastrados
3. Cada curso aparece em formato de lista ou card

---

# 3. Pontos críticos para teste

Os pontos mais críticos identificados são:

### Validação de campos
Todos os campos são obrigatórios.

Devem ser validados:

- campos vazios
- formatos inválidos
- datas inconsistentes
- número de vagas negativo

---

### Regras de negócio

- Data final deve ser maior ou igual à data inicial
- Número de vagas deve ser número inteiro positivo
- Tipo do curso deve ser Online ou Presencial
- Cursos presenciais devem ter endereço
- Cursos online devem ter link

---

### Persistência de dados

Após cadastrar:

- curso deve aparecer na listagem
- dados devem ser mantidos após refresh da página

---

### Experiência do usuário

- mensagens de erro claras
- confirmação de cadastro
- redirecionamento correto

---

# 4. Estratégia de testes

Os testes foram criados considerando:

- fluxo principal do sistema
- cenários negativos
- validações de campos
- comportamentos inesperados

O objetivo foi garantir boa cobertura dos fluxos críticos da aplicação.

---

# 5. Planilha de cenários e casos de teste

Os cenários de teste estão documentados em:

Google Sheets

link da planilha: https://docs.google.com/spreadsheets/d/1iDEEzQiaCzInxu2e2M0NDoJBG80zQAzgh-3ZNQrm2BQ/edit?usp=sharing

---

# 6. Evidências da execução

As evidências dos testes executados estão disponíveis em:

Google Drive

(link do drive aqui)(https://drive.google.com/drive/folders/1T84_WkVSHX69VP03Sk8G5y01XV_TIFpf?usp=sharing)

---

# 7. Bugs encontrados

Durante a execução dos testes foram encontrados os seguintes problemas.

---
Bug 1
Título: Sistema permite cadastrar curso com campo nome vazio

Passos
1 acessar página cadastro
2 deixar campo nome vazio
3 clicar em cadastrar

Resultado atual:Curso é cadastrado
Resultado esperado:Sistema deve impedir cadastro
Severidade:Alta
---
---
Bug 2
Título: Sistema aceita número negativo de vagas

Passos
1 acessar cadastro
2 inserir -10 em vagas
3 cadastrar

Resultado atual:Curso é salvo
Resultado esperado:Sistema deve bloquear valores negativos
Severidade:Alta
---
---
Bug 3
Título: Campo URL aceita texto inválido

Passos
1 inserir texto aleatório no campo URL
2 cadastrar curso

Resultado atual:Curso cadastrado
Resultado esperado: Sistema deve validar URL
Severidade:Média
---
---
Bug 4
Nao podera apagar nenhum curso todos eles continuam mesmo fazendo refresh na pag (F5)

Passos
1 cadastrar curso
2 aperte F5
3 continuam os curso que eram pra ser excluidos
---
---
Resultado atual:Curso cadastrado
Resultado esperado: Sistema deve apagar o curso
Severidade:Alta
---
---
Bug 5
Nao esta responsivo para celulares

Passos
1 clique com botao direito na pag
2 vai em insepcionar
3 aperte no icone do computador e celular no canto superior esquerdo
4 o titulo Beedoo QA Chalenge nao aparece 

Resultado atual:Alguem com celular nao consegue usar
Resultado esperado: Seja responsivo para todas as plataformas
Severidade:Alta
---
---
Bug 6
Ao clicar no texto-home da pagina (Beedoo QA Chalenge) nao leva ao inicio da pagina

Passos
1 apenas tente clicar em Beedoo QA Chalenge

Resultado atual:Nada ocorre
Resultado esperado:Voltaria para o inicio da pagina
Severidade:Media
---
