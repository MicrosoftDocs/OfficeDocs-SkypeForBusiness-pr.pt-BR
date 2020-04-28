---
title: Visão geral do teams PowerShell
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
description: Saiba como usar os controles do PowerShell para gerenciar o Microsoft Teams, incluindo como os cmdlets do PowerShell são estruturados.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e95b3ab5bdb2b13dbd4c37eca413c865f54fde94
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903036"
---
# <a name="teams-powershell-overview"></a>Visão geral do teams PowerShell

O Microsoft Teams tem um conjunto rico de ferramentas para administradores de ti gerenciar o produto por meio do centro de administração do Microsoft Teams, dos controles do PowerShell e de APIs de gráfico. Este guia explica como estruturamos nossos cmdlets do PowerShell para que os administradores de ti usem e fornecem ponteiros para documentação adicional. Observe que diferentes funções de administrador de equipes têm acesso a cmdlets diferentes. Para obter mais informações, consulte [usar funções de administrador do Microsoft Teams para gerenciar o Microsoft Teams](using-admin-roles.md).

## <a name="which-modules-do-you-need-to-use"></a>Quais módulos você precisa usar?

Os controles do PowerShell para gerenciar equipes estão em dois módulos diferentes do PowerShell: 
- [Módulo do PowerShell do Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) : o módulo do PowerShell do teams contém todos os cmdlets que você precisa para criar e gerenciar equipes.  
- [Módulo do PowerShell do Skype for Business](https://www.microsoft.com/download/details.aspx?id=39366): o módulo do PowerShell do Skype for Business contém os cmdlets para gerenciar políticas, configurações e outras ferramentas de equipe. 

A documentação de referência dos controles do PowerShell informará qual módulo contém o cmdlet que você está investigando. (Eventualmente, os dois módulos serão combinados.)

## <a name="what-can-each-admin-role-do"></a>O que cada função de administrador pode fazer?

Leia [usar funções de administração do Microsoft Teams para gerenciar equipes](using-admin-roles.md) para entender quais cmdlets do PowerShell diferentes funções de administrador poderão aproveitar.

## <a name="creating-and-managing-teams-via-powershell"></a>Criando e gerenciando equipes via PowerShell

Os cmdlets para criar e gerenciar equipes estão no [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). 

As equipes são apoiadas pelos grupos do O365, portanto, quando você cria uma equipe, cria um grupo. Há um conjunto de cmdlets fornecidos para operar na equipe principal e suas configurações (``new-team``, ``get-team``, ``set-team``) gerenciar usuários da equipe (``add-teamuser``, ``remove-teamuser``), bem como cmdlets para gerenciar os canais da equipe (``new-teamchannel``, ``remove-teamchannel``). Todos esses cmdlets podem ser executados como usuários finais, mas só funcionarão nas equipes que você possui ou são membros de. Se você for administrador global ou administrador de serviços do Teams, poderá atuar em todas as equipes da sua organização.

> O **GroupId** usado nos cmdlets do módulo do Microsoft Teams PowerShell é o mesmo **Identity** que a propriedade Identity ``Get-UnifiedGroup`` retornada pelo módulo do PowerShell do Exchange.

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>Diferenças entre a visualização e o módulo do Microsoft Teams PowerShell do Microsoft Teams geralmente disponíveis

Quando lançamos nossa versão geralmente disponível do nosso módulo do PowerShell, alguns cmdlets eram deixados no módulo beta-only, conforme descrito na tabela a seguir.

| Cmdlet | Disponível na visualização | Disponível no 1,0 |
|------- | -------------------- | ------------------------------ |
| Add-TeamUser | Sim | Sim |
| Connect-MicrosoftTeams | Sim | Sim |
| Desconectar-MicrosoftTeams | Sim | Sim |
| Get-Team | Sim | Sim |
| Get-TeamChannel | Sim | Sim |
| Get-TeamFunSettings | Lançamento anterior a 1,0 apenas | Não |
| Get-TeamGuestSettings | Lançamento anterior a 1,0 apenas | Não |
| Get-TeamHelp | Sim | Sim |
| Get-TeamMemberSettings | Lançamento anterior a 1,0 apenas | Não |
| Get-TeamMessagingSettings | Lançamento anterior a 1,0 apenas | Não |
| Get-TeamUser | Sim | Sim |
| New-Team | Sim | Sim |
| New-TeamChannel | Sim | Sim |
| Remover-equipe | Sim | Sim |
| Remove-TeamChannel | Sim | Sim |
| Remove-TeamUser | Sim | Sim |
| Set-Team | Sim | Sim |
| Set-TeamChannel | Sim | Sim |
| Set-TeamFunSettings | Lançamento anterior a 1,0 apenas | Não |
| Set-TeamGuestSettings | Lançamento anterior a 1,0 apenas | Não |
| Set-TeamMemberSettings | Lançamento anterior a 1,0 apenas | Não |
| Set-TeamMessagingSettings | Lançamento anterior a 1,0 apenas | Não |
| Set-TeamPicture | Sim | Não, planejado |


## <a name="managing-policies-via-powershell"></a>Gerenciando políticas pelo PowerShell

Use os cmdlets do [módulo cmdlet do Skype for Business](https://www.microsoft.com/download/details.aspx?id=39366) para gerenciar políticas para usuários individuais.

> [!NOTE]
> Os cmdlets estarão disponíveis na sessão do PowerShell quando você se conectar ao Skype for Business online. Para obter mais informações, consulte [gerenciar o Skype for Business online com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell). 

Uma política é um grupo de configurações que podem ser aplicadas detalhadamente a usuários individuais. Cada tipo de política tem seu próprio conjunto de cmdlets para criar, exibir, excluir e atualizar as políticas propriamente ditas e, em seguida, atribuir essas políticas aos usuários. A estrutura geral é:

- OBTER comandos (por exemplo, ``Get-CsTeamsMeetingPolicy``): retorne os documentos de política que estão disponíveis para você atribuir à sua organização, ambas as políticas criadas pela Microsoft para você usar e as políticas personalizadas que você criou.
   > Se quiser localizar apenas as políticas personalizadas que você criou em sua organização, você pode usar ``-Filter "tag:*"``.

- NOVOS comandos (por exemplo, ``New-CsTeamsMeetingPolicy``): permite que você crie novas políticas para sua organização que estão disponíveis para serem atribuídas aos usuários em sua organização. Nem todas as políticas dão suporte à criação de políticas personalizadas. Geralmente, isso é para garantir que as políticas usadas em sua organização tenham uma combinação de configurações com suporte.

- DEFINIR comandos (por exemplo, ``Set-CsTeamsMeetingPolicy``): permite que você defina valores específicos em uma determinada política. Algumas políticas não têm comandos set disponíveis ou contêm parâmetros que não podem ser personalizados na política. Cada descrição do PowerShell irá chamar quais parâmetros não podem ser personalizados. 
   > Para editar a política que, por padrão, será atribuída aos usuários em sua organização que não tenham uma política personalizada atribuída, executar ``Set-Cs<PolicyName> -Identity Global``.

- REMOVER comandos (por exemplo, ``Remove-CsTeamsMeetingPolicy``): você pode usar esse cmdlet para excluir uma política personalizada que foi criada em seu locatário. Se você excluir uma política personalizada atribuída a pelo menos um usuário em sua organização, esse usuário retornará à política global.
   > Não é possível remover realmente a política global em sua organização, mas se você quiser redefinir a política global em sua organização para as configurações padrão fornecidas pela Microsoft, você pode executar ``Remove-Cs<PolicyName> -Identity Global``.

- Comando conceder (por exemplo, ``Grant-CsTeamsMeetingPolicy``): permite atribuir uma política a um usuário específico.
   > Para remover uma atribuição de política personalizada e fazer com que o usuário retorne à política padrão em sua organização ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``, execute.

> [!TIP]
> Nem todas as políticas permitem a criação de políticas personalizadas, e algumas políticas têm configurações que você não pode personalizar (para que você possa exibir a configuração, mas não pode ``set-`` definir ``new-``um valor personalizado durante e). A documentação do cmdlet específico será chamada se os parâmetros não estiverem disponíveis para uso por clientes.

Parâmetros comuns:

- **Identidade**: para ``Get-``, ``Set-`` ``New-``, e ``Remove-``, o parâmetro **Identity** sempre se refere a uma instância específica de política. Para ``Grant``, o parâmetro **Identity** se refere a um objeto de usuário específico ao qual a política está sendo aplicada.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>Gerenciando configurações pelo PowerShell

Os cmdlets para gerenciar sua configuração estão no [módulo cmdlet do Skype for Business](https://www.microsoft.com/download/details.aspx?id=39366).

As configurações são buckets de configurações mantidas no serviço que não podem ser especificadas em um nível de usuário. As configurações sempre se aplicam em toda a organização. A configuração global é a única configuração efetiva em sua organização. Cada tipo de configuração vem com dois cmdlets principais:

- ``Get-Cs<ConfigurationName>``(por exemplo, ``Get-CsTeamsClientConfiguration``): 

- DEFINIR comandos (por exemplo, ``Set-CsTeamsClientConfiguration``): definir propriedades na configuração desse tipo. Especifique os parâmetros que você deseja modificar.
   > Você pode fazer referência à configuração que está modificando de uma das seguintes maneiras: especificando-**Identity global**ou running ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``.

## <a name="other-powershell-tools"></a>Outras ferramentas do PowerShell

Você pode encontrar instruções detalhadas sobre como usar todos os controles do PowerShell para gerenciar o Microsoft Teams e o Skype for Business, incluindo descrições detalhadas das configurações em cada política, na [referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) e [referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>Saiba mais

- [Referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Usar as funções de administrador do Microsoft Teams para gerenciar o Microsoft Teams](using-admin-roles.md)
