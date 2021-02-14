---
title: Usar funções de administrador do Microsoft Teams para gerenciar o Teams
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
ms.openlocfilehash: 637d6e63b0eabdc9517e8d5cd5986ae7661ad118
ms.sourcegitcommit: 032a22c8b61456dcbd798ec390f0ae1ca7d8eda0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357609"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usar funções de administrador do Microsoft Teams para gerenciar o Teams

Usando o Azure Active Directory (Azure AD), você pode designar administradores que precisam de diferentes níveis de acesso para gerenciar o Microsoft Teams. Os administradores podem gerenciar toda a carga de trabalho do Teams ou podem ter permissões delegadas para solucionar problemas de qualidade de chamada ou gerenciar as necessidades de telefonia da sua organização.

## <a name="teams-roles-and-capabilities"></a>Funções e recursos do Teams

Há várias funções de administrador do Teams disponíveis: administrador de serviços do Teams, administrador de comunicações do Teams, especialista de suporte de comunicações do Teams, engenheiro de suporte de comunicações do Teams e Administrador de Dispositivo do Teams. Revise a tabela a seguir para entender o que cada função pode fazer e quais ferramentas o administrador pode usar no Centro de administração do Microsoft Teams e no PowerShell.

Para acompanhar, você deve ser um administrador. As instruções para obter as permissões estão neste artigo.

<!-- add Global admin role? -->

| Função                                    | Pode realizar essas tarefas                                                           | Pode acessar as ferramentas a seguir                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrador de Serviço do Teams             | Gerencie o serviço do Teams e gerencie e crie Grupos do Microsoft 365.        | Tudo no Centro de administração do Microsoft Teams e controles do PowerShell associados, incluindo:<ul><li> Gerencie reuniões, incluindo políticas de reunião, configurações e pontes de conferência. <sup>1,3</sup></li><li>Gerencie voz, incluindo políticas de chamada, inventário e atribuição de números de telefone. <sup>1</sup></li><li>Gerencie mensagens, incluindo políticas de mensagens. <sup>1,3</sup></li><li>Gerencie todas as configurações de toda a organização, incluindo a federação, a atualização das equipes e as configurações do cliente de equipes. <sup>1,3</sup></li><li>Gerencie as equipes na organização e suas configurações associadas, incluindo associação (gerenciamento de grupo com suporte por meio do PowerShell, gerenciamento de equipe no centro de administração do Teams). <sup>2,3</sup></li><li>Gerencie dispositivos certificados pelo Teams e configurar e atribuir políticas de configuração. <sup>2</sup></li><li>Veja a página de perfil do usuário e solucione problemas de qualidade de chamada do usuário usando ferramentas avançadas de solução de problemas. <sup>3</sup> </li><li>Acessar todos os relatórios no Centro de administração do Microsoft Teams</li><li> Acesse, monitore e solucione problemas de confiabilidade e qualidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários afetados pela baixa qualidade da chamada. Crie novos relatórios de qualidade de chamada, atualize e remova relatórios de qualidade de chamada conforme necessário. Carregar e atualizar dados de construção do CQD.</li><li> [Publicar aplicativos no catálogo de aplicativos do locatário no Centro de administração do Microsoft Teams](manage-apps.md)</li></ul> |
| Administrador de Comunicações de Equipes      | Gerencie os recursos de chamada e reuniões dentro do serviço do Teams.               | Gerencie reuniões, incluindo políticas de reunião, configurações e pontes de conferência. <sup>1,3</sup><br><br> Gerencie voz, incluindo políticas de chamada, inventário e atribuição de números de telefone. <sup>1</sup><br><br> Veja a página de perfil do usuário e solucione problemas de qualidade de chamada do usuário usando o aplicativo avançado de ferramentas de solução de problemas. <sup>3</sup> <br><br> Acesse, monitore e solucione problemas de confiabilidade e qualidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários que são afetados pela baixa qualidade da chamada. Crie novos relatórios de qualidade de chamada, atualize e remova relatórios de qualidade de chamada conforme necessário. Carregar e atualizar dados de construção do CQD.|
| Engenheiro de Suporte de Comunicações de Equipes   | Solucione problemas de comunicação no Teams usando **ferramentas avançadas.** | Veja a página de perfil do usuário e solucione problemas de qualidade de chamada do usuário usando ferramentas avançadas de solução de problemas. <sup>3</sup> <br><br> Acesse, monitore e solucione problemas de confiabilidade e qualidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD) para os usuários que são afetados pela baixa qualidade da chamada. |
| Especialista em Suporte de Comunicações do Teams | Solucione problemas de comunicação no Teams usando **ferramentas básicas.**    | Acesse a página de perfil do usuário para solucionar problemas de chamadas no Recurso de Análise de Chamadas. Só pode exibir informações do usuário específico que está sendo pesquisado.<sup>3</sup> <br><br> Acesse, monitore e solucione problemas de confiabilidade e qualidade de chamada do locatário usando dados expostos no Painel de Qualidade de Chamada (CQD). |
| Administrador de Dispositivo do Teams              | Gerencie dispositivos configurados para uso com o serviço do Teams.                    | Gerencie as atualizações e a configuração do dispositivo, revise a saúde do dispositivo e o status dos periféricos conectados, configurar e aplicar perfis de configuração e reiniciar dispositivos.<p>A função Administrador de Dispositivo do Teams não fornece acesso a dados de qualidade de chamada ou análise de chamada. Para exibir dados de qualidade de chamada ou análise de chamada, você precisa ter a função de Administrador de Comunicações do Teams. |

<sup>1</sup> [PowerShell – módulo do Skype for Business](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell – módulo do Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3 Centro</sup> [de administração do Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Para obter mais informações sobre as ferramentas de administração disponíveis para gerenciar o Microsoft Teams, consulte [Gerenciando o Microsoft Teams.](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)

Para obter mais informações sobre limites, especificações e outros requisitos que se aplicam ao Teams, consulte Limites e [especificações do Microsoft Teams.](limits-specifications-teams.md)

## <a name="assign-users-to-each-role"></a>Atribuir usuários a cada função

Você pode atribuir usuários a essas funções no Azure AD. Para saber como atribuir funções administrativas a um usuário no Azure AD, consulte Atribuir um usuário a funções de administrador [no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponíveis para cada função

A maioria das ferramentas do PowerShell para essas funções de administrador mora no módulo do PowerShell do Skype for Business e é importante observar que alguns dos cmdlets que essas funções de administrador têm acesso para controlar as configurações compartilhadas que também são usadas para o Skype for Business Online. A função de administrador do Skype for Business também tem acesso a todos os cmdlets no módulo Do PowerShell do Skype for Business.

Para exibir a lista completa de cmdlets atualmente disponíveis para uma determinada função no módulo Do PowerShell do Skype for Business, siga estas etapas:

1. Atribua essa função a um usuário (e certifique-se de que o usuário não tenha outras funções).
2. Conecte-se ao módulo do PowerShell do Skype for Business:<br>
   a. $session = nova-csonlinesession<br>
   b. Importar-pssession $session<br>
   c. Use **o Get-Module** para identificar o nome da sessão importada (será um nome gerado aleatoriamente).<br>
3. Use **o nome get-command -module**  < *de cima*> para identificar todos os cmdlets disponíveis

### <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Microsoft Teams PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Atribuir proprietários de equipe e membros no Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

