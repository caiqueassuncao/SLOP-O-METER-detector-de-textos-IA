# AI Slop Detector

Detector de padrões linguísticos de IA rodando 100% no navegador, sem dependências externas, sem servidor, sem API.

---

## Como usar

1. Baixe o arquivo `ai_slop_detector.html`
2. Abra direto no navegador (duplo clique no arquivo)
3. Cole o texto no painel esquerdo
4. Clique em **Analisar** (ou `Ctrl+Enter`)
5. Veja o score e os sinais detalhados no painel direito

Não precisa instalar nada. Funciona offline.

---

## Como funciona

O detector roda 9 sinais heurísticos sobre o texto e combina os resultados num score ponderado de 0 a 100%.

| Sinal | O que detecta | Peso |
|---|---|---|
| Frases de abertura IA | "Certainly!", "Let's delve", "I'd be happy to" | 1.5 |
| Palavras-enchimento | delve, tapestry, nuanced, robusto, alavancar... | 2.0 |
| Estrutura formulaica | Listas em cascata, "In conclusion", headers em **negrito** | 1.5 |
| Hedging excessivo | "It's important to note", "Keep in mind that" | 1.2 |
| Uniformidade de sentenças | IA tem variância baixa no tamanho das frases | 1.8 |
| Diversidade lexical (TTR) | IA recicla vocabulário mais do que parece | 1.0 |
| Comprimento de palavras | IA prefere "utilize" a "usar", "leverage" a "usar" | 0.8 |
| Uniformidade de parágrafos | IA produz parágrafos de tamanho suspeitosamente igual | 1.3 |
| Comprimento de sentença | IA vive na zona confortável de ~18–28 palavras | 0.7 |

### Interpretação do score

| Score | Veredicto |
|---|---|
| 75–100% | 🤖 Muito provável — AI Slop |
| 55–74% | ⚠️ Suspeito — possível IA |
| 35–54% | 🔍 Incerto — pode ser humano ou IA |
| 0–34% | ✅ Provavelmente humano |

---

## Limitações

- Funciona melhor com textos de **pelo menos 100 palavras** — textos curtos têm sinais estatísticos fracos
- Detecta padrões de LLMs em inglês e português, mas o peso dos sinais é otimizado para inglês
- Não é infalível — um humano que escreve de forma muito formal pode ter score alto, e uma IA bem ajustada pode ter score baixo
- Não usa modelo de linguagem nem perplexidade — é baseado em regras, portanto transparente e auditável

---

## Tecnologias

- HTML + CSS + JavaScript puro
- Zero dependências externas
- Zero chamadas de rede
- Funciona offline

---

## Publicação

Para publicar online, as opções mais simples são:

**Netlify Drop** — arrasta o arquivo em [netlify.com/drop](https://netlify.com/drop), gera link na hora.

**GitHub Pages** — sobe o arquivo como `index.html` num repositório e habilita Pages em Settings.

---

## Licença

MIT — use, modifique e distribua à vontade.
