# LLM Tutor — Prompt de Tutoria Socrática

Um system prompt para transformar qualquer LLM com suporte a instruções customizadas em um **tutor socrático**. Não é fixado em nenhuma matéria: a identidade do prompt tem dois placeholders (`[ADICIONE SUA MATÉRIA AQUI]` e `[ADICIONE SEU EXEMPLO PRÁTICO AQUI]`) — basta preenchê-los com o tema e o exemplo do dia a dia que você quiser usar como fio condutor (o exemplo original de referência, usado durante o desenvolvimento deste prompt, foi modelagem de dados com um app de delivery).

O objetivo não é responder — é guiar o estudante a *entender* a lógica por trás do assunto, forçando ele a justificar as próprias respostas antes de avançar.

## Compatibilidade

Funciona em qualquer plataforma que aceite instruções de sistema customizadas:
- ChatGPT (Custom GPT / instruções do projeto)
- Claude (Projects / system prompt via API)
- Gemini (Gems)
- Qualquer LLM open-source rodando com um system prompt

## Como usar

1. Copie o conteúdo de [`prompts/claude-tutor-v2.md`](prompts/claude-tutor-v2.md)
2. Substitua `[ADICIONE SUA MATÉRIA AQUI]` e `[ADICIONE SEU EXEMPLO PRÁTICO AQUI]` na tag `<identity>` pelo tema e exemplo que você quiser
3. Cole como system prompt / instruções customizadas na plataforma de sua escolha
4. (Opcional) Anexe seu material de curso — o prompt prioriza esse material antes de ir além dele
5. Comece a conversa apresentando o que já sabe e onde está travando

## Estrutura do prompt

| Tag | O que faz |
|---|---|
| `<identity>` | Quem o modelo é e qual o objetivo final (ensinar, não resolver) |
| `<socratic_method>` | O processo de condução — as 4 fases de toda dúvida |
| `<rules>` | Comportamentos concretos e condicionais (quando aplicar quiz, quando travar o avanço) |
| `<state_tracking>` | Como o modelo declara o progresso — camada de auditoria |
| `<anti_sycophancy>` | Postura contra concordar/elogiar por reflexo |
| `<tone>` | Como a mensagem soa — nunca sobrepõe o conteúdo |

## Bugs encontrados e corrigidos

Este prompt passou por debug ativo depois de observar sessões reais de uso. Ver [`CHANGELOG.md`](CHANGELOG.md) para o histórico completo, incluindo:
- Quiz de fechamento de nível sendo pulado silenciosamente (regra usava "ofereça" em vez de "aplique")
- Roadmap sendo marcado como concluído sem critério de aprovação real
- Frases truncadas na versão original

## Licença

MIT — use, adapte e redistribua livremente.
