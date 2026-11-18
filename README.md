# 🧊 Controle da Geladeira

Aplicativo web simples para controlar os produtos que ficam na geladeira expositora durante a noite.

Antes de ir embora você conta o que tem (**noite**). Ao chegar de manhã você conta de novo (**manhã**). O app mostra a **diferença**, ou seja, o que saiu. Com o preço de cada item, ele compara **venda** e **perda**.

## Funcionalidades

- **Contagem**: escolha 🌙 Noite, ☀️ Manhã ou 🧾 Vendido e use **+** e **−** (ou digite) em cada produto. **Saiu** = noite − manhã. **Perda** = saiu − vendido. Mostra tudo em unidades e em R$. Se a manhã for maior que a noite, ou o vendido maior que o que saiu, o produto fica marcado como "conferir".
- **Conferência com o relatório**: a venda pela contagem (saiu × preço) é comparada com o valor que você lança do relatório, e o app diz se bateu ou qual é a diferença.
- **Histórico**: dia a dia, total geral de venda e perda em R$, e resumo por produto. Botão para copiar tudo em CSV.
- **Preços**: adicionar, renomear e remover produtos, com preço de venda e custo (opcional). A perda é valorizada pelo preço de venda. Os removidos continuam no histórico.
- Funciona **sem internet** e pode ser instalado na tela inicial do celular (PWA).
- Tema claro e escuro automáticos.

## Como publicar no GitHub Pages

1. Crie um repositório novo no GitHub (por exemplo `controle-geladeira`).
2. Envie todos os arquivos desta pasta para a raiz do repositório.
3. No repositório, abra **Settings → Pages**.
4. Em **Build and deployment**, escolha **Deploy from a branch**, branch `main` e pasta `/ (root)`, e salve.
5. Depois de um ou dois minutos o app abre em `https://SEU-USUARIO.github.io/controle-geladeira/`.

No celular, abra esse endereço e use **Adicionar à tela inicial** do navegador para instalar.

## Onde ficam os dados

Tudo é salvo no `localStorage` do navegador, no próprio aparelho. Não há servidor nem conta, e os dados **não sincronizam** entre aparelhos diferentes. Limpar os dados do navegador apaga o histórico, então use o botão **Copiar histórico (CSV)** de vez em quando como cópia de segurança.

## Estrutura

| Arquivo | Para que serve |
|---|---|
| `index.html` | O aplicativo inteiro (HTML, CSS e JavaScript) |
| `manifest.webmanifest` | Dados para instalar como app |
| `sw.js` | Service worker para funcionar offline |
| `icon.svg` | Ícone do app |

## Rodar localmente

Não precisa instalar nada. Para testar o modo offline, sirva a pasta por HTTP:

```bash
python3 -m http.server 8000
```

e abra `http://localhost:8000`.
