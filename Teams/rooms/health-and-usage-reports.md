---
title: Relatórios de integridade e uso
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Relatando dados do nó para integridade e uso de relatórios
f1keywords: ''
ms.openlocfilehash: f3c8ceec383d801c5992b0e8275cfe5360ef5bfe
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674813"
---
# <a name="health-and-usage-reports"></a>Relatórios de integridade e uso

O nó de relatório contém dados para a integridade e o uso de suas Salas Gerenciadas da Microsoft e insights de serviço. A **Visão geral** mostra as tendências de integridade de todo o locatário de suas salas. A **guia** Integridade exibe uma lista de salas com seus dados de integridade correspondentes. O uso da sala com base nas informações do calendário e nos dados de qualidade da chamada é visível na **guia** Uso.

## <a name="navigating-reports"></a>Navegando em relatórios

<!--![A screenshot of active tickets bar graph](../media/health-and-usage-002new.png)-->

A seção de visão geral fornece representações gráficas de aspectos importantes do gerenciamento de sala de reunião. Os gráficos serão alterados dependendo do período de tempo selecionado ou do grupo selecionado. Para alterar o período de tempo, clique no menu suspenso.

<!--!![A screenshot of a menu to choose a day](../media/health-and-usage-004.png)-->

Para alterar o grupo, clique no menu suspenso de seleção de grupo na faixa.

<!--!![A screenshot of the banner menu auto-generated](../media/health-and-usage-005.png)-->
### <a name="tickets-by-category"></a>Tíquetes por categoria

A rosca exibe o total de tíquetes gerados para o período e o grupo selecionados (o padrão é sete dias, todos os grupos). Os tíquetes são representados em suas categorias principais: Áudio, Exibição, Periféricos, Conectividade, Controle de Versão e Cliente relatados.

<!--!![A screenshot of pie chart tickets by category](../media/health-and-usage-006.png)-->

Um submenu para a exibição detalhada de tíquetes dessa categoria é exibido quando selecionado.

<!--!![A screenshot of tickets and versioning side by side](../media/health-and-usage-007.png)-->

No submenu, é possível filtrar a lista de tíquetes pela subcategoria selecionando a respectiva parte da rosca. 

<!--!![A screenshot tickets by subcategory automatically generated](../media/health-and-usage-008.png)-->

Para navegar de volta, clique na rosca ou clique na trilha na parte superior esquerda.

Para navegar até um tíquete específico neste modo de exibição de lista, clique no link na coluna **De tíquete de suporte**.

### <a name="ticket-history"></a>Histórico de tíquetes

O gráfico de histórico de tíquetes mostra uma comparação de incidentes atribuídos a você ou à Microsoft durante o período de tempo especificado.

> [!NOTE]
> Se um tíquete mudar de proprietário em um dia, quem possui a tarefa na maior parte do dia terá o tíquete contado para ele. Por exemplo, se você atribuir o tíquete à Microsoft no início do dia, o tíquete conta para **Atribuído à Microsoft** para o dia.

<!--![A screen shot of Tickets history by different periods](../media/health-and-usage-009.png)-->

### <a name="health-history"></a>Histórico de integridade

Esse grafo mostra a integridade média (definição na seção Integridade) para todas as salas no locatário, bem como a integridade média de todos os clientes MMR no dia a dia. Você pode exibir a integridade média por até 90 dias.

<!--!![A screenshot of rooms health and average health](../media/health-and-usage-010.png)-->

### <a name="most-reliableleast-reliable-rooms"></a>Salas mais confiáveis/menos confiáveis

Duas tabelas mostram as salas mais confiáveis e menos confiáveis com base na integridade. Para a exibição de lista completa, selecione Integridade e, em seguida, classifique a lista pela coluna Integridade.

### <a name="rooms-history"></a>Histórico de salas

Fornece uma visão histórica das salas registradas no serviço e fornece uma visão comparativo das salas que foram íntegras ou não monitoradas no mesmo período.

## <a name="health"></a>Saúde

Para navegar até o relatório de integridade de todas as salas, selecione Relatórios e, em seguida,  **selecione Integridade**.

<!--!![A screenshot of a Reports health percentage](../media/health-and-usage-001.png)-->

A pontuação de integridade é uma métrica projetada para exibir salas que provavelmente causam frustração do usuário final. Uma sala pode estar íntegra ou não íntegra por um determinado dia. Ele será considerado não íntegro se um tíquete ou muitos tíquetes afetarem a sala por mais de 20 minutos no total durante o horário de não manutenção (5h às 21h no horário local do computador). Por exemplo, se um tíquete for aberto às 5h, mas fechado às 5h15, a sala ainda será considerada íntegra. Mas, se um segundo tíquete ocorreu das 9h às 9h10, a sala seria considerada não íntegra para o dia. Da mesma forma, se um tíquete ocorreu das 5h às 5h21, ele será considerado não íntegro para o dia.

