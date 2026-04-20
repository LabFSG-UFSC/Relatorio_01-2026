# Guia Rápido para Editar Arquivos `.qmd`

Este repositório usa **Quarto**. Na prática, um arquivo `.qmd` é apenas um arquivo de texto onde você escreve o conteúdo do relatório.

Se você **nunca usou Markdown**, não se preocupe: para preencher sua parte, basta escrever texto normal e, quando precisar, copiar exemplos simples deste guia.

Para a maioria das pessoas, a regra é simples:

- abra apenas o arquivo da sua seção;
- escreva seu conteúdo nos títulos que já existem;
- se precisar, coloque imagens na pasta `img/`;
- salve e envie sua contribuição por branch e Pull Request.

## Fluxo rápido

Ex.: para o Kevin preencher o relatório `infra.qmd`, ele precisa:

1. Clonar o repositório na máquina dele.
2. Entrar na pasta do projeto.
3. Criar uma branch própria, por exemplo `kevin/infra`.
4. Editar apenas o arquivo `infra.qmd`.
5. Salvar, fazer `commit` e enviar a branch para o GitHub.
6. Abrir um Pull Request da branch dele para a `main`.

### Exemplo no Mac

No Terminal:

```bash
git clone https://github.com/LabFSG-UFSC/Relatorio_01-2026.git
cd Relatorio_01-2026
git checkout main
git pull origin main
git checkout -b kevin/infra
```

Depois de editar o arquivo:

```bash
git add infra.qmd
git commit -m "Preenche seção de infraestrutura"
git push -u origin kevin/infra
```

Se o Kevin também adicionou imagens novas na pasta `img/`, ele precisa incluir essas imagens no `git add`. Exemplo:

```bash
git add infra.qmd img/minha-imagem-1.png img/minha-imagem-2.png
git commit -m "Atualiza infraestrutura e adiciona imagens"
git push -u origin kevin/infra
```

### Exemplo no Windows

No Git Bash:

```bash
git clone https://github.com/LabFSG-UFSC/Relatorio_01-2026.git
cd Relatorio_01-2026
git checkout main
git pull origin main
git checkout -b kevin/infra
```

Depois de editar o arquivo:

```bash
git add infra.qmd
git commit -m "Preenche seção de infraestrutura"
git push -u origin kevin/infra
```

Se o Kevin também adicionou imagens novas na pasta `img/`, ele precisa incluir essas imagens no `git add`. Exemplo:

```bash
git add infra.qmd img/minha-imagem-1.png img/minha-imagem-2.png
git commit -m "Atualiza infraestrutura e adiciona imagens"
git push -u origin kevin/infra
```

Se a pessoa estiver usando o GitHub Desktop em vez de terminal, o fluxo é o mesmo:

1. Clonar o repositório.
2. Criar uma branch.
3. Editar `infra.qmd`.
4. Fazer commit.
5. Publicar a branch.
6. Abrir o Pull Request no GitHub.

## Antes de começar

Você **não precisa aprender Markdown inteiro**.

Na maior parte do tempo, você vai fazer só estas 3 coisas:

1. Escrever parágrafos normais.
2. Preencher tópicos que já estão no arquivo.
3. Inserir imagem usando um modelo pronto.

Se conseguir fazer isso, já consegue preencher sua seção.

## O que manter como está

- Não apague os títulos e subtítulos já criados no arquivo da sua seção.
- Não remova identificadores como `{#sec-carto}` no título principal.
- Evite alterar `_quarto.yml`, a ordem dos capítulos ou arquivos de outras pessoas sem combinar antes.

## Como escrever texto

Se quiser só escrever, escreva normalmente embaixo do título:

```md
## Atividades desenvolvidas

Nesta etapa, a equipe organizou as bases cartográficas, validou inconsistências e consolidou a estrutura territorial usada nas análises.
```

Ou seja: você pode simplesmente digitar o texto do relatório.

## Como fazer uma lista

Se quiser listar itens, use um hífen `-`:

```md
- Base territorial revisada.
- Padronização de nomes.
- Integração com cadastro.
```

## Como colocar uma imagem

Esta costuma ser a parte que mais gera dúvida. O jeito mais simples é:

1. salvar a imagem dentro da pasta `img/`;
2. copiar este modelo;
3. trocar o nome do arquivo.

Modelo:

```md
![Descrição da imagem](img/nome-da-imagem.png){width=80%}
```

