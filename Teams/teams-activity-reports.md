---
title: Usar relatórios de atividades do Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Saiba como usar relatórios de atividades para ver como os usuários em sua organização estiver usando Teams da Microsoft.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 202e40439c874aec493b96f8707ff218423d2339
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894348"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Usar relatórios de atividades do Microsoft Teams 
========================================

Você pode usar os relatórios de atividade no Centro de administração do Microsoft 365 para ver como os usuários em sua organização estiver usando Teams da Microsoft. Por exemplo, se alguns não usam o Microsoft Teams ainda, eles podem não saber como começar ou a entender como eles podem usar as equipes sejam mais produtivos e colaborativa. Sua organização pode usar os relatórios de atividades para decidir onde priorizar os esforços de treinamento e comunicação.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Como exibir os relatórios de equipes no painel relatórios

1. No [Centro de administração do Microsoft 365](https://portal.office.com/adminportal/home), selecione **relatórios** > **uso**.
 
2. Na página de **uso** , escolha **Selecionar um relatório**e, em seguida, em **Equipes da Microsoft** na lista de relatórios, escolha o relatório que você deseja exibir.

## <a name="teams-activity-reports-that-are-available"></a>Relatórios de atividade de equipes que estão disponíveis

Atualmente, há dois relatórios de atividade, você pode exibir:

- [Relatório de atividades do usuário do Microsoft Teams](#microsoft-teams-user-activity-report) 
- [Relatório de uso de dispositivos do Microsoft Teams](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário do Microsoft Teams

O relatório de atividades do usuário de equipes proporciona um modo de exibição das atividades mais comuns que os usuários executam em equipes. Isso inclui quantas pessoas participem de uma conversa em um canal, quantos comunicar-se através de mensagens de bate-papo privado e participem quantas chamadas ou reuniões. Você pode ver essas informações para toda a organização, bem como para cada usuário individual.

![Captura de tela do relatório de atividade do usuário de equipes no Centro de administração do Office 365.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar o relatório de atividades do usuário Teams da Microsoft

Você pode obter um modo de exibição em atividade do usuário de equipes, observando os gráficos de **atividade** e **usuários** .

![Captura de tela do relatório de atividade de equipes usuário no Centro de administração do Office 365 com textos explicativos numerados.](media/teams-user-activity-report-with-callouts.png)

|Texto explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividades do usuário de equipes pode ser exibido para tendências nos últimos 7 dias, 30 dias, 90 dias ou 180 dias. No entanto, se você clicar em um intervalo de tempo específico no relatório, a tabela (7) será mostrar dados por 30 dias, até a data (2) quando o relatório foi gerado. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O modo de exibição de **atividade** mostra o número de atividades do Microsoft Teams por tipo de atividade. Os tipos de atividade são o números de mensagens de chat de equipe, mensagens de bate-papo privado, chamadas e reuniões. |
|**4**   |O modo de exibição de **usuários** mostra o número de usuários por tipo de atividade. Os tipos de atividade são o números de mensagens de chat de equipe, mensagens de bate-papo privado, chamadas e reuniões. |
|**5**   |O eixo X nos gráficos é o intervalo de datas selecionado para o relatório específico. <ul><li>No gráfico de **atividade** , o eixo Y é a contagem da atividade especificada.</ul></li> <ul><li>No gráfico de **usuários** , o eixo Y é o número de usuários que participam de chats de equipes, bate-papos privadas, chamadas ou reuniões.</ul></li> |
|**6**   |Você pode filtrar a série que vê no gráfico clicando em um item na legenda. Por exemplo, no gráfico de **atividade** , clique ou toque em **mensagens de canal**, **mensagens de Chat**, **chamadas**ou **reuniões** para ver apenas as informações relacionadas a cada uma delas. Alterar essa opção não altera as informações na tabela de grade. |
|**7**   |A lista de equipes ativas entre o mais larga quadro relatórios tempo (180 dias).  A contagem de atividade irá variar de acordo com a seleção de data. <br><br> Para ver as informações a tabela a seguir, verifique se que você adicionar as colunas na tabela. <ul><li>**Nome de usuário** é o endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo.</ul></li> <ul><li>**Última atividade Data (UTC)** refere-se para a última data em que o usuário participou uma atividade Teams da Microsoft.</ul></li> <ul><li>**Mensagens de canal** é o número de mensagens exclusivos que o usuário postado no chat de uma equipe durante o período de tempo especificado.</ul></li> <ul><li>**Mensagens de chat** é o número de mensagens exclusivos que o usuário lançado em uma privada chat durante o período de tempo especificado.</ul></li> <ul><li>**Chamadas** é o número de chamadas que o usuário participou durante o período de tempo especificado.</ul></li> <ul><li>**Reuniões** é o número de reuniões online que o usuário participou durante o período de tempo especificado.</ul></li> <ul><li>**Outra atividade** é o número de outras atividades de equipe pelo usuário alguns deles incluem e não limitado à: mensagens de preferência, aplicativos, trabalhando em arquivos, pesquisa, estes equipes e canal e favoriting-los.</ul></li> <ul><li>**Deleted** indica se a equipe será excluída. Se a equipe é excluída, mas tinha atividade no período do relatório, ele aparecerá na grade com excluído definido como true.</ul></li> <ul><li>**Deleted data** é a data em que o usuário foi excluído.</ul></li> <ul><li>**Produto atribuído** é a lista de produtos que estão atribuídos ao usuário.</ul></li>Se diretivas da sua organização impede que você exibindo relatórios onde as informações do usuário são identificáveis, você poderá alterar a configuração de privacidade para todos esses relatórios. Confira o **como ocultar a detalhes de nível de usuário?** seção nos [Relatórios de atividades da visualização do Microsoft 365 Admin Center](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Clique ou toque em **colunas** para adicionar ou remover colunas na tabela. |
|**9**   |Clique ou toque em **Exportar** para exportar dados de relatório para um arquivo. csv do Excel. Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se você tiver menos de 2.000 usuários, você pode classificar e filtrar dentro da tabela no relatório em si. Se você tiver mais de 2.000 usuários, você precisará exportar os dados para filtrar e classificar o relatório. 

### <a name="microsoft-teams-device-usage-report"></a>Relatório de uso de dispositivos do Microsoft Teams

O relatório de uso do dispositivo de equipes fornece informações sobre como os usuários se conectam para equipes, incluindo aplicativos móveis. O relatório ajuda a entender quais dispositivos estão populares em sua organização e quantos usuários trabalham em trânsito.

![Captura de tela do relatório de uso de dispositivo de equipes, no Centro de administração do Office 365.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretar o relatório de uso do dispositivo Teams da Microsoft

Você pode obter um modo de exibição para o uso do dispositivo de equipes, observando os gráficos de **usuários** e **distribuição** .

![Captura de tela do relatório de uso de dispositivo de equipes, no Centro de administração do Office 365 com textos explicativos numerados.](media/teams-device-usage-report-with-callouts.png)

|Texto explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de dispositivo equipes pode ser exibido para tendências nos últimos 7 dias, 30 dias, 90 dias ou 180 dias. No entanto, se você clicar em um intervalo de tempo específico no relatório, a tabela (7) será mostrar dados por 30 dias, até a data (2) quando o relatório foi gerado. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O modo de exibição de **usuários** mostra o número de usuários diários por tipo de dispositivo. |
|**4**   |O modo de exibição de **distribuição** mostra o número de usuários por dispositivo durante o período de tempo selecionado.  |
|**5**   | <ul><li>No gráfico de **usuários** , o eixo X é o intervalo de datas selecionado para o relatório e o eixo Y é o número de usuários por tipo de dispositivo.</ul></li> <ul><li>No gráfico de **distribuição** , o eixo X mostra os diferentes dispositivos usados para se conectar ao equipes e do eixo Y é o número de usuários usando o dispositivo.</ul></li> |
|**6**   |Você pode filtrar a série que vê no gráfico clicando em um item na legenda. Por exemplo, no gráfico de **distribuição** , clique ou toque em **Windows**, **Mac**, **Web**, **iOS**ou **Android** para ver apenas as informações relacionadas a cada uma delas. Alterar essa opção não altera as informações na tabela de grade. |
|**7**   |A lista de equipes ativas entre o mais larga quadro relatórios tempo (180 dias).  A contagem de atividade irá variar de acordo com a seleção de data. <br><br> Para ver as informações na tabela a seguir, verifique se que você adicionar as colunas na tabela. <ul><li>**Nome de usuário** é o endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo.</ul></li> <ul><li>**Última atividade Data (UTC)** refere-se para a última data em que o usuário participou uma atividade de equipes.</ul></li> <ul><li>**Deleted** indica se a equipe será excluída. Se a equipe é excluída, mas tinha atividade no período do relatório, ele aparecerá na grade com excluído definido como true.</ul></li><ul><li>**Deleted data** é a data em que o usuário foi excluído.</ul></li> <ul><li>**Windows** é selecionada quando o usuário estava ativo no cliente de desktop do equipes em um computador baseado no Windows.</ul></li> <ul><li>**Mac** é selecionada quando o usuário estava ativo no cliente de desktop do equipes em um computador macOS.</ul></li>  <ul><li>**Web** é selecionada quando o usuário estava ativo no cliente web equipes.</ul></li> <ul><li>**iOS** é selecionada quando o usuário estava ativo no cliente móvel equipes para iOS.</ul></li> <ul><li>**Telefone Android** é selecionada quando o usuário estava ativo no cliente móvel equipes para Android.</ul></li></li> <ui>Se diretivas da sua organização impede que você exibindo relatórios onde as informações do usuário são identificáveis, você poderá alterar a configuração de privacidade para todos esses relatórios. Confira o **como ocultar a detalhes de nível de usuário?** seção nos [Relatórios de atividades da visualização do Microsoft 365 Admin Center](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Clique ou toque em **colunas** para adicionar ou remover colunas na tabela. |
|**9**   |Clique ou toque em **Exportar** para exportar dados de relatório para um arquivo. csv do Excel. Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se você tiver menos de 2.000 usuários, você pode classificar e filtrar dentro da tabela no relatório em si. Se você tiver mais de 2.000 usuários, você precisará exportar os dados para filtrar e classificar o relatório. 

## <a name="who-can-access-the-teams-activity-reports"></a>Quem pode acessar os relatórios de atividade de equipes

Os relatórios de atividade podem ser acessados por usuários que estão atribuídos:

- Função de administrador global do Office 365
- Função de administrador de produtos específicos (Exchange, Skype para negócios ou SharePoint)
- Função do leitor de relatórios

### <a name="reports-reader-role"></a>Função do leitor de relatórios

Você pode atribuir a função de *leitor de relatórios* para a equipe de não-IT que você deseja que tenham acesso a esses relatórios. Atribuindo esta função para gerentes de treinamento ou participantes de negócios, você pode fazer certeza de que eles tenham acesso às ideias que são úteis para a adoção das equipes de unidade e acompanhar.

## <a name="other-information-on-the-reports-dashboard"></a>Outras informações sobre o painel de relatórios

### <a name="at-a-glance-activity-widget"></a>Widget da atividade no instantâneo

O painel de relatórios inclui os dados de uso de equipes em do widget atividade em geral, o que resulta em um modo de exibição entre produtos de como os usuários se comunicar e colaboram através de vários serviços no Office 365.

![Captura de tela do widget equipes atividade em geral no painel de relatórios.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Cartão de atividade de equipes

O cartão de atividade de equipes no painel de relatórios lhe oferece uma visão geral da atividade em equipes, incluindo o número de usuários ativos, de modo que você pode entender rapidamente quantos usuários estão usando o serviço. Clicar em cartão de atividade no painel leva você para o relatório de atividades do usuário de equipes. 

![Captura de tela do cartão de atividade de equipes, no painel de relatórios.](media/teams-activity-card.png)
