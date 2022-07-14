---
title: Configurar a análise de chamadas para o Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configure a análise de chamadas por usuário para identificar e solucionar problemas de qualidade de chamadas do Microsoft Teams.
ms.openlocfilehash: bcfe39ccdd9a1a751b49cdc8d0f433e3707635e3
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789936"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurar a análise de chamadas para o Microsoft Teams

Como administrador do Microsoft Teams, você pode usar a análise de chamadas por usuário para solucionar problemas de conexão e qualidade de chamadas do Teams para **usuários individuais**. Para aproveitar ao máximo a análise de chamadas, configure o seguinte:
  
- Atribua funções de suporte especializadas a pessoas, como agentes de assistência técnica, para permitir que elas exibam a análise de chamadas para os usuários. Essas funções de suporte não podem acessar o restante do centro de administração do Teams. 
    
- Adicione informações de criação, site e locatário à análise de chamadas por usuário carregando um arquivo de dados .tsv ou .csv usuário.
    
Quando estiver pronto para começar a usar a análise de chamadas por usuário, leia Usar análise de chamadas por usuário para solucionar problemas [de baixa qualidade de chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Conceder permissão para a equipe de suporte e assistência técnica

Como administrador do Teams, você tem acesso completo às informações de análise de chamada para todos os usuários. Criamos algumas funções especializadas do Azure Active Directory que você pode atribuir à equipe de suporte e agentes de assistência técnica para que eles também possam acessar a análise de chamadas por usuário (sem ter acesso ao restante do centro de administração do Teams). Atribua a **função de especialista** de suporte de comunicações do Teams aos usuários que devem ter uma exibição limitada da análise de chamadas por usuário (suporte à Camada 1). Atribua a **função de** engenheiro de suporte de comunicações do Teams aos usuários que precisam de acesso completo à análise de chamadas por usuário (suporte à Camada 2). Nenhuma das funções tem acesso ao restante do centro de administração do Teams.

Para saber o que cada uma dessas funções faz, leia [O que cada função de Suporte do Teams faz](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Para obter mais informações sobre as funções de administrador do Teams, [consulte Usar funções de administrador do Teams para gerenciar o Teams](using-admin-roles.md). Para saber como atribuir funções de administrador no Azure Active Directory, consulte [Exibir e atribuir funções no Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Para saber como atribuir funções administrativas no Azure Active Directory, consulte [Exibir e atribuir funções no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Carregar um arquivo .tsv ou .csv para adicionar informações de edifício, site e locatário

Você pode adicionar informações de construção, site e locatário à análise de chamadas por usuário carregando um arquivo .csv ou .tsv. Com todas essas informações, a análise de chamadas pode mapear endereços IP para locais físicos. Os administradores e agentes de assistência técnica podem usar essas informações para ajudar a identificar tendências em problemas de chamada. Por exemplo, por que os usuários no mesmo prédio têm problemas semelhantes de qualidade de chamada? 

Se você for um administrador do Teams ou Skype for Business, poderá usar um locatário existente e criar um arquivo de dados do Teams ou Skype for Business CQD (Call Quality Dashboard). Primeiro, baixe o arquivo do CQD e, em seguida, carregue-o para chamar a análise. 

- Para baixar um arquivo de dados existente, vá para o Centro de administração do **Microsoft Teams** > **analytics & relatórios** > **do Upload do Painel** de Qualidade de  > **Chamada agora**. Na lista **Meus uploads** , clique **em Baixar** ao lado do arquivo desejado. 

- Para carregar o novo arquivo, consulte [Adicionar e atualizar rótulos de relatório](/microsoftteams/learn-more-about-site-upload).
  
Se você estiver criando o arquivo .tsv ou .csv do zero, consulte Carregar dados de locatário [e de criação](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Usar a análise de chamadas por usuário para solucionar problemas de baixa qualidade de chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