Exemplo real:

```md
![Mapa da área de estudo](img/mapa-area-estudo.png){width=80%}
```

O que cada parte significa:

- `![Descrição da imagem]`: texto da legenda da figura;
- `(img/nome-da-imagem.png)`: caminho da imagem;
- `{width=80%}`: tamanho da imagem na página.

## Como escolher o nome da imagem

Prefira nomes simples, por exemplo:

- `img/mapa-infra.png`
- `img/servidores-labfsg.jpg`
- `img/fluxo-cartografia.png`

Evite:

- espaços no nome;
- acentos;
- nomes muito longos;
- misturar maiúsculas e minúsculas sem necessidade.

## Como colocar legenda na imagem

A legenda é o texto entre colchetes:

```md
![Figura 1. Mapa preliminar da área de estudo.](img/mapa-area-estudo.png){width=80%}
```

Se não quiser uma legenda elaborada, pode usar algo simples:

```md
![Mapa da área de estudo.](img/mapa-area-estudo.png){width=80%}
```

## Como citar a imagem no texto

Isso é opcional. Só use se quiser mencionar a figura dentro do texto.

Se você quiser citar a figura no próprio relatório, use um identificador:

```md
![Mapa preliminar da área de estudo.](img/mapa-area-estudo.png){#fig-mapa-area width=80%}
```

Depois, no texto:

```md
Como mostra a @fig-mapa-area, a distribuição espacial...
```

## Como ajustar o tamanho da imagem

Alguns exemplos úteis:

```md
![Imagem menor](img/exemplo.png){width=40%}
![Imagem média](img/exemplo.png){width=60%}
![Imagem maior](img/exemplo.png){width=90%}
```

Se a imagem ficar grande ou pequena demais no PDF, ajuste o `width`.

## O que fazer se a imagem não aparecer

Verifique estas 3 coisas:

1. A imagem está mesmo dentro da pasta `img/`?
2. O nome no arquivo está exatamente igual ao nome da imagem?
3. A extensão está certa, como `.png`, `.jpg` ou `.jpeg`?

Exemplo de erro comum:

```md
![Mapa](img/Mapa Cartografia.PNG)
```

Exemplo melhor:

```md
![Mapa](img/mapa-cartografia.png){width=80%}
```

## Dicas importantes para imagens

- Use nomes de arquivo simples, sem acentos e sem espaços.
- Prefira algo como `img/mapa_cartografia_sc.png` ou `img/mapa-cartografia-sc.png`.
- Verifique se o caminho da imagem está correto.
- Se possível, use `png`, `jpg` ou `jpeg`.
- Uma imagem muito pesada pode deixar a geração do PDF mais lenta.

## A imagem ficou enorme no PDF

Defina largura:

```md
![Mapa](img/mapa-cartografia.png){width=70%}
```

## Quero colocar mais de uma imagem

Você pode inserir uma abaixo da outra:

```md
![Mapa 1](img/mapa1.png){width=75%}

![Mapa 2](img/mapa2.png){width=75%}
```

## Negrito, itálico e links

Se quiser usar alguns recursos simples:

```md
Texto em **negrito**.

Texto em *itálico*.

[Link para um site](https://quarto.org/)
```

## Tabelas simples

Tabela em Markdown:

```md
| Etapa | Situação | Observação |
|---|---|---|
| Cartografia | Concluída | Base validada |
| Infraestrutura | Em andamento | Revisão de ambiente |
| Indicadores | Em andamento | Ajuste metodológico |
```

Se tabela for difícil, não tem problema: você pode deixar os dados em forma de lista ou texto corrido e depois alguém ajuda a ajustar.

## Checklist antes de enviar

- Editei apenas o arquivo da minha seção.
- Mantive os títulos e a estrutura do documento.
- As imagens foram salvas em `img/`.
- Os caminhos das imagens estão corretos.
- Ajustei o tamanho das imagens com `{width=...}` quando necessário.
- Revisei ortografia e clareza do texto.

## Exemplo completo

```md
## Resultados

Os produtos gerados nesta etapa permitiram consolidar a base territorial de referência do projeto.

![Mapa consolidado da área de estudo.](img/mapa-consolidado.png){#fig-mapa-consolidado width=85%}

Como mostra a @fig-mapa-consolidado, a base final já apresenta consistência suficiente para apoiar as próximas etapas.
```
