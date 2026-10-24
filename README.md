# Agende-me

Aplicativo Android de organização pessoal, planejamento de compromissos e gestão de rotina, desenvolvido em Kotlin com Jetpack Compose. O objetivo principal é reunir calendário, agenda do dia, notificações, feriados, clima e anotações em uma experiência simples, visualmente clara e útil para uso diário.

O Agende-me foi pensado para funcionar como um centro de organização pessoal: permitindo visualizar eventos do calendário do dispositivo, criar lembretes, acompanhar feriados, registrar anotações rápidas e manter o usuário sempre informado sobre o que está chegando.

## Visão geral

O app centraliza as principais atividades do usuário em uma interface de três abas:

- Início: lista os eventos e feriados em categorias como hoje, passados e próximos
- Calendário: exibe um calendário mensal com navegação por meses, indicadores de compromissos e clima por dia
- Anotações: permite criar registros rápidos, visualizar itens importantes e organizar ideias sem sair do app

A aplicação usa o calendário nativo do Android, solicita permissões necessárias para leitura/escrita de eventos e integra lembretes com notificações do sistema, além de aproveitar informações de geolocalização e clima para enriquecer a experiência.

## Funcionalidades

### 1. Agenda e organização pessoal

- Visualização de compromissos e feriados em uma tela inicial organizada por categoria
- Separação entre:
  - eventos futuros
  - compromissos de hoje
  - itens passados
- Ordenação por proximidade e data de ocorrência
- Cards visuais para diferenciar feriados, eventos e compromissos
- Exclusão direta de itens agendados com confirmação

### 2. Calendário mensal interativo

- Navegação entre meses
- Seleção de dia do mês
- Marcação visual de dias com compromissos ou feriados
- Indicadores de presença de evento, feriado e clima no calendário
- Toque duplo em um dia para rapidamente criar um novo agendamento para aquela data
- Visualização detalhada do dia selecionado com lista de itens vinculados à data

### 3. Criação de agendamentos

- Modal de criação de novo item com:
  - título
  - descrição
  - data
  - hora
  - opção de som de alarme
- Integração com o calendário nativo do Android via `CalendarContract`
- Criação automática de eventos no calendário do sistema
- Lembretes programados por `AlarmManager` e `PendingIntent`

### 4. Notificações e alertas

- Canal de notificações silencioso e canal com som para lembretes
- Agendamento de alarme para eventos com hora definida
- Cancelamento automático de lembrete quando o evento é removido

### 5. Anotações rápidas

- Criação de anotações com título e descrição
- Organização em cards com expansão/colapso de texto
- Copiar descrição para área de transferência com toque longo
- Exclução com confirmação
- Persistência local das anotações usando `SharedPreferences`

### 6. Clima e contexto do dia

- Consulta de previsão do tempo por data e hora usando Open-Meteo
- Busca do ícone climático mais adequado para cada evento
- Recuperação de localização do dispositivo para melhor contextualização do clima
- Ícones climáticos exibidos no calendário para ajudar na leitura do dia
- Atualização do widget com dados climáticos e eventos futuros

### 7. Widgets do app

- Atualização de dados para widget de calendário e agenda
- Persistência dos eventos em armazenamento local
- Reuso de ícones climáticos em widgets e superfícies de visualização
- Organização dos eventos por data e proximidade

### 8. Persistência local e sincronização com o sistema

- Armazenamento de anotações em `SharedPreferences`
- Registro de itens removidos para evitar duplicações ou reapresentação indevida
- Atualização automática da interface quando eventos do calendário mudam
- Recarregamento dos dados do calendário sempre que há necessidade

## Tecnologias e bibliotecas

O projeto utiliza principalmente:

- Kotlin
- Jetpack Compose
- Material 3
- Android Calendar Provider (`CalendarContract`)
- `AlarmManager` e `NotificationManager`
- `SharedPreferences` para persistência leve
- Retrofit para consumo da API de clima
- Open-Meteo para previsão do tempo
- AndroidSVG para renderização de ícones climáticos em PNG
- Glance App Widgets para atualização de widgets

## Como usar o Agende-me

### Tela inicial

Na aba inicial, o usuário vê uma lista organizada de itens relevantes:

- eventos e feriados passados
- compromissos de hoje
- próximos acontecimentos

Cada item é exibido em um card com informações visuais de data, hora e descrição. O usuário pode expandir o conteúdo, excluir o evento ou visualizar detalhes com mais facilidade.

### Calendário

Na aba de calendário:

- navegue entre meses
- selecione um dia
- veja os eventos daquele dia
- toque duas vezes em um dia para criar um novo agendamento
- acompanhe feriados com destaque visual

### Anotações

Na aba de anotações:

- adicione textos rápidos e úteis
- mantenha lembretes, ideias ou observações
- toque no card para expandir ou recolher o conteúdo
- toque longo para copiar a descrição para a área de transferência

### Criação de agenda

O modal de nova agenda permite que o usuário informe:

- nome do compromisso
- observações do evento
- data e hora
- opção de ativar som do lembrete

Se o usuário preencher apenas um título e descrição sem data, o app entende que a entrada é melhor tratada como anotação, e não como evento de calendário.

## Fluxo de funcionamento principal

O fluxo de execução do app pode ser resumido assim:

1. A aplicação solicita as permissões de calendário, notificações e localização.
2. Carrega os eventos do calendário nativo do Android.
3. Classifica feriados, compromissos e anotações.
4. Organiza a agenda por proximidade e relevância.
5. Agenda lembretes com `AlarmManager`.
6. Atualiza widgets e dados visuais da aplicação.
7. Mantém persistência local para garantir que os dados continuem acessíveis.

## Pontos fortes do app

- interface limpa e moderna
- foco em produtividade pessoal
- integração com o sistema do Android
- uso de calendário nativo para manter consistência com o restante do dispositivo
- organização visual por data e categoria
- chave para uso diário, pessoal e de rotina

## Limitações e observações

- O comportamento de identificação de feriados depende dos calendários disponíveis no dispositivo e do nome dos eventos
- Alguns resultados de clima podem variar conforme localização, horário local e disponibilidade da API externa
- O app depende das permissões do sistema para funcionar corretamente em sua totalidade

## Imagens do App

<p align="center">
  <img src="images/1.png" width="250" />
  <img src="images/2.png" width="250" />
  <img src="images/3.png" width="250" />
  <img src="images/4.png" width="250" />
  <img src="images/5.png" width="250" />
  <img src="images/6.png" width="250" />
  <img src="images/7.png" width="250" />
</p>

## Licença

App criado por Arichel dos Santos Moron - Comercialização não autorizada.
