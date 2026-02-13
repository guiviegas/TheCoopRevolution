# Whitepaper Design - The Coop Revolution

## Overview

Whitepaper navegavel em pagina web separada, seguindo a mesma identidade visual da landing page.

## Decisoes Tecnicas

- **Localizacao:** `/whitepaper.html`
- **Tecnologia:** HTML/CSS/JS puro (igual landing page)
- **Idiomas:** EN/ES/PT com sistema `data-lang`
- **Fontes:** Space Grotesk + JetBrains Mono
- **Paleta:** Preto/Branco (igual landing page)

## Layout

```
+------------------+--------------------------------+
|  Logo            |            [EN] [ES] [PT]      |
+------------------+--------------------------------+
|                  |                                |
|  Sidebar Menu    |       Conteudo                 |
|                  |       (scroll interno)         |
|  - Inicio        |                                |
|  - Principios    |                                |
|  - Como Funciona |                                |
|  - Participar    |                                |
|  - Mais Fundo    |                                |
|  - Entre         |                                |
|                  |                                |
+------------------+--------------------------------+
|  Footer: link para landing, contato               |
+---------------------------------------------------+
```

**Mobile:** Sidebar vira menu hamburguer

## Estrutura de Conteudo

```
INICIO
  - The Coop Revolution em 2 minutos

OS PRINCIPIOS
  - 9 artigos fundacionais (v0.1)

COMO FUNCIONA
  - Uma rede, nao uma empresa
    - O centro vazio
    - Proposito como commons
    - O que a rede oferece
  - Cooperativas para tudo
    - O que e uma coop da rede
    - Estrutura dorsal (criterios)
    - 3 niveis de relacao
    - Coop-franchising
    - As 5 primeiras (Protocol, Bank, Cafe, Edu, Lab)
  - Um token, nao uma moeda
    - COOP Token (identidade + sinalizacao)
    - Quotas de cooperativa
    - O que o token nao e
    - O experimento
  - Dinheiro que circula
    - Dentro de cada coop
    - Entre cooperativas
    - Coops -> Protocol
    - Contribuicoes voluntarias
    - Franquias -> Marca coletiva

COMO PARTICIPAR
  - Entre numa cooperativa
    - A jornada (aprender fazendo)
  - Crie a sua
    - Usando os templates
    - Open source (self-hosted)
    - Cloud (Protocol hospeda)
  - Contribua de outras formas
    - Como builder
    - Como investidor
    - Como consumidor

MAIS FUNDO
  - Governanca em detalhe
    - 1 pessoa 1 voto (base legal)
    - O cardapio de ferramentas
    - Templates prontos
  - A infraestrutura tecnica
    - 6 camadas
  - O caminho (roadmap)
    - Fases 0-6

ENTRE
  - Junte-se ao movimento
```

## Os 9 Principios (v0.1 - a revisar)

1. **Propriedade compartilhada.** Nao tem dono. Tem donos. Quem trabalha, constroi e participa divide a propriedade. Juntos.

2. **Poder nao se compra.** Capital pode ter retorno. Controle, nao. Governanca e das pessoas, nao do dinheiro.

3. **Governanca transparente.** Decisoes visiveis. Financas visiveis. Quem votou o que, visivel. Confianca nasce de poder ver.

4. **O centro esta vazio.** A rede e uma DAO sem dono, sem sede, sem CEO. Ela guarda o proposito e a cultura — o resto e de quem faz.

5. **Cooperativas soberanas.** Cada uma e autonoma. Entra por escolha, sai quando quiser. Conectadas, nunca controladas.

6. **Digital desde o inicio.** Nasceu na internet, escala na internet. Ferramentas modernas, governanca programavel, sem burocracia analogica.

7. **Colaboracao como estrutura.** Nao e valor no slide. E como a coisa e feita. Distribuido no DNA, desde o primeiro dia.

8. **Codigo e conhecimento abertos.** O que construimos vira bem publico. Templates, ferramentas, aprendizados. Usa quem quiser.

9. **Um experimento vivo.** Nao sabemos todas as respostas. Testamos, aprendemos, evoluimos. A rede e um laboratorio em movimento.

## Tom e Estilo

- Conversacional como padrao
- Tecnico quando necessario
- Sem emojis
- Direto, claro, com personalidade
- "Nos acreditamos...", "Estamos construindo..."

## Referencias

- ENS DAO Basics (https://basics.ensdao.org/)
- Optimism Docs (https://docs.optimism.io/)
- Stripe Docs (https://docs.stripe.com/)

## Notas

- Principios precisam revisao profunda (parte mais importante)
- Estrutura dorsal (criterios de entrada) precisa revisao
- Templates do Protocol precisam desenvolvimento detalhado
- Roadmap precisa revisao
