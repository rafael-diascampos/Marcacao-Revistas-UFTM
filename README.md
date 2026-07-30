# Marcação-Revistas-UFTM

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

## Estilos

O conjunto é **o mesmo para todas as revistas da UFTM**, vindo do modelo ODT oficial (padrão SciELO/JATS). São 66 estilos: 51 de parágrafo e 15 de caractere.

- Metadados: `Artigo_TituloPrincipal`, `Artigo_DOI`, `Artigo_Secao`, `Artigo_Licenca_CC`, etc.
- Autoria: `Autor_Nome`, `Autor_Aff`, `Autor_Email`, `Autor_Orcid`
- Resumos: `Resumo_PT` / `_EN` / `_ES`, com `Resumo_Titulo_*` e `Kwd_*`
- Corpo: `Corpo_Texto`, `Citacao_Direta`, `Figura_Legenda`, `Figura_Fonte`, `Quadro_Legenda`, `Quadro_Fonte`
- Referências: `Referencia_Item` e os estilos de caractere `Ref_Autor`, `Ref_Titulo`, `Ref_DOI`, `Ref_URL`, etc.

## Status

Em construção (v0.1). Prontos: módulo VBA, XML do botão, instalador e roteiro de montagem. Falta gerar o `.dotm`, escrever o guia da equipe e publicar a primeira Release.

## Estrutura

```
Marcacao-Revistas-UFTM/
  dist/            saida de build (.dotm; ignorado pelo git)
  docs/            MONTAR-DOTM.md e notas de projeto
  modelo/          Modelo-Estilos-Revistas-UFTM.docx (fonte dos estilos)
  ribbon/          customUI14.xml (o botao)
  scripts/         Instalar.bat, Instalar-Revistas-UFTM.ps1, InjetarRibbon.ps1
  src/             modImportarEstilosRevista.bas
  LICENSE
  README.md
```

Como montar o `.dotm`: ver `docs/MONTAR-DOTM.md`.

## Licença

MIT (ver `LICENSE`).
