---
title: Gerenciar equipes com o Microsoft Teams PowerShell
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
description: Saiba como gerenciar o Microsoft Teams usando o PowerShell do teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09d11b2c697ba57ea161d0ce961cf5ba73794617
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852172"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Gerenciar equipes com o Microsoft Teams PowerShell

Este artigo mostra como usar o Microsoft Teams PowerShell para gerenciar o Microsoft Teams e o Skype for Business. 

Use estas diretrizes em conjunto com a referência do [cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) e [referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="create-and-manage-teams-using-powershell"></a>Criar e gerenciar equipes usando o PowerShell

Os cmdlets para criar e gerenciar equipes estão no [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).

As equipes são apoiadas pelos grupos do Office 365, portanto, quando você cria uma equipe, cria um grupo. Há um conjunto de cmdlets fornecidos para operar na equipe principal e suas configurações ( ``new-team`` , ``get-team`` ,  ``set-team`` ) gerenciar usuários da equipe ( ``add-teamuser`` , ``remove-teamuser`` ), bem como cmdlets para gerenciar os canais da equipe ( ``new-teamchannel`` , ``remove-teamchannel`` ). Todos esses cmdlets podem ser executados como usuários finais, mas só funcionarão nas equipes que você possui ou são membros de. Se você for administrador global ou administrador de serviços do Teams, poderá atuar em todas as equipes da sua organização.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> O **GroupId** usado nos cmdlets do módulo do Microsoft Teams PowerShell é o mesmo que a propriedade **Identity** retornada pelo ``Get-UnifiedGroup`` módulo do PowerShell do Exchange.

## <a name="manage-policies-via-powershell"></a>Gerenciar políticas pelo PowerShell

> [!NOTE]
> - O conector do Skype for Business online está sendo consolidado no PowerShell do teams. No momento, ele está disponível no modo de visualização pública. No momento, os cmdlets do Skype for Business online que se aplicam ao Teams estarão disponíveis nativamente no módulo do PowerShell Teams. As etapas de instalação estão disponíveis no artigo do [PowerShell instalar Teams](teams-powershell-install.md) .
>
> - Os cmdlets estarão disponíveis na sessão do PowerShell quando você se conectar ao Skype for Business online. Para obter mais informações, consulte [gerenciar o Skype for Business online com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Encontre os cmdlets de gerenciamento de políticas no [módulo cmdlet do Skype for Business](https://www.microsoft.com/download/details.aspx?id=39366).

Uma política é um grupo de configurações que podem ser aplicadas detalhadamente a usuários individuais. Cada tipo de política tem seu próprio conjunto de cmdlets para criar, exibir, excluir e atualizar as políticas propriamente ditas e, em seguida, atribuir essas políticas aos usuários. A estrutura geral é:

- **Obter** comandos (por exemplo, ``Get-CsTeamsMeetingPolicy`` ): retorna os documentos de política que estão disponíveis para você atribuir em sua organização, incluindo as políticas criadas pela Microsoft para você usar, bem como as políticas personalizadas que você criou.
   - Para localizar apenas as políticas personalizadas que você criou em sua organização, use ``-Filter "tag:*"`` .

- **Novos** comandos (por exemplo, ``New-CsTeamsMeetingPolicy`` ): cria novas políticas para sua organização atribuir aos usuários em sua organização. Nem todas as políticas dão suporte à criação de políticas personalizadas. Geralmente, isso é para garantir que as políticas usadas em sua organização tenham uma combinação de configurações com suporte.

- **Definir** comandos (por exemplo, ``Set-CsTeamsMeetingPolicy`` ): define determinados valores em uma determinada política. Algumas políticas não têm comandos SET disponíveis ou contêm parâmetros que não podem ser personalizados na política. As descrições do PowerShell mostram quais parâmetros não podem ser personalizados. 
   - Para editar a política que, por padrão, será atribuída aos usuários em sua organização que não tenham uma política personalizada atribuída, executar ``Set-Cs<PolicyName> -Identity Global`` .

- **Remover** comandos (por exemplo, ``Remove-CsTeamsMeetingPolicy`` ): exclui uma política personalizada que foi criada em seu locatário. Se você excluir uma política personalizada atribuída a pelo menos um usuário em sua organização, esse usuário retornará à política global.
   - Na verdade, você não pode remover a política global na sua organização, mas se desejar redefinir a política global em sua organização para as configurações padrão fornecidas pela Microsoft, execute ``Remove-Cs<PolicyName> -Identity Global`` .

- Comando **conceder** (por exemplo, ``Grant-CsTeamsMeetingPolicy`` ): atribui uma política a um usuário específico.
   - Para remover uma atribuição de política personalizada e fazer com que o usuário retorne à política padrão em sua organização, execute ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> Nem todas as políticas permitem a criação de políticas personalizadas, e algumas políticas têm configurações que você não pode personalizar (para que você possa exibir a configuração, mas não pode definir um valor personalizado durante ``set-`` e ``new-`` ). A documentação de cada cmdlet chama se os parâmetros estão disponíveis para serem usados por clientes.

Parâmetros comuns:

- **Identidade** : para ``Get-`` , ``Set-`` , ``New-`` e ``Remove-`` , o parâmetro **Identity** sempre se refere a uma instância específica de política. Para ``Grant`` , o parâmetro **Identity** se refere a um objeto de usuário específico ao qual a política está sendo aplicada.

## <a name="manage-configurations-via-powershell"></a>Gerenciar configurações pelo PowerShell

Encontre os cmdlets para gerenciar sua configuração no [módulo cmdlet do Skype for Business](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

As configurações são buckets de configurações mantidas no serviço que não podem ser especificadas em um nível de usuário. As configurações sempre se aplicam em toda a organização. A configuração global é a única configuração efetiva em sua organização. Cada tipo de configuração vem com dois cmdlets principais:

- ``Get-Cs<ConfigurationName>`` (por exemplo, ``Get-CsTeamsClientConfiguration`` ):

- DEFINIR comandos (por exemplo, ``Set-CsTeamsClientConfiguration`` ): definir propriedades na configuração desse tipo. Especifique os parâmetros que você deseja modificar.
   > Você pode fazer referência à configuração que está modificando de uma das seguintes maneiras: especificando- **Identity global** ou running ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>O que cada função de administrador pode fazer?

Leia [usar funções de administração do Microsoft Teams para gerenciar equipes](using-admin-roles.md) para entender quais funções de administrador podem executar cada cmdlet do PowerShell.

## <a name="related-topics"></a>Tópicos relacionados

[Instalando o Microsoft Teams PowerShell](teams-powershell-install.md)

[Notas de versão do teams PowerShell](teams-powershell-release-notes.md)

[Referência do cmdlet do teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usar as funções de administrador para gerenciar o Teams](using-admin-roles.md)
