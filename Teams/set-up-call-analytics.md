---
title: Configurar análise de chamada para Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
description: Configurar a análise de chamada por usuário para identificar e solucionar Microsoft Teams problemas de qualidade de chamada.
ms.openlocfilehash: be93a24f7d18e5b347c6375622ca47c3bdaeae26
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556472"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurar análise de chamada para Microsoft Teams

Como administrador Microsoft Teams, você pode usar a análise de chamada por usuário para solucionar problemas de Teams de conexão e qualidade de chamada para **usuários individuais**. Para aproveitar ao máximo a análise de chamada, de configurar o seguinte:
  
- Atribua funções de suporte especializadas a pessoas, como agentes auxiliares, para permitir que eles exibirem a análise de chamada para usuários. Essas funções de suporte não podem acessar o restante do Teams de administração. 
    
- Adicione informações de construção, site e locatário à análise de chamada por usuário carregando um arquivo de dados .tsv ou .csv usuário.
    
Quando estiver pronto para começar a usar a análise de chamada por usuário, leia [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Dar permissão para suporte e equipe de suporte técnico

Como administrador Teams, você tem acesso total às informações de análise de chamada para todos os usuários. Criamos algumas funções de Azure Active Directory que você pode atribuir para dar suporte a funcionários e agentes de assistência técnica para que eles também possam acessar a análise de chamada por usuário (sem ter acesso ao restante do centro de administração do Teams). Atribua a **Teams de** suporte de comunicações a usuários que devem ter uma visão limitada da análise de chamada por usuário (suporte à Camada 1). Atribua a **função Teams de** engenheiro de comunicações a usuários que precisam de acesso total à análise de chamada por usuário (suporte à Camada 2). Nenhuma função tem acesso ao restante do Teams de administração.

Para saber o que cada uma dessas funções faz, leia [O que cada função Teams Suporte faz](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Para obter mais informações sobre Teams funções de administrador, consulte [Use Teams admin roles to manage Teams](using-admin-roles.md). Para saber como atribuir funções de administrador Azure Active Directory, consulte [Exibir e atribuir funções em Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Para saber como atribuir funções administrativas Azure Active Directory, consulte [Exibir e atribuir funções Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Upload um arquivo .tsv ou .csv para adicionar informações de construção, site e locatário

Você pode adicionar informações de construção, site e locatário à análise de chamada por usuário carregando um arquivo .csv ou .tsv. Com todas essas informações, a análise de chamada pode mapear endereços IP para locais físicos. Os administradores e agentes auxiliares podem usar essas informações para ajudar a detectar tendências em problemas de chamada. Por exemplo, por que os usuários no mesmo edifício têm problemas semelhantes de qualidade de chamada? 

Se você for um administrador Teams ou Skype for Business, poderá usar um locatário existente e criar um arquivo de dados a partir do Teams ou do CQD (Painel de Qualidade de Chamada Skype for Business de chamada). Primeiro, você baixa o arquivo do CQD e o carrega para análise de chamada. 

- Para baixar um arquivo de dados existente, vá **Microsoft Teams centro** >  de **administraçãoAnalytics & reportsCall** >  **Quality Dashboard** >  **Upload now**. Na lista **Meus carregamentos** , clique **em Baixar** ao lado do arquivo que você deseja. 

- Para carregar o novo arquivo, consulte [Adicionar e atualizar rótulos de relatório](/microsoftteams/learn-more-about-site-upload).
  
Se você estiver criando o arquivo .tsv ou .csv do zero, [consulte Upload locatário e criando dados](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Usar a análise de chamada por usuário para solucionar problemas de qualidade de chamada ruim](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
