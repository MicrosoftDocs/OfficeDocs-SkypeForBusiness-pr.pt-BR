---
title: Usar as funções de administrador do Microsoft Teams para gerenciar o Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 17a8f6e9475355a5ee0f8960294bf3589d228ed1
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615447"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usar as funções de administrador do Microsoft Teams para gerenciar o Teams

Usando o Azure Active Directory (Azure AD), você pode designar administradores que precisam de diferentes níveis de acesso para gerenciar o Microsoft Teams. Os administradores podem gerenciar toda a carga de trabalho do Teams ou podem ter permissões delegadas para solucionar problemas de qualidade de chamada ou gerenciar as necessidades de telefonia da sua organização.

## <a name="teams-roles-and-capabilities"></a>Funções e funcionalidades do Teams

Há várias funções de administrador do Teams disponíveis: administrador do Teams, administrador de comunicações do Teams, especialista em suporte a comunicações do Teams, engenheiro de suporte de comunicações do Teams e Administrador de Dispositivos do Teams. Examine a tabela a seguir para entender o que cada função pode fazer e quais ferramentas o administrador pode usar no centro de administração do Microsoft Teams e no PowerShell.

> [!NOTE]
> Os Administradores Online do Cliente Skype® for Business podem gerenciar as políticas do aplicativo **Teams** e **Skype for Business Online** pelo PowerShell.

Para acompanhar, você deve ser um administrador. As instruções para obter as permissões estão neste artigo.

<!-- add Global admin role? -->

| Função                                    | Pode realizar essas tarefas                                                           | Pode acessar as ferramentas a seguir                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrador do Teams             | Gerencie o serviço do Teams e gerencie e crie Grupos do Microsoft 365.        | Tudo no centro de administração do Microsoft Teams e nos controles associados do PowerShell, incluindo:<ul><li> Gerencie reuniões, incluindo políticas de reunião, configurações e pontes de conferência. <sup>1,2</sup></li><li>Gerencie voz, incluindo políticas de chamada e inventário e atribuição de números de telefone. <sup>1,3</sup></li><li>Gerenciar mensagens, incluindo políticas de mensagens. <sup>1,2</sup></li><li>Gerencie todas as configurações de toda a organização, incluindo federação, atualização de equipes e configurações de cliente de equipes. <sup>1,2</sup></li><li>Gerencie as equipes na organização e suas configurações associadas, incluindo associação (gerenciamento de grupo com suporte por meio do PowerShell, gerenciamento de equipe no centro de administração do Teams). <sup>1,2</sup></li><li>Gerencie dispositivos certificados pelo Teams e configure e atribua políticas de configuração. <sup>1</sup></li><li>Exiba a página de perfil do usuário e solucione problemas de qualidade de chamada do usuário usando o conjunto de ferramentas de solução de problemas avançada. <sup>2</sup> </li><li>Acessar todos os relatórios no centro de administração do Microsoft Teams</li><li> Acesse, monitore e solucione problemas de confiabilidade e qualidade de chamadas do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários afetados pela baixa qualidade da chamada. Crie novos relatórios de qualidade de chamada, atualize e remova relatórios de qualidade de chamada conforme necessário. Carregar e atualizar dados de compilação do CQD.</li><li> [Publicar aplicativos no catálogo de aplicativos de locatário no Centro de administração do Microsoft Teams](manage-apps.md)</li></ul> |
| Administrador de Comunicações de Equipes      | Gerencie recursos de chamadas e reuniões no serviço do Teams.               | Gerencie reuniões, incluindo políticas de reunião, configurações e pontes de conferência. <sup>1,2</sup><br><br> Gerencie voz, incluindo políticas de chamada e inventário e atribuição de números de telefone. <sup>1,3</sup><br><br> Exiba a página de perfil do usuário e solucione problemas de qualidade de chamada do usuário usando o conjunto de ferramentas de solução de problemas avançado. <sup>2</sup> <br><br> Acesse, monitore e solucione problemas de confiabilidade e qualidade de chamadas do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários que são afetados pela baixa qualidade da chamada. Crie novos relatórios de qualidade de chamada, atualize e remova relatórios de qualidade de chamada conforme necessário. Carregar e atualizar dados de compilação do CQD.|
| Engenheiro de Suporte de Comunicações de Equipes   | Solucionar problemas de comunicação no Teams usando **ferramentas avançadas** . | Exiba a página de perfil do usuário e solucione problemas de qualidade de chamada do usuário usando o conjunto de ferramentas de solução de problemas avançada. <sup>2</sup> <br><br> Acesse, monitore e solucione problemas de confiabilidade e qualidade de chamadas do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários que são afetados pela baixa qualidade da chamada. |
| Especialista em Suporte de Comunicações do Teams | Solucione problemas de comunicação no Teams usando **ferramentas básicas** .    | Acesse a página de perfil do usuário para solucionar problemas de chamadas na Análise de Chamadas. Só é possível exibir informações do usuário para o usuário específico que está sendo pesquisado. <sup>2</sup> <br><br> Acesse, monitore e solucione problemas de confiabilidade e qualidade de chamadas do locatário usando dados expostos no CQD (Painel de Qualidade de Chamadas). |
| Administrador de Dispositivos do Teams              | Gerencie dispositivos configurados para uso com o serviço do Teams.                    | Gerencie a configuração e as atualizações do dispositivo, examine a integridade e o status do dispositivo de periféricos conectados, configure e aplique perfis de configuração e reinicie os dispositivos.<p>A função Administrador de Dispositivos do Teams não fornece acesso a dados de qualidade de chamada ou análise de chamadas. Para exibir dados de qualidade de chamada ou análise de chamadas, você precisa ter a função de Administrador de Comunicações do Teams. |

<sup>1</sup> [PowerShell – módulo do Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) (a versão pública 1.1.6 ou posterior é integrada ao Skype for Business Online Connector.)<br>
<sup>2 Centro</sup> [de administração do](./manage-teams-skypeforbusiness-admin-center.md)
 Microsoft Teams<sup>3 A</sup> conta de administrador do Teams deve ter uma licença válida do Teams.
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Para obter mais informações sobre as ferramentas de administração disponíveis para gerenciar o Microsoft Teams, consulte [Gerenciando o Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md).

Para obter mais informações sobre limites, especificações e outros requisitos que se aplicam ao Teams, consulte Limites e [especificações do Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Atribuir usuários a cada função

Você pode atribuir usuários a essas funções no Azure AD. Para saber como atribuir funções administrativas a um usuário no Azure AD, consulte Atribuir um usuário a funções de administrador [no Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponíveis para cada função

A maioria das ferramentas do PowerShell para essas funções de administrador vive no módulo do PowerShell do Teams e é importante observar que alguns dos cmdlets que essas funções de administrador têm acesso para controlar as configurações compartilhadas que também são usadas para o Skype for Business Online. 

Para exibir a lista completa de cmdlets:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>Artigos relacionados

- [Visão geral do PowerShell do Microsoft Teams](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [Atribuir proprietários e membros da equipe no Microsoft Teams](./assign-roles-permissions.md)
