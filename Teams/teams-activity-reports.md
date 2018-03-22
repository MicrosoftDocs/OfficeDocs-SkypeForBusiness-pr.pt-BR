---
title: Usar relatórios de atividade for Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 03/08/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
description: Saiba como usar relatórios de atividades para ver como os usuários em sua organização estiver usando Teams da Microsoft.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14e2bc5964af6bf37988960c2d4626de17805fba
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2018
---
<a name="use-activity-reports-for-microsoft-teams"></a>Usar relatórios de atividade for Microsoft Teams 
========================================

Você pode usar os relatórios de atividades para ver como os usuários em sua organização estiver usando Teams da Microsoft. Por exemplo, se alguns não usam equipes ainda, eles podem não saber como começar ou a entender como eles podem usar as equipes sejam mais produtivos e colaborativa. Sua organização pode usar os relatórios de atividade para decidir onde priorizar os esforços de treinamento e comunicação.

## <a name="how-to-get-to-the-reports-dashboard"></a>Como obter ao painel relatórios

1. No [Centro de administração do Office 365](https://portal.office.com/adminportal/home), selecione **relatórios** > **uso**.
 
2. Na página de **uso** , escolha **Selecionar um relatório** para selecionar de uma lista de relatórios disponíveis. 

## <a name="teams-activity-reports-that-are-available"></a>Relatórios de atividade de equipes que estão disponíveis

Atualmente, há dois relatórios de atividade, você pode exibir:

- Relatório de atividades do usuário Teams da Microsoft 
- Relatório de uso do dispositivo Teams da Microsoft 

### <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário Teams da Microsoft

O relatório de atividades do usuário Teams da Microsoft oferece um modo de exibição das atividades mais comuns que os usuários executam em Microsoft Teams. Isso inclui quantas pessoas participem de uma conversa em um canal, quantos comunicar-se através de mensagens de bate-papo privado e participem quantas chamadas ou reuniões. Você pode ver essa informação tanto no nível de locatário, bem como para cada usuário individual.

![Captura de tela do relatório de atividade do usuário de equipes no Centro de administração do Office 365.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar o relatório de atividades do usuário Teams da Microsoft

Você pode obter um modo de exibição em atividade do usuário Teams Microsoft examinando os gráficos de **atividade** e **usuários** .

![Captura de tela do relatório de atividade de equipes usuário no Centro de administração do Office 365 com textos explicativos numerados.](media/teams-user-activity-report-with-callouts.png)

|Legenda |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividades do usuário Teams da Microsoft pode ser exibido para tendências nos últimos 7 dias, 30 dias, 90 dias ou 180 dias. No entanto, se você clicar em um determinado dia no relatório, a tabela (7) será mostrar dados por 30 dias, até a data (2) quando o relatório foi gerado. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O modo de exibição de **atividade** mostra o número de atividades do Microsoft Teams por tipo de atividade. Os tipos de atividade são o número de equipes de mensagens de chat, mensagens de bate-papo privado, chamadas ou reuniões. |
|**4**   |O modo de exibição de **usuários** mostra o número de usuários por tipo de atividade. Os tipos de atividade são o número de equipes de mensagens de chat, mensagens de bate-papo privado, chamadas ou reuniões. |
|**5**   |O eixo X nos gráficos é o intervalo de datas selecionado para o relatório específico. <ul><li>No gráfico de **atividade** , o eixo Y é a contagem de atividade especificada.</ul></li> <ul><li>No gráfico de **arquivos** , o eixo Y é o número de usuários que participam de chats de equipes, bate-papos privadas, chamadas ou reuniões.</ul></li> |
|**6**   |Você pode filtrar a série que vê no gráfico clicando em um item na legenda. Por exemplo, no gráfico de **atividade** , clique ou toque em **mensagens de canal**, **mensagens de Chat**, **chamadas**ou **reuniões** para ver apenas as informações relacionadas a cada uma delas. Alterar essa opção não altera as informações na tabela de grade. |
|**7**   |A lista de grupos mostrados é determinada pelo conjunto de todos os grupos que existiam (não foram excluídos) entre o mais largo quadro relatórios tempo (180 dias).  A contagem de atividade irá variar de acordo com a seleção de data. <ul><li>**Nome de usuário** é o endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo.</ul></li> <ul><li>**Última atividade Data (UTC)** refere-se para a última data em que o usuário participou uma atividade Teams da Microsoft.</ul></li> <ul><li>**Mensagens de canal** é o número de mensagens exclusivos que o usuário postado no chat de uma equipe durante o período de tempo especificado.</ul></li> <ul><li>**Mensagens de chat** é o número de mensagens exclusivos que o usuário lançado em uma privada chat durante o período de tempo especificado.</ul></li> <ul><li>**Chamadas** é o número de chamadas que o usuário participou durante o período de tempo especificado.</ul></li> <ul><li>**Reuniões** é o número de reuniões online que o usuário participou durante o período de tempo especificado.</ul></li> <ul><li>**Outra atividade** é o número de outras atividades de equipe pelo usuário.</ul></li> <ul><li>**Deleted** indica se a equipe será excluída. Se a equipe é excluída, mas tinha atividade no período do relatório, ele aparecerá na grade com excluído definido como true.</ul></li> <ul><li>**Deleted data** é a data em que a equipe foi excluída.</ul></li> <ul><li>**Produto atribuído** é a lista de produtos que estão atribuídos ao usuário.</ul></li> <ui>**Observação:** Você não pode ver todos os itens na lista abaixo nas colunas até você adicioná-los. </ul><br><br> <ui>Se diretivas da sua organização impede que você exibindo relatórios onde as informações do usuário são identificáveis, você poderá alterar a configuração de privacidade para todos esses relatórios. Confira o **como ocultar a detalhes de nível de usuário?** seção nos [Relatórios de atividade da avaliação do Office 365 Admin Center](https://support.office.com/en-us/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Clique ou toque em **Colunas** para adicionar ou remover colunas do relatório. |
|**9**   |Você também pode exportar os dados do relatório em um arquivo. csv do Excel, clicando ou tocando no link de exportação. Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se você tiver menos de 2.000 usuários, você pode classificar e filtrar dentro da tabela no relatório em si. Se você tiver mais de 2.000 usuários, na ordem para filtrar e classificar, você precisará exportar os dados. |

### <a name="microsoft-teams-device-usage-report"></a>Relatório de uso do dispositivo Teams da Microsoft

O relatório de uso do aplicativo Microsoft Teams fornece informações sobre como os seus usuários se conectam à Teams da Microsoft, incluindo aplicativos móveis. O relatório ajuda a entender quais dispositivos estão populares em sua organização e quantos usuários trabalham em trânsito.

![Captura de tela do relatório de uso de dispositivo de equipes, no Centro de administração do Office 365.](media/teams-device-usage-report.png)

## <a name="who-can-access-the-teams-activity-reports"></a>Quem pode acessar os relatórios de atividade de equipes

Os relatórios de atividade podem ser acessados por usuários que estão atribuídos:

- Função de administrador global do Office 365
- Função de administrador de produtos específicos (Exchange, Skype para negócios ou SharePoint)
- Função do leitor de relatórios

### <a name="reports-reader-role"></a>Função do leitor de relatórios

Você pode atribuir a função de *leitor de relatórios* para a equipe de não-IT que você deseja que tenham acesso a esses relatórios. Atribuindo esta função para gerentes de treinamento ou participantes de negócios, você pode fazer certeza de que eles tenham acesso às ideias que são úteis para a adoção das equipes de unidade e acompanhar.

## <a name="other-information-on-the-reports-dashboard"></a>Outras informações sobre o painel de relatórios

### <a name="at-a-glance-activity-widget"></a>Widget da atividade no instantâneo

O painel de relatórios inclui os dados de uso do Microsoft Teams no widget atividade em geral, que resulta em um modo de exibição entre produtos de como os usuários se comunicar e colaboram através de vários serviços no Office 365.

![Captura de tela do widget equipes atividade em geral no painel de relatórios.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Cartão de atividade de equipes

O painel de relatórios também inclui um novo cartão for Microsoft Teams. O cartão lhe oferece uma visão geral da atividade em equipes, incluindo o número de usuários ativos, de modo que você pode entender rapidamente quantos usuários estão usando o serviço.

![Captura de tela do cartão de atividade de equipes, no painel de relatórios.](media/teams-activity-card.png)
