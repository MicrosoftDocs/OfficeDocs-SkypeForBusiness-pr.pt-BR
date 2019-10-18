---
title: Usar funções de administrador do Microsoft Teams para gerenciar equipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
ms.reviewer: islubin
description: Saiba como usar as diferentes funções administrativas para gerenciar o Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89463b2bc36dc1886fdf595105290d67dcd10d66
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568584"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usar funções de administrador do Microsoft Teams para gerenciar equipes

Usando o Active Directory do Azure (Azure AD), você pode designar administradores que precisam de diferentes níveis de acesso para gerenciar o Microsoft Teams. Os administradores podem gerenciar toda a carga de trabalho da equipe ou podem ter permissões delegadas para solucionar problemas de qualidade da chamada ou gerenciar as necessidades de telefonia da sua organização. 

## <a name="teams-roles-and-capabilities"></a>Funções e recursos do teams

Há quatro funções de administração de equipes disponíveis: administrador de serviços do Teams, administrador de comunicações do Teams, especialista de suporte de comunicações de equipe e engenheiro de suporte de comunicações de equipe. Revise a tabela a seguir para entender o que cada função pode fazer e quais ferramentas o administrador pode usar no centro de administração do Microsoft Teams e no PowerShell.



<!-- add Global admin role? -->

| Função | Pode executar essas tarefas | Pode acessar as seguintes ferramentas |
|----- | ------------------ | ------------------------------ |
| Administrador de Serviço de Equipes | Gerenciar o serviço do Teams e gerenciar e criar grupos do Office 365 | Tudo no centro de administração do Microsoft Teams e controles do PowerShell associados, incluindo:<ul><li> Gerenciar reuniões, incluindo políticas de reunião, configurações e pontes de conferência. <sup>1, 3</sup></li><li>Gerenciar voz, incluindo políticas de chamada e inventário e atribuição de número de telefone. <sup>1</sup></li><li>Gerenciar mensagens, incluindo políticas de mensagens. <sup>1, 3</sup></li><li>Gerenciar todas as configurações da organização, incluindo Federação, atualização do Teams e configuração do cliente do teams. s<sup>1, 3</sup></li><li>Gerencie as equipes na organização e suas configurações associadas, incluindo associação (gerenciamento de grupo compatível pelo PowerShell, gerenciamento de equipe no centro de administração do Teams). <sup>23</sup></li><li>Exiba a página de perfil do usuário e solucione problemas de qualidade das chamadas do usuário usando o conjunto de ferramentas de solução de problemas avançada <sup>3</sup> </li><li> Acesse, monitore e solucione problemas de qualidade e confiabilidade das chamadas do locatário usando dados expostos no painel de qualidade da chamada (CQD) para os usuários afetados por uma qualidade de chamada ruim. Crie novos relatórios, atualize e remova relatórios conforme necessário. Carregar e atualizar os dados de construção do CQD.</li><li> [Publicar aplicativos no catálogo de aplicativos do locatário a partir do cliente da equipe](https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams)</li></ul> |
| Administrador de Comunicações de Equipes | Gerenciar recursos de chamadas e reuniões dentro do serviço Teams. | Gerenciar reuniões, incluindo políticas de reunião, configurações e pontes de conferência. <sup>1, 3</sup><br><br> Gerenciar voz, incluindo políticas de chamada e inventário e atribuição de número de telefone. <sup>1</sup><br><br> Exiba a página de perfil do usuário e solucione problemas de qualidade das chamadas do usuário usando o conjunto de ferramentas de solução de problemas avançada <sup>3</sup> <br><br> Acesse, monitore e solucione problemas com a qualidade e a confiabilidade das chamadas do locatário usando dados expostos no painel de qualidade de chamada (CQD) para os usuários afetados por baixa qualidade de chamadas. Crie novos relatórios, atualize e remova relatórios conforme necessário. Carregar e atualizar os dados de construção do CQD.|
| Engenheiro de Suporte de Comunicações de Equipes | Solucionar problemas de comunicação no Teams usando ferramentas **avançadas** . | Exiba a página de perfil do usuário e solucione problemas de qualidade das chamadas do usuário usando o conjunto de ferramentas de solução de problemas avançada <sup>3</sup> <br><br> Acesse, monitore e solucione problemas com a qualidade e a confiabilidade das chamadas do locatário usando dados expostos no painel de qualidade de chamada (CQD) para os usuários afetados por baixa qualidade de chamadas. |
| Especialista em suporte do teams Communications | Solucionar problemas de comunicação no Teams usando ferramentas **básicas** .| Acessar a página de perfil de usuário para solução de problemas de chamadas no recurso de análise de chamadas. Só pode exibir informações do usuário específico que está sendo pesquisado.<sup>3</sup> <br><br> Acessar, monitorar e solucionar problemas de qualidade de chamada e confiabilidade do locatário usando dados expostos no painel de qualidade da chamada (CQD).  

<sup>1</sup> [PowerShell-módulo Skype for Business](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell-módulo do Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [centro de administração do Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Para obter mais informações sobre as ferramentas de administração disponíveis para gerenciar o Microsoft Teams, consulte [Gerenciando o Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

Para obter mais informações sobre limites, especificações e outros requisitos que se aplicam ao Teams, consulte [limites e especificações do Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Atribuir usuários a cada função

Você pode atribuir usuários a essas funções no Azure AD. Para saber como atribuir funções administrativas a um usuário no Azure AD, consulte [atribuir funções de usuário às funções de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponíveis para cada função

A maioria das ferramentas do PowerShell para essas funções de administração residem no módulo do PowerShell do Skype for Business, e é importante observar que alguns cmdlets que essas funções de administrador têm acesso para controlar as configurações compartilhadas que também são usadas para o Skype for Business online. A função de administrador do Skype for Business também tem acesso a todos os cmdlets do módulo PowerShell do Skype for Business.

Para ver a lista completa de cmdlets disponíveis atualmente para uma determinada função no módulo do PowerShell do Skype for Business, siga estas etapas:

1. Atribua essa função a um usuário (e certifique-se de que o usuário não tenha outras funções).
2. Conecte-se ao módulo do PowerShell do Skype for Business:<br>
   a. $session = New-csonlinesession<br>
   b. Importar-pssession $session<br>
   c. Use **Get-Module** para identificar o nome da sessão importada (será um nome gerado aleatoriamente).<br>
3. Use o **Get-Command-module** <*Name do> acima* para identificar todos os cmdlets disponíveis

### <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Microsoft Teams PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Atribuir proprietários de equipe e membros no Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

