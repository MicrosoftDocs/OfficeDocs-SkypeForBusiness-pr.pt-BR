---
title: Configurar a análise de chamada para o Microsoft Teams
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
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581102"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurar a análise de chamada para o Microsoft Teams

Como administrador do Microsoft Teams, você pode usar a análise de chamada por usuário para solucionar problemas de conexão e qualidade de chamada do Teams para **usuários individuais.** Para aproveitar ao máximo a análise de chamada, configurar o seguinte:
  
- Atribua funções especializadas de suporte a pessoas, como agentes de assistência, para permitir que eles vejam a análise de chamada para os usuários. Essas funções de suporte não podem acessar o restante do centro de administração do Teams. 
    
- Adicione informações de edifício, site e locatário à análise de chamada por usuário carregando um arquivo de dados .tsv ou .csv.
    
Quando estiver pronto para começar a usar a análise de chamada por usuário, leia Use a análise de chamada por usuário para solucionar problemas de baixa qualidade [da chamada.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Dar permissão para o suporte e a equipe de suporte técnico

Como administrador do Teams, você tem acesso total às informações de análise de chamada para todos os usuários. Criamos algumas funções especializadas do Azure Active Directory que você pode atribuir à equipe de suporte e agentes de assistência técnica para que eles também possam acessar a análise de chamada por usuário (sem ter acesso ao restante do centro de administração do Teams). Atribua a **função de** especialista de suporte de comunicações do Teams aos usuários que devem ter uma visão limitada da análise de chamada por usuário (suporte de Nível 1). Atribua a **função de** engenheiro de suporte de comunicações do Teams aos usuários que precisam de acesso total à análise de chamada por usuário (suporte de Nível 2). Nenhuma função tem acesso ao restante do centro de administração do Teams.

Para saber o que cada uma dessas funções faz, leia O que cada função de Suporte [do Teams faz?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)

Para saber mais sobre as funções de administrador do Teams, [consulte Usar funções de administrador do Teams para gerenciar o Teams.](using-admin-roles.md) Para saber como atribuir funções de administrador no Azure Active Directory, consulte Exibir e atribuir funções [no Azure Active Directory.](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

Para saber como atribuir funções administrativas no Azure Active Directory, consulte Exibir e atribuir funções [no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Carregar um arquivo .tsv ou .csv para adicionar informações de edifício, site e locatário

Você pode adicionar informações de edifício, site e locatário à análise de chamada por usuário carregando um arquivo .csv ou .tsv. Com todas essas informações, a análise de chamada pode mapear endereços IP para locais físicos. Os administradores e agentes de ajuda podem usar essas informações para ajudar a identificar tendências em problemas de chamada. Por exemplo, por que os usuários no mesmo prédio estão com problemas semelhantes de qualidade de chamada? 

Se você for um administrador do Teams ou do Skype for Business, poderá usar um locatário existente e criar um arquivo de dados do Teams ou do Painel de Qualidade de Chamada do Skype for Business (CQD). Primeiro, baixe o arquivo do CQD e, em seguida, carregue-o para a análise de chamada. 

- Para baixar um arquivo de dados existente, vá para o Carregamento do Painel de Qualidade de Chamada do Centro de administração do **Microsoft**  >    >  Teams. Na lista **Meus carregamentos,** clique **em Baixar** ao lado do arquivo que você deseja. 

- Para carregar o novo arquivo, vá para Locais do Centro de administração do **Microsoft Teams** e selecione Carregar dados de local ou Substituir dados de  >   **localização.** 
  
Se você estiver criando o arquivo .tsv ou .csv do zero, consulte Carregar dados do [locatário e do edifício.](CQD-upload-tenant-building-data.md)
  
## <a name="related-topics"></a>Tópicos relacionados

[Usar a análise de chamada por usuário para solucionar problemas de baixa qualidade de chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
