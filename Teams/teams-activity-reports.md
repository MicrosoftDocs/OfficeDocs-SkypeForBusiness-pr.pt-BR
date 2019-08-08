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
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Saiba como usar relatórios de atividade para ver como os usuários em sua organização estão usando o Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d7346ef19f70366ec32ad6d7a6bcf24fc98e6e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242380"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Usar relatórios de atividades do Microsoft Teams 
========================================

Você pode usar relatórios de atividades no centro de administração do Microsoft 365 para ver como os usuários da sua organização estão usando o Microsoft Teams. Por exemplo, se algumas delas ainda não usam o Microsoft Teams, talvez não saibam como começar ou compreender como elas podem usar o Microsoft Teams para serem mais produtivos e colaborativas. Sua organização pode usar os relatórios de atividades para decidir onde priorizar os esforços de treinamento e comunicação.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Como exibir os relatórios do teams no painel relatórios

1. No [centro de administração do Microsoft 365](https://portal.office.com/adminportal/home), selecione**uso**de **relatórios** > .
 
2. Na página **uso** , escolha **selecionar um relatório**e, em **Microsoft Teams** , na lista de relatórios, escolha o relatório que você deseja exibir.

## <a name="teams-activity-reports-that-are-available"></a>Relatórios de atividades de equipe disponíveis

Atualmente, há dois relatórios de atividades que você pode exibir:

- [Relatório de atividades do usuário do Microsoft Teams](#microsoft-teams-user-activity-report) 
- [Relatório de uso de dispositivos do Microsoft Teams](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Relatório de atividades do usuário do Microsoft Teams

O relatório de atividade de usuários do teams oferece uma visão das atividades mais comuns que os usuários executam no Teams. Isso inclui o número de pessoas que participam de um chat em um canal, o número de comunicação por meio de uma mensagem de chat particular e a quantidade de participantes em chamadas ou reuniões. Você pode ver essas informações para toda a sua organização, bem como para cada usuário individual.

![Captura de tela do relatório atividade do usuário no centro de administração.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar o relatório de atividade do usuário do Microsoft Teams

Você pode obter uma visão da atividade de usuários do teams examinando os gráficos **atividade** e **usuários** .

![Captura de tela do relatório de atividade do usuário com textos explicativos numerados.](media/teams-user-activity-report-with-callouts.png)

|Texto explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de atividade de usuários do teams pode ser visualizado em busca de tendências nos últimos sete dias, 30 dias, 90 dias ou 180 dias. No entanto, se você clicar em um intervalo de tempo específico no relatório, a tabela (7) mostrará os dados por 30 dias até a data (2) para quando o relatório foi gerado. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O modo de exibição **atividade** mostra o número de atividades do Microsoft Teams por tipo de atividade. Os tipos de atividade são o número de mensagens de chat da equipe, mensagens de chat particulares, chamadas e reuniões. |
|**4**   |O modo de exibição **usuários** mostra o número de usuários por tipo de atividade. Os tipos de atividade são o número de mensagens de chat da equipe, mensagens de chat particulares, chamadas e reuniões. |
|**5**   |O eixo X nos gráficos é o intervalo de datas selecionado para o relatório específico. <ul><li>No gráfico **atividade** , o eixo Y é a contagem da atividade especificada.</ul></li> <ul><li>No gráfico **usuários** , o eixo Y é o número de usuários que participam de chats de equipe, chats privados, chamadas ou reuniões.</ul></li> |
|**6**   |Você pode filtrar a série que vê no gráfico clicando em um item na legenda. Por exemplo, no gráfico **atividade** , clique ou toque em **mensagens de canal**, **mensagens de chat**, **chamadas**ou **reuniões** para ver apenas as informações relacionadas a cada uma delas. Alterar essa seleção não altera as informações na tabela de grade. |
|**7**   |A lista de equipes ativas pelo período de tempo de relatório mais largo (180 dias).  A contagem de atividades vai variar de acordo com a seleção de data. <br><br> Para ver as informações a seguir na tabela, certifique-se de adicionar as colunas à tabela. <ul><li>**Nome** de usuário é o endereço de email do usuário. Você pode exibir o endereço de email real ou transformar este campo em anônimo.</ul></li> <ul><li>**Data da última atividade (UTC)** refere-se à última data em que o usuário participou de uma atividade do Microsoft Teams.</ul></li> <ul><li>**Mensagens de canal** é o número de mensagens exclusivas que o usuário publicou em um chat de equipe durante o período de tempo especificado.</ul></li> <ul><li>**Mensagens de chat** é o número de mensagens exclusivas que o usuário publicou em um chat particular durante o período de tempo especificado.</ul></li> <ul><li>**Chamadas** é o número de chamadas que o usuário participou durante o período de tempo especificado.</ul></li> <ul><li>**Reuniões** é o número de reuniões online das quais o usuário participou durante o período de tempo especificado.</ul></li> <ul><li>**Outra atividade** é o número de outras atividades da equipe pelo usuário que incluem, e não se limitam a: mensagens de preferência, aplicativos, trabalho em arquivos, pesquisa, seguir equipes e canal e adicionar-los.</ul></li> <ul><li>**Excluído** indica se a equipe foi excluída. Se a equipe for excluída, mas tiver atividade no período do relatório, ela será mostrada na grade com excluído definido como verdadeiro.</ul></li> <ul><li>**Data de exclusão** é a data em que o usuário foi excluído.</ul></li> <ul><li>**Produto atribuído** é a lista de produtos atribuídos ao usuário.</ul></li>Se as políticas da sua organização impedirem você de exibir relatórios nos quais as informações do usuário sejam identificáveis, você pode alterar a configuração de privacidade de todos esses relatórios. Confira a seção **como faço para ocultar detalhes do nível do usuário?** nos [relatórios de atividades na visualização do centro de administração do Microsoft 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**08**   |Clique ou toque em **colunas** para adicionar ou remover colunas na tabela. |
|**222**   |Clique ou toque em **Exportar** para exportar dados de relatório para um arquivo. csv do Excel. Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se você tiver menos de 2.000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2.000 usuários, será preciso exportar os dados para filtrar e classificar o relatório. 

### <a name="microsoft-teams-device-usage-report"></a>Relatório de uso de dispositivos do Microsoft Teams

O relatório de uso de dispositivos do teams fornece informações sobre como seus usuários se conectam ao Teams, incluindo aplicativos móveis. O relatório ajuda você a entender quais dispositivos são populares em sua organização e quantos usuários trabalham em trânsito.

![Captura de tela do relatório de uso de dispositivos do teams.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpretar o relatório de uso do dispositivo do Microsoft Teams

Você pode obter uma visão do uso do dispositivo do teams examinando os gráficos **usuários** e **distribuição** .

![Captura de tela do relatório de uso de dispositivos do teams com textos explicativos numerados.](media/teams-device-usage-report-with-callouts.png)

|Texto explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de dispositivos do teams pode ser exibido para obter tendências nos últimos sete dias, 30 dias, 90 dias ou 180 dias. No entanto, se você clicar em um intervalo de tempo específico no relatório, a tabela (7) mostrará os dados por 30 dias até a data (2) para quando o relatório foi gerado. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |O modo de exibição **usuários** mostra o número de usuários diários por tipo de dispositivo. |
|**4**   |O modo de exibição de **distribuição** mostra o número de usuários por dispositivo durante o período de tempo selecionado.  |
|**5**   | <ul><li>No gráfico **usuários** , o eixo X é o intervalo de datas selecionado para o relatório e o eixo Y é o número de usuários por tipo de dispositivo.</ul></li> <ul><li>No gráfico de **distribuição** , o eixo X mostra os diferentes dispositivos usados para se conectar ao Teams e o eixo Y é o número de usuários que estão usando o dispositivo.</ul></li> |
|**6**   |Você pode filtrar a série que vê no gráfico clicando em um item na legenda. Por exemplo, no gráfico **de distribuição** , clique ou toque em **Windows**, **Mac**, **Web**, **Ios**ou **Android** para ver apenas as informações relacionadas a cada uma delas. Alterar essa seleção não altera as informações na tabela de grade. |
|**7**   |A lista de equipes ativas pelo período de tempo de relatório mais largo (180 dias).  A contagem de atividades vai variar de acordo com a seleção de data. <br><br> Para ver as informações a seguir na tabela, certifique-se de adicionar as colunas à tabela. <ul><li>**Nome** de usuário é o endereço de email do usuário. Você pode exibir o endereço de email real ou transformar este campo em anônimo.</ul></li> <ul><li>**Data da última atividade (UTC)** refere-se à última data em que o usuário participou de uma atividade de equipe.</ul></li> <ul><li>**Excluído** indica se a equipe foi excluída. Se a equipe for excluída, mas tiver atividade no período do relatório, ela será mostrada na grade com excluído definido como verdadeiro.</ul></li><ul><li>**Data de exclusão** é a data em que o usuário foi excluído.</ul></li> <ul><li>O **Windows** estará selecionado se o usuário estava ativo no cliente da área de trabalho do teams em um computador com Windows.</ul></li> <ul><li>**Mac** estará selecionado se o usuário estava ativo no cliente da área de trabalho do teams em um computador MacOS.</ul></li>  <ul><li>**Web** estará selecionado se o usuário estava ativo no cliente da Web do teams.</ul></li> <ul><li>**Ios** estará selecionado se o usuário estava ativo no cliente móvel do teams para Ios.</ul></li> <ul><li>**Telefone Android** estará selecionado se o usuário estava ativo no cliente do teams Mobile para Android.</ul></li></li> <ui>Se as políticas da sua organização impedirem você de exibir relatórios nos quais as informações do usuário sejam identificáveis, você pode alterar a configuração de privacidade de todos esses relatórios. Confira a seção **como faço para ocultar detalhes do nível do usuário?** nos [relatórios de atividades na visualização do centro de administração do Microsoft 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**08**   |Clique ou toque em **colunas** para adicionar ou remover colunas na tabela. |
|**222**   |Clique ou toque em **Exportar** para exportar dados de relatório para um arquivo. csv do Excel. Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se você tiver menos de 2.000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2.000 usuários, será preciso exportar os dados para filtrar e classificar o relatório. 

## <a name="who-can-access-the-teams-activity-reports"></a>Quem pode acessar os relatórios de atividades da equipe

Os relatórios de atividades podem ser acessados por usuários atribuídos:

- Função de administrador global do Office 365
- Função de administrador específica do produto (Exchange, Skype for Business ou SharePoint)
- Função de leitor de relatórios

### <a name="reports-reader-role"></a>Função de leitor de relatórios

Você pode atribuir a função *leitor de relatórios* a uma equipe que não seja de ti que você deseja que tenha acesso a esses relatórios. Atribuindo esta função a gerentes de treinamento ou stakeholders corporativos, você pode garantir que eles tenham acesso às ideias úteis para direcionar e rastrear a adoção de equipes.

## <a name="other-information-on-the-reports-dashboard"></a>Outras informações sobre o painel relatórios

### <a name="at-a-glance-activity-widget"></a>Widget atividade em resumo

O painel relatórios inclui os dados de uso do teams no widget atividade em resumo, que oferece uma visão de produtos para a maneira como os usuários se comunicam e colaboram usando os vários serviços do Office 365.

![Captura de tela do widget atividade instantânea do teams.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Cartão de atividade do teams

O cartão de atividades do teams no painel Relatórios fornece uma visão geral da atividade no Teams, incluindo o número de usuários ativos, para que você possa entender rapidamente quantos usuários estão usando o serviço. Clicar no cartão de atividade no painel leva você ao relatório de atividades do usuário do teams. 

![Captura de tela do cartão de atividades do teams.](media/teams-activity-card.png)
