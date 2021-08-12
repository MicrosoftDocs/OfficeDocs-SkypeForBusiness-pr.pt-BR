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
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de licença Teams proteção de informações no centro de administração Microsoft Teams para ver como os aplicativos em sua organização estão usando APIs de assinatura de eventos de notificação de alteração.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ea5916cdf2d91a8440f5b674b1dc60ceb29f804dd5b547d1867ffaad69af8d5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308332"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams relatório de licença de proteção de informações

O relatório de licença de proteção de informações [](/graph/api/resources/subscription?view=graph-rest-1.0) do [](/graph/api/resources/webhooks?view=graph-rest-1.0) Teams fornece informações sobre aplicativos que assinaram para alterar eventos de notificação para ouvir mensagens criadas, atualizadas ou excluídas no nível do locatário (ou seja, /teams/getAllMessage ou /chats/getAllMessages). Uma notificação de alteração correspondente à mensagem é enviada com êxito somente quando o usuário tem [a licença necessária](/graph/teams-licenses).  Você pode ver quantas notificações de alteração foram disparadas por um determinado usuário.


## <a name="view-the-information-protection-license-report"></a>Exibir o relatório de licença de proteção de informações

Você deve ser um administrador de serviço do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](../using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Na navegação à esquerda do centro de administração Microsoft Teams, selecione **Análise & relatórios** de  >  **uso.** Na guia **Exibir relatórios,** em **Relatório**, selecione **Licença de Proteção de Informações**.
2. Em **Intervalo de datas,** selecione um intervalo.
3. Em **Aplicativos,** selecione um aplicativo e selecione **Executar relatório**.

    ![Captura de tela do relatório Teams de licença de proteção de informações no centro de administração Teams com callouts](../media/teams-info-protection-license-report-with-callouts.png "Captura de tela do relatório Teams de licença de proteção de informações no centro de administração Teams com callouts")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de licença de proteção de informações pode ser exibido para tendências nos últimos 7, 30 ou 90 dias. |
|**2**   |O nome do aplicativo exibirá uma lista de todos os aplicativos que assinaram para alterar eventos de notificação de mensagens nos últimos n dias, conforme selecionado no intervalo de datas. |
|**3**   |A tabela fornece uma divisão de uso por usuário para o aplicativo selecionado.<ul><li>**Nome para** exibição é o nome de exibição do usuário. Selecione o nome de exibição para ir para a página de detalhes do usuário no centro de Microsoft Teams de administração.</li><li>**Has Required License** is yes if the user has one of the required licenses as defined (here)[ https://docs.microsoft.com/en-us/graph/teams-licenses ]. Se o usuário não tiver a licença necessária, será exibido o _link_ Atribuir licença que navegue até a página de detalhes de licença do usuário no Centro de administração da Microsoft **(** Usuários ativos > nome de usuário  >   selecionado).</li><li>**Eventos Protegidos por Licença** é o número de eventos de notificação de alteração exclusivos enviados ao aplicativo em uma mensagem que foi criada, atualizada ou excluída por esse usuário.</li></ul> |
|**4**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, em seguida, a guia **Downloads.** Selecione **Baixar** para baixar o relatório quando estiver pronto. |
|**5**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione **Exportar para Excel** e, em seguida, a guia **Downloads.** Selecione **Baixar** para baixar o relatório quando estiver pronto. Quando você exibir o relatório no Excel, você também verá uma **coluna de ID** e **email,** que representa a ID do Usuário e o endereço de email do usuário. |

## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados no relatório Teams atividades do usuário anônimos, você precisa ser um administrador global. Isso ocultará informações identificáveis, como nome de exibição, email e ID do Azure AD em relatórios e suas exportações.

1. Na Centro de administração do Microsoft 365, vá para **Configurações** \> **Org Configurações** e, na guia **Serviços,** escolha **Relatórios**.
    
2. Selecione **Relatórios** e escolha Exibir **identificadores anônimos.** Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365 e no Teams de administração.
  
3. Selecione **Salvar alterações**.
