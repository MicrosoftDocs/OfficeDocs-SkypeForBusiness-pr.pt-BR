---
title: Configurar análise de chamada para o Microsoft Teams
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurar a análise de chamada por usuário para identificar e solucionar problemas de qualidade de chamada do Microsoft Teams.
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117129"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurar análise de chamada para o Microsoft Teams

Como administrador do Microsoft Teams, você pode usar a análise de chamada por usuário para solucionar problemas de qualidade de chamada e conexão do Teams para **usuários individuais.** Para aproveitar ao máximo a análise de chamada, de configurar o seguinte:
  
- Atribua funções de suporte especializadas a pessoas, como agentes auxiliares, para permitir que eles exibirem a análise de chamada para usuários. Essas funções de suporte não podem acessar o restante do centro de administração do Teams. 
    
- Adicione informações de construção, site e locatário à análise de chamada por usuário carregando um arquivo de dados .tsv ou .csv.
    
Quando estiver pronto para começar a usar a análise de chamada por usuário, leia [Use per-user call analytics to](use-call-analytics-to-troubleshoot-poor-call-quality.md)troubleshoot poor call quality .
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Dar permissão para suporte e equipe de suporte técnico

Como administrador do Teams, você tem acesso total a informações de análise de chamada para todos os usuários. Criamos algumas funções especializadas do Azure Active Directory que você pode atribuir para dar suporte a funcionários e agentes de assistência técnica para que eles também possam acessar a análise de chamada por usuário (sem ter acesso ao restante do centro de administração do Teams). Atribua a **função de especialista** de suporte de comunicações do Teams aos usuários que devem ter uma visão limitada da análise de chamada por usuário (suporte à Camada 1). Atribua a **função de** engenheiro de suporte de comunicações do Teams aos usuários que precisam de acesso total à análise de chamada por usuário (suporte à Camada 2). Nenhuma função tem acesso ao restante do centro de administração do Teams.

Para saber o que cada uma dessas funções faz, leia O que cada função de Suporte [do Teams faz?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)

Para obter mais informações sobre funções de administrador do Teams, consulte [Use Teams admin roles to manage Teams](using-admin-roles.md). Para saber como atribuir funções de administrador no Azure Active Directory, consulte Exibir e atribuir funções [no Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Para saber como atribuir funções administrativas no Azure Active Directory, consulte Exibir e [atribuir funções no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Carregar um arquivo .tsv ou .csv para adicionar informações de construção, site e locatário

Você pode adicionar informações de construção, site e locatário à análise de chamada por usuário carregando um arquivo .csv ou .tsv. Com todas essas informações, a análise de chamada pode mapear endereços IP para locais físicos. Os administradores e agentes auxiliares podem usar essas informações para ajudar a detectar tendências em problemas de chamada. Por exemplo, por que os usuários no mesmo edifício têm problemas semelhantes de qualidade de chamada? 

Se você for um administrador do Teams ou do Skype for Business, poderá usar um locatário existente e criar um arquivo de dados do Teams ou do Painel de Qualidade de Chamadas do Skype for Business (CQD). Primeiro, você baixa o arquivo do CQD e o carrega para análise de chamada. 

- Para baixar um arquivo de dados existente, vá para o Centro de **administração do Microsoft Teams** Call Quality  >  **Dashboard**  >  **Upload agora**. Na lista **Meus carregamentos,** clique **em Baixar** ao lado do arquivo que você deseja. 

- Para carregar o novo arquivo, vá para o Centro de administração do **Microsoft Teams** Locais e selecione Carregar dados  >  de **local** ou Substituir dados **de local.**
  
Se você estiver criando o arquivo .tsv ou .csv do zero, consulte [Upload tenant and building data](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Usar a análise de chamada por usuário para solucionar problemas de qualidade de chamada ruim](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)