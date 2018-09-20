---
title: Usar funções de administrador do Microsoft Teams para gerenciar equipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
description: Saiba como usar as funções administrativas diferentes para gerenciar equipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 279fed07554589fda4d302b893e5136815963399
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "24025257"
---
# <a name="use-microsoft-teams-admin-roles-to-manage-teams"></a>Usar funções de administrador do Microsoft Teams para gerenciar equipes

Usando o Windows Azure Active Directory (AD Azure), você pode designar os administradores que precisarem diferentes níveis de acesso para gerenciar Teams da Microsoft. Os administradores podem gerenciar a carga de trabalho de equipes toda, ou eles podem ter permissões delegadas para solução de problemas chamar problemas de qualidade ou gerenciando precisa de telefonia da sua organização. 

## <a name="teams-roles-and-capabilities"></a>As equipes de funções e recursos

Há quatro funções de administrador de equipes: administrador de serviço de equipes, administrador de comunicação de equipes, especialista equipes de suporte de comunicações e comunicações de equipes engenheiro de suporte. Analise a tabela a seguir para entender o que cada função pode fazer e quais Ferram o administrador pode usar em equipes e Skype para o Centro de administração de negócios e do PowerShell.

<!-- add Global admin role? -->

| Função | Pode fazer essas tarefas | Pode acessar as seguintes ferramentas |
|----- | ------------------ | ------------------------------ |
| Administrador de serviço de equipes | Gerenciar o serviço Microsoft Teams, gerenciar e criar grupos do Office 365 (Observe que as permissões para gerenciar o Office 365 grupos entram em outubro de 2018) | Tudo no Microsoft Teams & Skype para o Centro de administração de negócios e controles de PowerShell associados, incluindo:<br><br> Gerenciar reuniões, incluindo conferência, configurações e políticas de pontes<sup>1,3</sup> de reunião<br><br> Gerenciar voice, incluindo chamar políticas e de inventário e atribuição número<sup>1</sup> de telefone<br><br> Gerenciar mensagens, incluindo mensagens de políticas<sup>1,3</sup><br><br> Gerenciar todas as configurações de toda a organização, incluindo configurações de cliente equipes<sup>1,3</sup> , equipes de atualização e federação<br><br> Gerenciar as equipes na organização e suas configurações associadas, incluindo associação (estão chegando outubro de 2018) <sup>23</sup><br><br> Exibir a página de perfil de usuário e solucionar problemas de qualidade de chamada do usuário usando de conjunto de ferramentas de solução de problemas avançados<sup>3</sup> |
| Administrador de comunicação de equipes | Gerenciar a chamada e recursos de reuniões dentro do serviço de Teams da Microsoft | Gerenciar reuniões, incluindo conferência, configurações e políticas de pontes<sup>1,3</sup> de reunião<br><br> Gerenciar voice, incluindo chamar políticas e de inventário e atribuição número<sup>1</sup> de telefone<br><br> Exibir a página de perfil de usuário e solucionar problemas de qualidade de chamada do usuário usando de conjunto de ferramentas de solução de problemas avançados<sup>1,3</sup> |
| Engenheiro de suporte de comunicação de equipes | Solucionar problemas de comunicação em equipes usando ferramentas **avançadas** . | Acesso à página de perfil de usuário para solucionar problemas de chamadas na análise de chamada. Pode exibir informações do Registro chamada completa. <sup>3</sup> |
| Especialista de suporte de comunicação de equipes | Solucionar problemas de comunicação dentro de equipes, usando as ferramentas **básicas** .| Acesso à página de perfil de usuário para solucionar problemas de chamadas na análise de chamada. Só pode exibir informações do usuário para o usuário específico que está sendo procurado. <sup>3</sup>

<sup>1</sup> [PowerShell - Skype para o módulo de negócios](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - módulo de equipes da Microsoft](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [equipes da Microsoft e Skype para Business Admin Center](https://docs.microsoft.com/en-us/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Para obter mais informações sobre as ferramentas de administração disponíveis para gerenciamento Teams da Microsoft, consulte [Gerenciando equipes da Microsoft](https://docs.microsoft.com/en-us/microsoftteams/manage-teams-skypeforbusiness-admin-center).

## <a name="assign-users-to-each-role"></a>Atribuir usuários a cada função

Você pode atribuir usuários a essas funções no Windows Azure Active Directory. Para saber como atribuir funções administrativas a um usuário no Active Directory do Windows Azure, consulte [atribuir um usuário para as funções de administrador no Windows Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponíveis para cada função

A maioria das ferramentas do PowerShell para essas funções de administrador live no Skype para o módulo de PowerShell de negócios e é importante observar que alguns dos cmdlets que essas funções de administração tenham acesso ao controle compartilhados configurações que também são utilizadas para Skype para negócios Online. Para exibir a lista completa dos cmdlets disponíveis atualmente para uma determinada função no Skype para o módulo de PowerShell de negócios, siga estas etapas:

1. Atribuir essa função a um usuário (e certifique-se de que o usuário não tem nenhuma outra função).
2. Conecte o Skype para o módulo de PowerShell de negócios:<br>
   a. $session = new-csonlinesession<br>
   b. Import-pssession $session<br>
   c. Use o **Get-Module** para identificar o nome da sessão importado (ele será um nome gerado aleatoriamente).<br>
3. Uso **Get-Command - Module** <*nome acima*> para identificar todos os cmdlets disponíveis

### <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do PowerShell equipes da Microsoft](teams-powershell-overview.md)
- [As equipes da Microsoft PowerShell](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps)
- [Atribuir membros em Microsoft Teams e proprietários de equipe](https://docs.microsoft.com/en-us/microsoftteams/assign-roles-permissions)

