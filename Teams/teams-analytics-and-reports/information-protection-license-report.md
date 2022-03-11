---
title: Microsoft Teams relatório de licença de proteção de informações
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de licença Teams proteção de informações no centro de administração Microsoft Teams para ver como os aplicativos em sua organização estão usando APIs de assinatura de eventos de notificação de alteração.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73ce4b5720c42cdb4e468182d6290912baf95d7e
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435855"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams relatório de licença de proteção de informações


Teams relatório de licença de proteção de informações fornece informações sobre o uso da API das [APIs Graph Microsoft que têm requisitos de licença e pagamento](/graph/teams-licenses). Este relatório destaca todos os aplicativos que estão usando essas APIs [em model=A](/graph/teams-licenses#modela-requirements). Ele não mostra o uso quando as APIs são usadas [no modo model=B](/graph/teams-licenses#modelb-requirements) [ou de avaliação](/graph/teams-licenses#evaluation-mode-default-requirements). 


## <a name="view-the-information-protection-license-report"></a>Exibir o relatório de licença de proteção de informações

Você deve ser um administrador de serviço do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](../using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Na navegação à esquerda do centro de administração Microsoft Teams, selecione **Análise & relatóriosusuário** > . Na guia **Exibir relatórios** , em **Relatório**, selecione **Licença de Proteção de Informações**.
2. Em **Intervalo de datas**, selecione um intervalo.
3. Em **Aplicativos**, selecione um aplicativo e selecione **Executar relatório**.

    ![Captura de tela de lista Teams relatório de licença de proteção de informações no centro de administração Teams com explicações explicativas.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Captura de tela de lista Teams relatório de licença de proteção de informações no centro de administração Teams com explicações explicativas.")

4. Para cada categoria, as métricas sobre usuários com licença, usuários sem licença, capacidade de semente e capacidade utilizada podem ser visualizadas. 

    ![Captura de tela do gráfico de resumo Teams relatório de licença de proteção de informações no centro de administração Teams de notificação de alteração com explicações explicativas.](../media/teams-info-protection-license-report-chart-with-callouts.png "Captura de tela do gráfico de resumo Teams relatório de licença de proteção de informações no centro de administração Teams de notificação de alteração com explicações explicativas.")

5. Os dados podem ser exportados clicando no botão exportar. Os dados da tabela podem ser alternados clicando nas guias para Teams API de notificação de alteração, API de patch Teams, apIs de exportação Teams (chat) e Teams exportar APIs (equipes). 

    ![Captura de tela das diferentes guias do Teams de licença de proteção de informações no centro de administração Teams de guias com explicações explicativas.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "Captura de tela das diferentes guias do Teams de licença de proteção de informações no centro de administração Teams de guias com explicações explicativas.")

    ![Captura de tela da guia de notificação de alteração Teams relatório de licença de proteção de informações no centro de administração Teams com explicações explicativas.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Captura de tela da guia de notificação de alteração Teams relatório de licença de proteção de informações no centro de administração Teams com explicações explicativas.")


## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de licença de proteção de informações pode ser exibido para tendências nos últimos três meses. |
|**2**   |O nome do aplicativo exibirá uma lista de todos os aplicativos que usaram a [API do Microsoft Graph que](/graph/teams-licenses) possui requisitos de licença e pagamento durante o período de tempo selecionado.|
|**3**   |Número de usuários com [licenças válidas](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |Número de usuários que não têm uma licença [válida](/graph/teams-licenses#required-licenses-for-modela).  |
|**5**   |Volume total de chamada da API permitido para um aplicativo além do qual uma taxa de consumo por chamada de API será cobrada para o aplicativo. |
|**6**   |Volume total de chamada da API usado pelo aplicativo para o intervalo de datas determinado. |
|**7**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, em seguida, a guia **Downloads**. Selecione **Baixar** para baixar o relatório quando estiver pronto. Essa exportação exportará somente a guia selecionada no momento.|
|**8**   |Selecione qualquer rótulo específico para mostrar ou ocultar em um gráfico. |
|**9**   |Cada guia exibe o uso de um determinado conjunto de APIs, ou seja, a notificação de [alteração,](/graph/api/resources/webhooks) [a API de exportação](/microsoftteams/export-teams-content) e a API de mensagem [de atualização](/graph/api/message-update). Selecione uma guia para exibir detalhes de uso dessa API. |
|**10**   |**Alterar o uso da API de notificação**<li>**Nome de** exibição - Nome de exibição do usuário no qual uma notificação de alteração foi disparada.</li><li>**Licença Necessária** - Se o usuário tem a licença necessária para enviar com êxito uma notificação de alteração para o aplicativo.</li><li>**Contagem Tentada** - Número total de notificações de alteração que foram disparadas por causa desse usuário.</li><li>**Notificação de Alteração Enviada** - Número total de notificações de alteração que foram enviadas ao aplicativo. Isso será menor do que o total de notificações de alteração disparadas se o usuário não tiver uma licença válida.</li>|
|**11**|**Patch API**<li>**Nome de** exibição - Nome de exibição do usuário em que uma tentativa de atualizar a mensagem foi feita.</li> <li>**Licença Necessária** - Se o usuário tem a licença necessária para que a mensagem seja atualizada com êxito.</li><li>**Contagem Tentada** - Total de tentativas de atualização de mensagens.</li><li>**Mensagem Corrigida** - Total de mensagens que foram atualizadas com êxito.</li>|
|**12**|**Uso da API de Exportação de Chat**<li>**Nome de** exibição - Nome de exibição do usuário em que uma tentativa de exportar a mensagem de chat do usuário foi feita.</li><li>**Licença Necessária** - Se o usuário determinado tem a licença necessária para que a mensagem seja exportada com êxito.</li><li>**Contagem tentada** - Total de tentativas de exportar mensagens de chat.</li><li>**Mensagem Exportada** - Total de tentativas em que a mensagem de chat foi exportada com êxito.</li> |
|**13**|**Uso da API de Exportação de Equipe**<li>**Nome de** exibição - Nome de exibição da equipe em que foi feita uma tentativa de exportar a mensagem da equipe.</li><li>**Contagem Tentada** - Total de tentativas para exportar mensagens de equipe.</li><li>**Mensagem Exportada** - Total de tentativas em que a mensagem de equipe foi exportada com êxito.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados no relatório Teams atividade do usuário anônimo, você precisa ser um administrador global. Isso ocultará informações identificáveis, como nome de exibição, email e ID do Azure AD em relatórios e suas exportações.

1. Na Centro de administração do Microsoft 365, **acesse Configurações** \> **Org Configurações** e, na guia **Serviços**, escolha **Relatórios**.
    
2. Selecione **Relatórios** e escolha Exibir **identificadores anônimos**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365 e no Teams de administração.
  
3. Selecione **Salvar alterações**.