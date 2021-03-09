---
title: Usar as funções de administrador do Microsoft Teams para gerenciar o Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
- seo-marvel-apr2020
ms.reviewer: islubin
description: Saiba como usar as funções administrativas para designar administradores que precisam de diferentes níveis de acesso para gerenciar o Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: feccaa2662189016c721a2bf11629598d90f0501
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558390"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usar as funções de administrador do Microsoft Teams para gerenciar o Teams

Usando o Azure Active Directory (Azure AD), você pode designar administradores que precisam de diferentes níveis de acesso para gerenciar o Microsoft Teams. Os administradores podem gerenciar toda a carga de trabalho do Teams, ou eles podem ter permissões delegadas para solucionar problemas de qualidade de chamada ou gerenciar as necessidades de telefonia da sua organização.

## <a name="teams-roles-and-capabilities"></a>Funções e recursos do Teams

Há várias funções de administrador do Teams disponíveis: administrador de serviço do Teams, administrador de comunicações do Teams, especialista em suporte a comunicações do Teams, engenheiro de suporte de comunicações do Teams e Administrador de Dispositivos do Teams. Revise a tabela a seguir para entender o que cada função pode fazer e quais ferramentas o administrador pode usar no Centro de administração do Microsoft Teams e no PowerShell.

Para acompanhar, você deve ser um administrador. As instruções para obter as permissões estão neste artigo.

<!-- add Global admin role? -->

| Função                                    | Pode fazer essas tarefas                                                           | Pode acessar as ferramentas a seguir                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrador de Serviço do Teams             | Gerencie o serviço do Teams e gerencie e crie Grupos do Microsoft 365.        | Tudo no centro de administração do Microsoft Teams e controles associados do PowerShell, incluindo:<ul><li> Gerencie reuniões, incluindo políticas de reunião, configurações e pontes de conferência. <sup>1,3</sup></li><li>Gerencie voz, incluindo políticas de chamada e inventário e atribuição de números de telefone. <sup>1</sup></li><li>Gerenciar mensagens, incluindo políticas de mensagens. <sup>1,3</sup></li><li>Gerencie todas as configurações em toda a organização, incluindo federação, atualização de equipes e configurações de cliente de equipes. <sup>1,3</sup></li><li>Gerencie as equipes na organização e suas configurações associadas, incluindo associação (gerenciamento de grupo com suporte via PowerShell, gerenciamento de equipe no centro de administração do Teams). <sup>2,3</sup></li><li>Gerenciar dispositivos certificados pelo Teams e configurar e atribuir políticas de configuração. <sup>2</sup></li><li>Exibir a página de perfil de usuário e solucionar problemas de qualidade de chamada do usuário usando ferramentas avançadas de solução de problemas. <sup>3</sup> </li><li>Acessar todos os relatórios no centro de administração do Microsoft Teams</li><li> Acessar, monitorar e solucionar problemas de qualidade e confiabilidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários afetados pela qualidade de chamada ruim. Crie novos relatórios de qualidade de chamada, atualize e remova relatórios de qualidade de chamada conforme necessário. Carregar e atualizar dados de construção do CQD.</li><li> [Publicar aplicativos no catálogo de aplicativos de locatários no centro de administração do Microsoft Teams](manage-apps.md)</li></ul> |
| Administrador de Comunicações de Equipes      | Gerencie recursos de chamada e reuniões no serviço do Teams.               | Gerencie reuniões, incluindo políticas de reunião, configurações e pontes de conferência. <sup>1,3</sup><br><br> Gerencie voz, incluindo políticas de chamada e inventário e atribuição de números de telefone. <sup>1</sup><br><br> Exibir a página de perfil de usuário e solucionar problemas de qualidade de chamada do usuário usando o toolset de solução de problemas avançado. <sup>3</sup> <br><br> Acessar, monitorar e solucionar problemas de qualidade e confiabilidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários que são afetados pela qualidade de chamada ruim. Crie novos relatórios de qualidade de chamada, atualize e remova relatórios de qualidade de chamada conforme necessário. Carregar e atualizar dados de construção do CQD.|
| Engenheiro de Suporte de Comunicações de Equipes   | Solucionar problemas de comunicação no Teams usando **ferramentas avançadas.** | Exibir a página de perfil de usuário e solucionar problemas de qualidade de chamada do usuário usando ferramentas avançadas de solução de problemas. <sup>3</sup> <br><br> Acessar, monitorar e solucionar problemas de qualidade e confiabilidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários que são afetados pela qualidade de chamada ruim. |
| Especialista em Suporte de Comunicações do Teams | Solucionar problemas de comunicação no Teams usando **ferramentas básicas.**    | Acesse a página de perfil de usuário para solucionar problemas de chamadas no Call Analytics. Só pode exibir informações do usuário específico que está sendo pesquisado.<sup>3</sup> <br><br> Acessar, monitorar e solucionar problemas de qualidade e confiabilidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD). |
| Administrador de Dispositivos do Teams              | Gerenciar dispositivos configurados para uso com o serviço do Teams.                    | Gerencie a configuração e as atualizações do dispositivo, revise a saúde do dispositivo e o status dos periféricos conectados, configurar e aplicar perfis de configuração e reiniciar dispositivos.<p>A função Administrador de Dispositivos do Teams não fornece acesso a dados de qualidade de chamada ou análise de chamada. Para exibir dados de qualidade de chamada ou análise de chamada, você precisa ter a função Administrador de Comunicações do Teams. |

<sup>1</sup> [PowerShell - Módulo do Skype for Business](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Módulo do Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3 Centro</sup> [de administração do Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Para obter mais informações sobre as ferramentas de administração disponíveis para gerenciar o Microsoft Teams, consulte [Managing Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

Para obter mais informações sobre limites, especificações e outros requisitos que se aplicam ao Teams, consulte Limites e [especificações do Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Atribuir usuários a cada função

Você pode atribuir usuários a essas funções no Azure AD. Para saber como atribuir funções administrativas a um usuário no Azure AD, consulte Atribuir um usuário a funções de administrador [no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponíveis para cada função

A maioria das ferramentas do PowerShell para essas funções de administrador mora no módulo do Teams PowerShell e é importante observar que alguns dos cmdlets que essas funções de administrador têm acesso para controlar as configurações compartilhadas que também são usadas para o Skype for Business Online. 

Para exibir a lista completa de cmdlets:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Microsoft Teams PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Atribuir proprietários de equipe e membros no Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)
