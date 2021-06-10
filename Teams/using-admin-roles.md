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
description: Saiba como usar as funções administrativas para designar administradores que precisam de diferentes níveis de acesso para gerenciar Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8ede97c91254c2dfeace83302c20e310e62be12
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282337"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usar as funções de administrador do Microsoft Teams para gerenciar o Teams

Usando Azure Active Directory (Azure AD), você pode designar administradores que precisam de diferentes níveis de acesso para gerenciar Microsoft Teams. Os administradores podem gerenciar toda a carga de trabalho Teams, ou eles podem ter permissões delegadas para solucionar problemas de qualidade de chamada ou gerenciar as necessidades de telefonia da sua organização.

## <a name="teams-roles-and-capabilities"></a>Teams funções e recursos

Há várias funções de administrador Teams disponíveis: administrador do Teams, administrador de comunicações do Teams, especialista em suporte Teams comunicações, engenheiro de suporte Teams comunicações e administrador de dispositivos Teams. Revise a tabela a seguir para entender o que cada função pode fazer e quais ferramentas o administrador pode usar no centro de administração Microsoft Teams e no PowerShell.

Para acompanhar, você deve ser um administrador. As instruções para obter as permissões estão neste artigo.

<!-- add Global admin role? -->

| Função                                    | Pode fazer essas tarefas                                                           | Pode acessar as ferramentas a seguir                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrador do Teams             | Gerencie o Teams e gerencie e crie Microsoft 365 Grupos.        | Tudo no centro de Microsoft Teams de administração e controles associados do PowerShell, incluindo:<ul><li> Gerencie reuniões, incluindo políticas de reunião, configurações e pontes de conferência. <sup>1,2</sup></li><li>Gerencie voz, incluindo políticas de chamada e inventário e atribuição de números de telefone. <sup>1,3</sup></li><li>Gerenciar mensagens, incluindo políticas de mensagens. <sup>1,2</sup></li><li>Gerencie todas as configurações em toda a organização, incluindo federação, atualização de equipes e configurações de cliente de equipes. <sup>1,2</sup></li><li>Gerencie as equipes na organização e suas configurações associadas, incluindo associação (gerenciamento de grupo suportado por meio do PowerShell, gerenciamento de equipe no Teams de administração). <sup>1,2</sup></li><li>Gerenciar Teams certificados e configurar e atribuir políticas de configuração. <sup>1</sup></li><li>Exibir a página de perfil de usuário e solucionar problemas de qualidade de chamada do usuário usando ferramentas avançadas de solução de problemas. <sup>2</sup> </li><li>Acessar todos os relatórios no Microsoft Teams de administração</li><li> Acessar, monitorar e solucionar problemas de qualidade e confiabilidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários afetados pela qualidade de chamada ruim. Crie novos relatórios de qualidade de chamada, atualize e remova relatórios de qualidade de chamada conforme necessário. Upload atualizar dados de construção do CQD.</li><li> [Publicar aplicativos no catálogo de aplicativos de locatários no Microsoft Teams de administração](manage-apps.md)</li></ul> |
| Administrador de Comunicações de Equipes      | Gerencie recursos de chamada e reuniões no Teams serviço.               | Gerencie reuniões, incluindo políticas de reunião, configurações e pontes de conferência. <sup>1,2</sup><br><br> Gerencie voz, incluindo políticas de chamada e inventário e atribuição de números de telefone. <sup>1,3</sup><br><br> Exibir a página de perfil de usuário e solucionar problemas de qualidade de chamada do usuário usando o toolset de solução de problemas avançado. <sup>2</sup> <br><br> Acessar, monitorar e solucionar problemas de qualidade e confiabilidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários que são afetados pela qualidade de chamada ruim. Crie novos relatórios de qualidade de chamada, atualize e remova relatórios de qualidade de chamada conforme necessário. Upload atualizar dados de construção do CQD.|
| Engenheiro de Suporte de Comunicações de Equipes   | Solucionar problemas de comunicações Teams usando **ferramentas avançadas.** | Exibir a página de perfil de usuário e solucionar problemas de qualidade de chamada do usuário usando ferramentas avançadas de solução de problemas. <sup>2</sup> <br><br> Acessar, monitorar e solucionar problemas de qualidade e confiabilidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários que são afetados pela qualidade de chamada ruim. |
| Teams Especialista em Suporte de Comunicações | Solucionar problemas de comunicações Teams usando **ferramentas básicas.**    | Acesse a página de perfil de usuário para solucionar problemas de chamadas no Call Analytics. Só é possível exibir informações do usuário para o usuário específico que está sendo pesquisado. <sup>2</sup> <br><br> Acessar, monitorar e solucionar problemas de qualidade e confiabilidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD). |
| Teams Administrador de Dispositivos              | Gerenciar dispositivos configurados para uso com o Teams serviço.                    | Gerencie a configuração e as atualizações do dispositivo, revise a saúde do dispositivo e o status dos periféricos conectados, configurar e aplicar perfis de configuração e reiniciar dispositivos.<p>A Teams de Administrador de Dispositivos não fornece acesso a dados de qualidade de chamada ou análise de chamada. Para exibir dados de qualidade de chamada ou análise de chamada, você precisa ter a função de Administrador Teams Comunicações. |

<sup>1</sup> [PowerShell - Microsoft Teams módulo](https://www.powershellgallery.com/packages/MicrosoftTeams/) (a versão pública 1.1.6 ou posterior é integrada ao Skype for Business Online Connector.)<br>
<sup>2</sup> [Microsoft Teams de administração](./manage-teams-skypeforbusiness-admin-center.md)3 Teams conta de administrador deve ter uma licença Teams 
 <sup></sup> válida.
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Para obter mais informações sobre as ferramentas de administração disponíveis para gerenciar Microsoft Teams, consulte [Managing Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md).

Para obter mais informações sobre limites, especificações e outros requisitos que se aplicam ao Teams, consulte Limites e especificações para [Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Atribuir usuários a cada função

Você pode atribuir usuários a essas funções no Azure AD. Para saber como atribuir funções administrativas a um usuário no Azure AD, consulte Atribuir um usuário a funções de [administrador no Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponíveis para cada função

A maioria das ferramentas do PowerShell para essas funções de administrador mora no módulo do Teams PowerShell, e é importante observar que alguns dos cmdlets que essas funções de administrador têm acesso para controlar as configurações compartilhadas que também são usadas para o Skype for Business Online. 

Para exibir a lista completa de cmdlets:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>Tópicos relacionados

- [Microsoft Teams Visão geral do PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)
- [Atribuir proprietários e membros da equipe no Microsoft Teams](./assign-roles-permissions.md)
