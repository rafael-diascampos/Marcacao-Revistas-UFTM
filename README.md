# Marcacao-Revistas-UFTM

Add-in VBA para Microsoft Word: um botão que **importa os estilos de marcação** das revistas da Editora UFTM para o artigo que está aberto. Sem copiar e colar. Sem abrir modelo. Sem "Salvar como".

O arquivo de distribuição é um único `.dotm` (macros + estilos juntos), no mesmo espírito do add-in do Zotero: instala uma vez na pasta STARTUP do Word e o botão aparece em qualquer documento.

## Para quem marca artigos (resumo)

1. **Uma vez:** baixar a release, rodar o instalador, fechar e abrir o Word.
2. **Cada artigo:** baixar o `.docx` no sistema da revista → abrir → clicar no botão → marcar com os estilos da lista → salvar → subir.

Guia passo a passo: ainda em elaboração (`docs/`).

## O que este repositório **não** é

- Não é o kit **Norm@lize** (faxina tipográfica, notas, etc.). Esse vive noutro repo / pasta.
- Não exige LibreOffice. Quem usa LibreOffice tem caminho nativo documentado no guia (quando existir).

## Instalação (Word, Windows)

1. Feche o Word por completo.
2. Baixe o `.dotm` (e o instalador, se houver) na [Release](#) mais recente.
3. Rode o instalador **ou** copie o `.dotm` para a pasta STARTUP do Word, por exemplo:  
   `C:\Users\<você>\AppData\Roaming\Microsoft\Word\STARTUP\`
4. Abra o Word, habilite macros se pedido, e procure o botão / aba da revista.

Arquivos baixados da internet podem ser bloqueados pelo Windows. O instalador deve desbloquear o `.dotm` antes de copiar. Se aparecer "O Windows protegeu o seu PC", use **Mais informações** → **Executar mesmo assim** (é esperado sem certificado de assinatura).

## Status

Scaffold inicial. Ainda faltam: lista real de estilos (a partir do modelo da revista), macro `ImportarEstilosRevista`, ribbon mínimo, instalador e guia para monitores.

## Estrutura

```
Marcacao-Revistas-UFTM/
  dist/            saida de build (.dotm; ignorado pelo git)
  docs/            guia e notas de projeto
  scripts/         instalador e build de release
  src/             modulos VBA
  LICENSE
  README.md
```

## Licença

MIT (ver `LICENSE`).
