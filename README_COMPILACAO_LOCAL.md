# Projeto UECE atualizado — CI/CD, DORA e Zero Trust

## Arquivo principal
Compile sempre o arquivo:

```text
documento.tex
```

Não compile `preambulo.tex`, pois ele é apenas importado pelo projeto.

## Comandos recomendados no PC

Com TeX Live completo instalado:

```bash
pdflatex documento.tex
bibtex documento
makeindex documento.idx
makeglossaries documento
pdflatex documento.tex
pdflatex documento.tex
```

Ou, se tiver `latexmk` configurado:

```bash
latexmk -pdf documento.tex
```

## Observações

- O pacote já contém os capítulos substituídos:
  - `elementos-textuais/introducao.tex`
  - `elementos-textuais/fundamentacao-teorica.tex`
  - `elementos-textuais/trabalhos-relacionados.tex`
  - `elementos-textuais/metodologia.tex`
  - `elementos-textuais/resultados.tex`
  - `elementos-textuais/conclusao.tex`
- O arquivo `elementos-pos-textuais/referencias.bib` foi atualizado.
- As figuras TikZ estão em `figuras/`.
- O `lib/preambulo.tex` mantém o template UECE e adiciona apenas TikZ.

## Se der erro no TikZ

Confirme se sua instalação possui o pacote PGF/TikZ. Em distribuições TeX Live, ele vem no pacote `texlive-pictures` ou no TeX Live full.

## Se der erro no BibTeX

Confirme se o comando `bibtex` está instalado e disponível no PATH.
