# Correção do erro `Missing \begin{document}` no Overleaf

O erro ocorreu porque o arquivo `elementos-pre-textuais/lista-de-abreviaturas-e-siglas.tex` estava usando:

```latex
\begin{siglas}
...
\end{siglas}
```

No template UECE (`uecetex2`), esse arquivo é carregado ainda no preâmbulo, antes de `\begin{document}`. Por isso ele não pode conter ambientes de impressão de lista.

A correção foi trocar o conteúdo por comandos `\newacronym`, que são próprios para serem declarados no preâmbulo:

```latex
\newacronym{ci}{CI}{Continuous Integration}
```

## Como compilar

No Overleaf ou no PC, compile sempre pelo arquivo:

```text
documento.tex
```

Em compilação local, use preferencialmente:

```bash
pdflatex documento.tex
bibtex documento
makeglossaries documento
pdflatex documento.tex
pdflatex documento.tex
```

Se não quiser gerar glossário/siglas no PC, o PDF ainda pode sair com avisos, mas não deve falhar por causa da lista de siglas.