> [!NOTE]
> A integridade do dia é agregada uma vez por dia às 00:00 UTC. Para clientes próximos à linha de data internacional, a agregação de integridade pode ocorrer próximo ao meio do dia de trabalho.

> [!NOTE]
> As salas que estão sendo integradas estão ocultas para a lista de salas na guia Integridade e não contam para a integridade média do locatário.

Clicar em uma sala listada neste modo de exibição exibe mais detalhes.

O gráfico de barras exibe o número de tíquetes em cada dia. Os tíquetes abertos nesse respectivo dia aparecem em azul. Os tíquetes abertos antes do respectivo dia aparecem em laranja. Clicar em um dia no gráfico filtra o gráfico de pizza e a tabela para os tíquetes relevantes. Para inverter o filtro, navegue com as trilhas ou clique no grafo.

A categorização de tíquetes é representada no gráfico de rosca. Interagir com isso filtra o gráfico de linha do tempo e a tabela. Para inverter o filtro, navegue com as trilhas ou clique no grafo.

<!--!![A screenshot of a Reports health bar graph](../media/health-and-usage-014.png)-->

A exibição de impacto da reunião mostra reuniões agendadas durante as quais um tíquete com uma severidade de "Importante" ou "Crítico" estava aberto. A finalidade desse modo de exibição é fornecer uma aproximação das reuniões em que os participantes podem ter tido problemas.

A exibição de impacto da reunião mostra reuniões agendadas durante as quais um tíquete com uma severidade de "Importante" ou "Crítico" estava aberto. A finalidade desse modo de exibição é fornecer uma aproximação das reuniões em que os participantes podem ter tido problemas.

<!--![A screenshot of a Reports meeting impact](../media/health-and-usage-015.png)-->

A Configurações guia exibe os metadados da sala, como as informações de hardware, as configurações do dispositivo, as informações do BIOS, as configurações do aplicativo e o local.

## <a name="usage"></a>Uso

Para exibir o relatório uso de todas as salas, selecione **Relatórios >Uso**.

<!--!![A screenshot of all rooms' usage by health](../media/health-and-usage-011.png)-->

Os títulos fornecem algumas informações:

- Total de salas em seu locatário
- Quantos não têm reuniões reservadas, offline ou online
- Porcentagem de utilização de salas em todo o locatário
- Número total de reuniões reservadas por meio da troca
- Porcentagem de reuniões reservadas que incluíam um link Skype ou Teams agendado
- Total de chamadas com participação de sala
- Agregar a pontuação de desempenho de chamadas de todas as chamadas classificadas com qualidade "Boa" para todas as chamadas. 

Abaixo das métricas de título está um índice de salas com métricas correspondentes. Selecione uma sala para exibir mais detalhes de uso. As métricas na tabela são descritas na tabela a seguir.

|Coluna|Descrição|
|---|---|
|Utilização|Porcentagem de tempo em que a sala foi reservada durante o horário comercial no período selecionado. Ex. Período de tempo definido como 7 dias. 80% de utilização ao longo dos meios que o quarto foi reservado por 32/40 horas|
|Reservado online|Das reuniões reservadas, a porcentagem das quais foram habilitadas com Teams. Ex. 10 reuniões foram agendadas. Disso, 8 tinham um Teams link. Booked Online = 80%|
|Reuniões agendadas|Número absoluto de reuniões agendadas na sala|
|Total de chamadas|Número absoluto de chamadas com a sala como participante.|
Desempenho da chamada|Porcentagem de chamadas com uma classificação "Boa". Cada chamada é avaliada e recebe uma classificação Boa, Ruim, Desconhecida. Essa métrica é calculada de Boas chamadas/Total de chamadas|

O uso é calculado no final de cada dia à meia-noite (00:00) hora local do dispositivo da sala de reunião. A utilização é calculada com base no tempo total de reunião reservado para esse dia dividido por 8 horas.

## <a name="usage-details-of-a-room"></a>Detalhes de uso de uma sala

Clicar em uma sala no modo de exibição de lista solicita um submenu com informações mais detalhadas. Na guia Utilização do submenu, há um gráfico mostrando as horas de uso dos últimos cinco dias úteis. Para cada dia, há duas barras: azul representa a hora da reunião reservada; roxo representa a hora agendada Teams/Skype reuniões habilitadas. Na parte inferior, as reservas médias de reunião e a duração dos últimos cinco dias úteis são calculadas.

<!--![A screenshot of utilization by hours per day](../media/health-and-usage-012.png)-->

A **tabela** Chamadas mostra reuniões nas quais a sala participou de uma Teams chamada. A Qualidade de Áudio da Sala é avaliada apenas para a sala, não para todos os participantes. Para exibir a qualidade da chamada para todos os participantes de uma chamada específica, selecione uma chamada clicando na Hora de Início.

<!--!![A screenshot of room audio quality](../media/health-and-usage-016.png)-->

Para exibir os detalhes do fluxo da sala, clique na Hora de Início da Sessão.
