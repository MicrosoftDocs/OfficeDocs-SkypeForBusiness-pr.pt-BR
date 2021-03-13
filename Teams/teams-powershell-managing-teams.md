---
title: Gerenciar o Teams com o Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba como gerenciar o Microsoft Teams usando o Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4200c23f6320e67781353e62363d588c230fceb7
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756147"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Gerenciar o Teams com o Microsoft Teams PowerShell

Este artigo mostra como usar o Microsoft Teams PowerShell para gerenciar o Teams e o Skype for Business. 

Use essa orientação em conjunto com a referência [de cmdlet](https://docs.microsoft.com/powershell/teams/?view=teams-ps) do Microsoft Teams e a [referência de cmdlet](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)do Skype for Business.

## <a name="create-and-manage-teams-using-powershell"></a>Criar e gerenciar equipes usando o PowerShell

Os cmdlets para criar e gerenciar equipes estão no módulo [do Microsoft Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

As equipes têm o suporte dos Grupos do Office 365, portanto, quando você cria uma equipe, cria um grupo. Há um conjunto de cmdlets fornecidos para operar na equipe principal e suas configurações ( , , ), gerenciar usuários de equipe ( , ), bem como ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` cmdlets ``new-teamchannel`` para gerenciar os canais da equipe ( , ``remove-teamchannel`` ). Todos esses cmdlets podem ser executados como usuários finais, mas funcionarão apenas nas equipes das que você possui ou são membros. Se você for um Administrador Global ou Administrador de Serviço do Teams, poderá atuar em todas as equipes de sua organização.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> A **GroupId** usada nos cmdlets do módulo do Microsoft Teams PowerShell é a mesma que a **propriedade Identity** retornada no módulo do Exchange ``Get-UnifiedGroup`` PowerShell.

## <a name="manage-policies-via-powershell"></a>Gerenciar políticas por meio do PowerShell

> [!NOTE]
> - O Conector do Skype for Business Online está sendo consolidado no Teams PowerShell. Atualmente, ele está disponível na visualização pública. Com o tempo, os cmdlets do Skype for Business Online que se aplicam ao Teams estarão disponíveis de forma nativa no módulo do Teams PowerShell. As etapas de instalação estão disponíveis no artigo [Instalar o PowerShell do Teams.](teams-powershell-install.md)
>
> - Os cmdlets estarão disponíveis em sua sessão do PowerShell quando você se conectar ao Skype for Business Online. Para obter mais informações, consulte [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Encontre os cmdlets para gerenciar políticas no módulo [de cmdlet](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)do Skype for Business.

Uma política é um grupo de configurações que pode ser aplicado granularmente a usuários individuais. Cada tipo de política tem seu próprio conjunto de cmdlets para criar, exibir, excluir e atualizar as políticas por conta própria e, em seguida, atribuir essas políticas aos usuários. A estrutura geral é:

- **Comandos GET** (por exemplo: retorna os documentos de política disponíveis para você atribuir em sua organização, incluindo as políticas criadas pela Microsoft para você usar, bem como as políticas personalizadas que você ``Get-CsTeamsMeetingPolicy`` criou.
   - Para encontrar apenas as políticas personalizadas que você criou em sua organização, use ``-Filter "tag:*"`` .

- **COMANDOS** NOVOS (por exemplo: cria novas ``New-CsTeamsMeetingPolicy`` políticas para sua organização atribuir aos usuários em sua organização. Nem todas as políticas suportam a criação de políticas personalizadas. Geralmente, isso é para garantir que as políticas que você usa em sua organização tenham uma combinação de configurações com suporte.

- **Comandos SET** (por exemplo: ``Set-CsTeamsMeetingPolicy`` define valores específicos em uma determinada política. Algumas políticas não têm comandos SET disponíveis ou contêm parâmetros que não podem ser personalizados na política. As descrições do PowerShell dizem quais parâmetros não podem ser personalizados. 
   - Para editar a política que será atribuída por padrão aos usuários em sua organização que não têm uma política personalizada atribuída, execute ``Set-Cs<PolicyName> -Identity Global`` .

- **Comandos REMOVE** (por exemplo: exclui uma política ``Remove-CsTeamsMeetingPolicy`` personalizada que foi criada em seu locatário. Se você excluir uma política personalizada atribuída a pelo menos um usuário em sua organização, esse usuário retornará à política global.
   - Você não pode realmente remover a política global em sua organização, mas se quiser redefinir a política global em sua organização para as configurações padrão fornecidas pela Microsoft, execute ``Remove-Cs<PolicyName> -Identity Global`` .

- **Comando GRANT** (por exemplo: ``Grant-CsTeamsMeetingPolicy`` atribui uma política a um usuário específico.
   - Para remover uma atribuição de política personalizada e fazer com que o usuário volte à política padrão em sua organização, execute ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> Nem todas as políticas permitem que políticas personalizadas sejam criadas, e algumas políticas têm configurações que você não pode personalizar (para que você possa exibir a configuração, mas não pode definir um valor personalizado durante ``set-`` e ``new-`` ). A documentação de cada cmdlet chama se os parâmetros estão disponíveis para uso pelos clientes.

Parâmetros comuns:

- **Identidade**: ``Get-`` para , , e , o parâmetro Identity ``Set-`` ``New-`` sempre se ``Remove-`` referirá a uma instância de política específica.  Para ``Grant`` , o parâmetro **Identity** refere-se a um objeto de usuário específico ao qual a política está sendo aplicada.

## <a name="manage-configurations-via-powershell"></a>Gerenciar configurações por meio do PowerShell

Encontre os cmdlets para gerenciar sua configuração no [módulo de cmdlet do Skype for Business.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

As configurações são buckets de configurações mantidas no serviço que não podem ser especificadas em um nível de usuário. As configurações sempre se aplicam em toda a organização. Sua configuração global é a única configuração efetiva em sua organização. Cada tipo de configuração vem com dois cmdlets principais:

- ``Get-Cs<ConfigurationName>`` (por exemplo, ``Get-CsTeamsClientConfiguration`` ):

- Comandos SET (por exemplo: ``Set-CsTeamsClientConfiguration`` definir propriedades na configuração desse tipo. Especifique os parâmetros que você deseja modificar.
   > Você pode fazer referência à configuração que está modificando de duas maneiras: especificando -**Identity Global** ou executando ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>O que cada função de administrador pode fazer?

Leia [Usar funções de administrador do Microsoft Teams para gerenciar](using-admin-roles.md) o Teams para entender quais funções de administrador podem executar cada cmdlet do PowerShell.

## <a name="related-topics"></a>Tópicos relacionados

[Instalando o PowerShell do Teams](teams-powershell-install.md)

[Notas de versão do PowerShell do Teams](teams-powershell-release-notes.md)

[Referência de cmdlet do Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência de cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usar as funções de administrador para gerenciar o Teams](using-admin-roles.md)
