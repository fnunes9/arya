# Arya — agente de IA de QA para o Claude
 
A Arya é uma skill para o Claude que monta e executa rotinas de teste de interface, tela por tela. Ela aprende com o time pelo kanban, gera um relatório padrão e avisa a equipe no Discord.
 
## Como ela funciona
 
- **Modo Montar:** a Arya faz perguntas sobre a tela, a documentação, o design e as regras de segurança. Com as respostas, gera o guia da rotina, os casos de teste e o prompt da tarefa agendada. A rotina só vale depois da sua aprovação.
- **Modo Executar:** a Arya roda a rotina do início ao fim, sem parar para perguntar, e entrega um único relatório.
As regras de teste, a documentação e o design são responsabilidade de quem monta a rotina. A Arya traz o método, e o Claude executa os testes.
 
## O que você precisa
 
- Claude com suporte a skills e a extensão Claude in Chrome, com a sessão do ambiente de teste já logada.
- Um kanban conectado ao Claude, com:
  - um épico, tag ou label para agrupar as tarefas da Arya;
  - uma coluna **"Reservado pra Arya"**. É nela que o time coloca as tarefas que não são falha, com um comentário. A Arya lê essa coluna em toda execução e transforma cada caso em regra, para não repetir o mesmo achado.
- Um canal no Discord com webhook.
- Um projeto no Claude para cada tela.
## Instalação
 
1. Baixe o arquivo `arya-compartilhar.skill`.
2. No Claude, vá em Configurações > Capacidades > Skills e envie o arquivo.
## Primeiros passos
 
1. Peça: "Arya, me ajude a integrar o meu kanban com você."
2. Copie `references/perfis/exemplo.md` e preencha com os dados da sua empresa.
3. Peça: "Arya, vamos criar uma rotina para a tela [nome da tela]."
## O que vem na skill
 
- `SKILL.md`: quem é a Arya, os dois modos e as regras gerais.
- `assets/moldes/`: moldes padronizados (ARYA-entrevista, ARYA-guia, ARYA-casos, ARYA-prompt, ARYA-relatorio, ARYA-tarefa, ARYA-comentarios, ARYA-regra-aprendida, ARYA-discord, ARYA-perfil).
- `references/integracao-kanban.md`: roteiro para integrar o seu kanban.
- `references/perfis/exemplo.md`: perfil de exemplo para preencher.
## Cuidados
 
- A Arya nunca faz login nem digita senhas.
- Ela só mexe nas tarefas que ela mesma criou.
- Nunca coloque senhas, tokens ou URLs de webhook nos arquivos da skill.
