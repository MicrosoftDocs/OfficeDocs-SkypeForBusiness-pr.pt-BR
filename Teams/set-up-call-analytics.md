---
title: Configurar a análise de chamadas do Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurar a análise de chamadas por usuário para identificar e solucionar problemas de qualidade de chamada do Microsoft Teams.
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085307"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurar a análise de chamadas do Microsoft Teams

Como administrador do Microsoft Teams, você pode usar a análise de chamadas por usuário para solucionar problemas com a qualidade das chamadas e problemas de conexão para **usuários individuais**. Para aproveitar ao máximo a análise de chamadas, configure o seguinte:
  
- Atribua funções de suporte especializadas a pessoas, como agentes de assistência técnica, para permitir que eles vejam a análise de chamadas para os usuários. Essas funções de suporte não podem acessar o restante do centro de administração do teams. 
    
- Adicione informações de construção, site e locatário às análises de chamadas por usuário carregando um arquivo de dados. tsv ou. csv.
    
Quando estiver pronto para começar a usar a análise de chamadas por usuário, leia [usar a análise de chamadas por usuário para solucionar problemas de qualidade de chamada de baixa qualidade](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Conceder permissão para a equipe de suporte e helpdesk

Como administrador do Teams, você tem acesso completo para fazer chamadas para a análise de todos os usuários. Criamos algumas funções especializadas do Azure Active Directory que você pode atribuir à equipe de suporte e aos agentes de helpdesk para que elas também possam acessar a análise de chamadas por usuário (sem ter acesso ao resto do centro de administração do Teams). Atribua a função de **especialista de comunicações do teams** a usuários que devem ter um modo de exibição limitado de análise de chamadas por usuário (suporte de camada 1). Atribua a função de **engenheiro de suporte de comunicações ao Teams** a usuários que precisam de acesso completo a análises de chamadas por usuário (suporte a nível 2). Nenhuma função tem acesso ao restante do centro de administração do teams.

Para saber o que cada uma dessas funções faz, leia [o que faz cada função de suporte do teams](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Para obter mais informações sobre as funções de administração do Teams, consulte [usar funções de administração do teams para gerenciar o Teams](using-admin-roles.md). Para saber como atribuir funções de administrador no Azure Active Directory, consulte [Exibir e atribuir funções no Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Para saber como atribuir funções administrativas no Azure Active Directory, consulte [Exibir e atribuir funções no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Carregar um arquivo. tsv ou. csv para adicionar informações de criação, site e locatário

Você pode adicionar informações de construção, site e locatário a análises de chamadas por usuário carregando um arquivo. csv ou. TSV. Com todas essas informações, a análise de chamadas pode mapear endereços IP para locais físicos. Os agentes de administradores e helpdesks podem usar essas informações para ajudar a identificar tendências em problemas com chamadas. Por exemplo, por que os usuários na mesma criação têm problemas de qualidade de chamada semelhantes? 

Se você for um administrador do teams ou do Skype for Business, poderá usar um locatário existente e construir um arquivo de dados do teams ou do painel de qualidade de chamada do Skype for Business (CQD). Primeiro, baixe o arquivo do CQD e carregue-o para a análise de chamadas. 

- Para baixar um arquivo de dados existente, acesse o painel de qualidade de chamada **do centro de administração do Microsoft Teams**  >  **Call Quality Dashboard**  >  **agora**. Na lista **meus uploads** , clique em **baixar** ao lado do arquivo desejado. 

- Para carregar o novo arquivo, vá para locais do **centro de administração do Microsoft Teams**  >  **Locations**e, em seguida, selecione **carregar dados de localização** ou **substituir dados de localização**.
  
Se você estiver criando o arquivo. tsv ou. csv do zero, consulte [carregar dados do locatário e construção de dados](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Use a análise de chamadas por usuário para solucionar problemas de qualidade de chamadas ruins](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
