---
title: Visão geral do PowerShell equipes
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Saiba como usar os controles do PowerShell para gerenciar Teams da Microsoft.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e85261b133d8f1562bcca7d79f83eb21e345be2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204465"
---
# <a name="teams-powershell-overview"></a>Visão geral do PowerShell equipes

Microsoft Teams tem um rico conjunto de ferramentas para administradores de TI gerenciar o produto através do Centro de administração do Microsoft Teams, controles do PowerShell e APIs do gráfico. Este guia explica como podemos estruturar nossos cmdlets do PowerShell para administradores de TI ser usado e fornece ponteiros a documentação adicional. Observe que as diferentes funções de administrador de equipes têm acesso aos cmdlets diferentes. Para obter mais informações, consulte [equipes da Microsoft que usar funções de administrador para gerenciar equipes](using-admin-roles.md).

## <a name="which-modules-do-you-need-to-use"></a>Quais módulos você precisa usar?

Os controles do PowerShell para gerenciar equipes estão em dois diferentes módulos do PowerShell: 
- [Módulo de PowerShell de equipes da Microsoft](https://www.powershellgallery.com/packages/MicrosoftTeams/) : O PowerShell de equipes módulo contém todos os cmdlets que você precisa criar e gerenciar equipes.  
- [Skype para o módulo de PowerShell corporativos](https://www.microsoft.com/en-us/download/details.aspx?id=39366): O Skype para o módulo de PowerShell Business contém os cmdlets para gerenciar diretivas, configurações e outras ferramentas de equipes. 

A documentação de referência para os controles do PowerShell você saberá qual módulo contiver o cmdlet que você está investigando. (Eventualmente, os dois módulos serão combinados.)

## <a name="what-can-each-admin-role-do"></a>O que cada função de administrador pode fazer?

Leia as [equipes da Microsoft que usar funções de administrador para gerenciar equipes](using-admin-roles.md) para entender quais funções de administrador diferentes de cmdlets do PowerShell poderão aproveitar.

## <a name="creating-and-managing-teams-via-powershell"></a>Criando e gerenciando equipes via PowerShell

Os cmdlets para criar e gerenciar as equipes estão no [módulo de PowerShell de equipes da Microsoft](https://www.powershellgallery.com/packages/MicrosoftTeams/). 

As equipes contam com grupos do O365, portanto quando você criar uma equipe, você cria um grupo. Há um conjunto de cmdlets fornecidos para funcionando com a equipe principal e suas configurações (``new-team``, ``get-team``, ``set-team``), gerenciamento de usuários de equipe (``add-teamuser``, ``remove-teamuser``), bem como os cmdlets para gerenciar os canais da equipe (``new-teamchannel``, ``remove-teamchannel``). Todos esses cmdlets podem ser executados como os usuários finais, mas eles funcionam, somente nas equipes que você possui ou é um membro do. Se você for um Administrador Global ou administrador de serviço de equipes, você poderá agir em todas as equipes em sua organização.

> **GroupId** usados em que o módulo de cmdlets do PowerShell de equipes da Microsoft é o mesmo que a propriedade **Identity** retornada por ``Get-UnifiedGroup`` no módulo de PowerShell do Exchange.

## <a name="managing-policies-via-powershell"></a>Gerenciando políticas via PowerShell

Os cmdlets de gerenciamento de políticas estão no [Skype para o módulo do cmdlet de negócios](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Uma política é um grupo de configurações que podem ser aplicadas de forma granular a usuários individuais. Cada tipo de política tem seu próprio conjunto de cmdlets para criar, exibindo, excluindo e atualizando as próprias diretivas e, em seguida, atribuindo essas políticas a usuários. A estrutura geral é:

- Os comandos GET (por exemplo, ``Get-CsTeamsMeetingPolicy``): retornar os documentos de política que estão disponíveis para atribuir em sua organização, tanto as políticas criadas pela Microsoft para usar como as políticas personalizadas que você criou.
   > Se você quiser encontrar apenas as políticas personalizadas que você criou na sua organização, você poderá usar ``-Filter "tag:*"``.

- NOVOS comandos (por exemplo, ``New-CsTeamsMeetingPolicy``): permitem que você crie novas políticas, em seguida, estão disponíveis para ser atribuídas aos usuários em sua organização para sua organização. Nem todas as políticas oferecem suporte à criação de políticas personalizadas. Geralmente, esse é para garantir que as políticas que você pode usar em sua organização tenham uma combinação com suporte de configurações.

- CONJUNTO de comandos (por exemplo, ``Set-CsTeamsMeetingPolicy``): permite que você defina valores específicos em uma determinada política. Algumas diretivas não tem um conjunto de comandos disponíveis, ou contêm parâmetros que não podem ser personalizados na política. Descrição de cada PowerShell chamará o check-out de quais parâmetros não podem ser personalizados. 
   > Para editar a política que serão por padrão atribuída aos usuários em sua organização que não têm uma política personalizada atribuída, execute ``Set-Cs<PolicyName> -Identity Global``.

- REMOVE comandos (por exemplo, ``Remove-CsTeamsMeetingPolicy``): você pode usar esse cmdlet para excluir uma política personalizada que foi criada em seu locatário. Se você excluir uma política personalizada que tenha sido atribuída a pelo menos um usuário em sua organização, que o usuário se voltará para a política global.
   > É possível remover efetivamente a política global em sua organização, mas se você deseja redefinir a política global em sua organização para as configurações padrão fornecidas pela Microsoft, você poderá executar ``Remove-Cs<PolicyName> -Identity Global``.

- Comando GRANT (por exemplo, ``Grant-CsTeamsMeetingPolicy``): permite atribuir uma política a um usuário específico.
   > Para remover uma atribuição de política personalizada e fazer com que o usuário de fallback para a política padrão na sua organização, execute ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.

> [!TIP]
> Nem todas as políticas permitem políticas personalizadas a ser criado e algumas diretivas de tem configurações que você não pode personalizar (para que você pode exibir a configuração, mas não é possível definir um valor personalizado durante ``set-`` e ``new-``). A documentação do cmdlet específico chamará check-out, se os parâmetros não estão disponíveis para uso por clientes.

Parâmetros comuns:

- **Identidade**: para ``Get-``, ``Set-``, ``New-``, e ``Remove-``, o parâmetro **Identity** sempre fará referência a uma instância de políticas específicas. Para ``Grant``, o parâmetro **Identity** se refere a um objeto de usuário específicos aos quais a política será aplicada.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>Gerenciando configurações por meio do PowerShell

Os cmdlets de gerenciamento de sua configuração estão no [Skype para o módulo do cmdlet de negócios](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

As configurações são partições de memória de configurações mantidas no serviço que não pode ser especificado em um nível de usuário. Configurações sempre se aplicam em toda a organização inteira. A configuração global é a configuração tem efeita apenas em sua organização. Cada tipo de configuração vem com dois cmdlets primários:

- ``Get-Cs<ConfigurationName>``(por exemplo, ``Get-CsTeamsClientConfiguration``): 

- CONJUNTO de comandos (por exemplo, ``Set-CsTeamsClientConfiguration``): definir propriedades na configuração desse tipo. Especifica os parâmetros que você deseja modificar.
   > É possível fazer referência a configuração que você está modificando em uma das duas maneiras: especificando -**Identidade Global**, ou executando por ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``.

## <a name="other-powershell-tools"></a>Outras ferramentas do PowerShell

Você pode encontrar instruções detalhadas sobre como usar todos os controles do PowerShell para gerenciar o Microsoft Teams e Skype para os negócios, incluindo descrições detalhadas sobre as configurações de cada política, na [referência do cmdlet equipes da Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps) e [Skype para Referência do cmdlet de negócios](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>Saiba mais

- [Referência do cmdlet Teams da Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Skype para referência do cmdlet de negócios](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Usar as funções de administrador do Microsoft Teams para gerenciar o Microsoft Teams](using-admin-roles.md)
