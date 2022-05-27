---
title: Microsoft Teams de licença de proteção de informações
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
description: Saiba como usar o relatório de licença Teams proteção de informações no centro de administração do Microsoft Teams para ver como os aplicativos em sua organização estão usando APIs de assinatura de eventos de notificação de alteração.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fade7b4d5d89061cdc1dd5eb231a80d5ee9e8938
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681532"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams de licença de proteção de informações


Teams de licença de proteção de informações fornece informações de uso da API das [APIs do Microsoft Graph que têm requisitos de licença e pagamento](/graph/teams-licenses). Este relatório destaca todos os aplicativos que estão usando essas APIs em [model=A](/graph/teams-licenses#modela-requirements). Ele não mostra o uso quando as APIs são usadas no [modo model=B](/graph/teams-licenses#modelb-requirements) [ou de avaliação](/graph/teams-licenses#evaluation-mode-default-requirements). 


## <a name="view-the-information-protection-license-report"></a>Exibir o relatório de licença de proteção de informações

Você deve ser um administrador de serviço do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](../using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Na navegação à esquerda do centro de administração Microsoft Teams, selecione **Relatórios de uso** >  &**análise.** Na guia **Exibir relatórios**, em **Relatório**, selecione **Proteção de Informações Licença**.
2. Em **Intervalo de datas**, selecione um intervalo.
3. Em **Aplicativos**, selecione um aplicativo e, em seguida, **selecione Executar relatório**.

    ![Captura de tela da lista suspensa Teams de licença de proteção de informações no Teams de administração com textos explicativo.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Captura de tela da lista suspensa Teams de licença de proteção de informações no Teams de administração com textos explicativo.")

4. Para cada categoria, as métricas sobre usuários com licença, usuários sem licença, capacidade de propagação e capacidade utilizada podem ser exibidas. 

    ![Captura de tela do gráfico de resumo do Teams licença de proteção de informações no centro de administração Teams de notificação de alteração com textos explicativo.](../media/teams-info-protection-license-report-chart-with-callouts.png "Captura de tela do gráfico de resumo do Teams licença de proteção de informações no centro de administração Teams de notificação de alteração com textos explicativo.")

5. Os dados podem ser exportados clicando no botão exportar. Os dados da tabela podem ser alternados clicando nas guias da API de notificação de alteração do Teams, api de patch do Teams, APIs de exportação Teams (chat) e apIs de exportação Teams (equipes). 

    ![Captura de tela das diferentes guias do Teams licença de proteção de informações no Teams de guias com textos explicativo.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "Captura de tela das diferentes guias do Teams licença de proteção de informações no Teams de guias com textos explicativo.")

    ![Captura de tela da guia notificação de alteração Teams relatório de licença de proteção de informações no Teams de administração com textos explicativo.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Captura de tela da guia notificação de alteração Teams relatório de licença de proteção de informações no Teams de administração com textos explicativo.")


## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de licença de proteção de informações pode ser exibido para tendências nos últimos três meses. |
|**2**   |O nome do aplicativo exibirá uma lista de todos os aplicativos que usaram o [Microsoft API do Graph que](/graph/teams-licenses) tem requisitos de licença e pagamento durante o período de tempo selecionado.|
|**3**   |Número de usuários que têm [licenças válidas](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |Número de usuários que não têm uma licença [válida](/graph/teams-licenses#required-licenses-for-modela).  |
|**5**   |Volume total de chamadas à API permitido para um aplicativo além do qual uma taxa de consumo por chamada à API será cobrada para o aplicativo. |
|**6**   |Volume total de chamadas à API usado pelo aplicativo para o intervalo de datas especificado. |
|**7**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, em seguida, a guia **Downloads**. Selecione **Baixar** para baixar o relatório quando ele estiver pronto. Essa exportação exportará apenas a guia selecionada no momento.|
|**8**   |Selecione qualquer rótulo específico para mostrar ou ocultá-lo em um gráfico. |
|**9**   |Cada guia exibe o uso de um determinado conjunto de APIs, ou [seja,](/graph/api/resources/webhooks) notificação de alteração, [API de exportação](/microsoftteams/export-teams-content) e [API de atualização de mensagem](/graph/api/message-update). Selecione uma guia para exibir os detalhes de uso dessa API. |
|**10**   |**Alterar o uso da API de notificação**<li>**Nome de Exibição** – Nome de exibição do usuário no qual uma notificação de alteração foi disparada.</li><li>**Licença necessária** – se o usuário fornecido tem a licença necessária para enviar com êxito uma notificação de alteração para o aplicativo.</li><li>**Tentativa de Contagem** - Número total de notificações de alteração que foram disparadas por causa desse usuário.</li><li>**Notificação de Alteração** Enviada - Número total de notificações de alteração que foram enviadas para o aplicativo. Isso será menor que o total de notificações de alteração disparadas se o usuário não tiver uma licença válida.</li>|
|**11**|**Patch API**<li>**Nome de** Exibição – Nome de exibição do usuário em que foi feita uma tentativa de atualizar a mensagem.</li> <li>**Licença necessária** – se o usuário fornecido tem a licença necessária para que a mensagem seja atualizada com êxito.</li><li>**Tentativa de Contagem** - Total de tentativas de atualização de mensagens.</li><li>**Mensagem Corrigida** - Total de mensagens que foram atualizadas com êxito.</li>|
|**12**|**Uso da API de Exportação de Chat**<li>**Nome de** Exibição – Nome de exibição do usuário em que foi feita uma tentativa de exportar a mensagem de chat do usuário.</li><li>**Licença necessária** – se o usuário fornecido tem a licença necessária para que a mensagem seja exportada com êxito.</li><li>**Tentativa de Contagem** - Total de tentativas de exportar mensagens de chat.</li><li>**Mensagem Exportada** - Total de tentativas em que a mensagem de chat foi exportada com êxito.</li> |
|**13**|**Uso da API de Exportação de Equipe**<li>**Nome de** Exibição – Nome de exibição da equipe em que foi feita uma tentativa de exportar a mensagem da equipe.</li><li>**Tentativa de Contagem** - Total de tentativas para exportar mensagens da equipe.</li><li>**Mensagem Exportada** - Total de tentativas em que a mensagem da equipe foi exportada com êxito.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados no relatório Teams atividade do usuário anônimo, você precisa ser um administrador global. Isso ocultará informações identificáveis, como nome de exibição, email e Azure AD ID em relatórios e suas exportações.

1. No Centro de administração do Microsoft 365, vá  \> para Configurações **Org Configurações** e, na guia Serviços, escolha **Relatórios**.
    
2. Selecione **Relatórios** e escolha Exibir **identificadores anônimos**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365 e no Teams de administração.
  
3. Selecione **Salvar alterações**.