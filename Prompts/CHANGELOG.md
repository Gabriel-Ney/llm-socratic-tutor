# Changelog

## v2

### Corrigido
- **Quiz sendo pulado no fim de cada nível.** A regra usava "ofereça Quiz ou Flashcards", o que deixava a aplicação opcional a critério do modelo. Trocado por gate obrigatório: o quiz é aplicado diretamente, sem perguntar permissão.
- **Roadmap marcado como concluído sem critério real de aprovação.** A regra de atualizar o roadmap não estava amarrada ao resultado do quiz — qualquer resposta correta no chat era tratada como "domínio demonstrado". Agora o nível só fecha se o estudante acertar pelo menos 2 das perguntas do quiz daquele nível.
- **Conflito estrutural entre "uma pergunta por turno" e o quiz.** A regra de terminar toda resposta em uma única pergunta investigável não deixava espaço para o quiz aparecer. Adicionada exceção explícita nos turnos de fechamento de nível.
- **Frases truncadas na versão original**, provavelmente por corte na colagem: regras 5 e 7, e o bloco `<anti_sycophancy>`, foram reconstruídos.

### Adicionado
- Tag `<state_tracking>`: o modelo declara uma linha curta de status a cada transição de nível (quiz aplicado, aprovado, reprovado), facilitando auditoria externa do progresso.
- Placeholders `[ADICIONE SUA MATÉRIA AQUI]` e `[ADICIONE SEU EXEMPLO PRÁTICO AQUI]` na `<identity>`, no lugar do tema e exemplo fixos (Lógica de Sistemas / app de delivery) — qualquer estudante pode baixar e adaptar pra sua própria matéria editando essas duas partes.

### Conhecido / em investigação
- Em alguns usos, o tutor reinicia a conversa do zero (voltando à pergunta diagnóstica inicial) mesmo com um Roadmap já em andamento. Ainda não confirmado se isso ocorre dentro da mesma conversa (possível gatilho incorreto da regra de "início") ou apenas em conversas novas (limitação de memória entre sessões, não um bug do prompt em si).

## v1

Versão original, sem separação em tags: identidade, método socrático e regras num único bloco de texto corrido.
