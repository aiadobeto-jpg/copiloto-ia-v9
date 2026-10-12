# Contexto do Co-piloto.ia — leia antes de alterar

## Estado salvo

Este repositório contém a versão atual do Co-piloto.ia para Florianópolis. A versão está publicada no GitHub e foi revisada em 12/10/2026.

Repositório: https://github.com/aiadobeto-jpg/copiloto-ia-v9
Commit atual: 7701cc2
Arquivo principal: `index.html`

## O que existe agora

O aplicativo é um HTML único, mobile-first, sem iframe e sem o crédito “Made with Runable”. A navegação inferior tem cinco áreas: Agora, Bairros, Eventos, Turno e Perguntar.

A tela Agora apresenta check-up, score estimado, ação recomendada, quatro melhores bairros, previsão de seis horas e alertas. A tela Bairros permite busca e seleção compacta de aproximadamente 30 bairros. A tela Eventos é independente e exibe agenda com data destacada, horário, local, bairro, categoria, impacto estimado, confiança e fonte clicável. Turno registra corridas no localStorage. Perguntar responde perguntas simples usando o motor local.

O botão de GPS tenta selecionar o bairro mais próximo da posição do aparelho. O clima é consultado pelo Open-Meteo quando há internet; em caso de falha, o app informa que está offline. A atualização automática ocorre a cada minuto.

## Agenda de eventos

A base atual contém 23 referências de eventos, com 22 ativos ou futuros na data da última atualização. Os eventos encerrados são filtrados da agenda operacional. As fontes usadas foram:

- Guia Floripa: https://guiafloripa.com.br/agenda
- Imagem da Ilha: https://imagemdailha.com.br/agenda-cultural.html
- Baladas Floripa: https://baladasfloripa.com.br/agenda-outubro-em-floripa-2026-shows-festas/
- Blueticket / Folianópolis: https://www.blueticket.com.br/evento/39368/folianopolis-2026-dias-30-31-de-outubro-e-01-de-novembro
- Floripa.com: https://www.floripa.com/eventos/

Os critérios e limitações estão documentados em `docs/eventos-fontes.md`.

## Regra de honestidade dos dados

Não afirmar que os scores de bairro são dados reais de Uber, 99, inDrive ou chamadas do mercado. O aplicativo não tem acesso autorizado a essas plataformas. Os scores são heurísticas de horário, bairro, temporada e regras locais.

Não afirmar que um evento é garantido. A agenda vem de páginas públicas e pode mudar, ser cancelada ou ter horário alterado. O app deve mostrar a fonte e marcar “horário não informado”, “confirmado” ou “adiado” quando aplicável.

## O que não fazer

- Não reintroduzir o antigo iframe “Inteligência V9”.
- Não restaurar a interface branca antiga com abas longas.
- Não adicionar novamente “Made with Runable”.
- Não apresentar estimativas como certezas.
- Não remover as fontes dos eventos.
- Não trocar o arquivo único por uma aplicação que dependa de backend sem explicar a mudança.

## Próximas evoluções possíveis

A melhoria mais importante seria criar uma rotina de atualização de eventos com fontes públicas e registro de data da última verificação. Depois, melhorar o modelo de demanda usando registros reais de corridas do motorista, com comparação entre previsão e resultado. Para tráfego e chamadas em tempo real seria necessário uma integração autorizada com APIs ou dados fornecidos pelo usuário.

Ao continuar o trabalho, primeiro abra `index.html`, este arquivo e `docs/eventos-fontes.md`. Preserve o visual compacto e teste no celular antes de publicar.
