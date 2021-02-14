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
description: Saiba como gerenciar o Microsoft Teams usando o Teams PowerShell.
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

Este artigo mostra como usar o Microsoft Teams PowerShell para gerenciar o Teams e o Skype for Business. 

Use esta orientação em conjunto com a referência [de cmdlet](https://docs.microsoft.com/powershell/teams/?view=teams-ps) do Microsoft Teams e a referência [de cmdlet](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)do Skype for Business.

## <a name="create-and-manage-teams-using-powershell"></a>Criar e gerenciar equipes usando o PowerShell

Os cmdlets para criar e gerenciar equipes estão no módulo [do PowerShell do Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

As equipes são respaldadas pelos Grupos do Office 365, portanto, quando você cria uma equipe, cria um grupo. Há um conjunto de cmdlets fornecidos para operar na equipe principal e suas configurações ( , , ), gerenciamento de usuários da equipe ( , ), bem como ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` cmdlets ``new-teamchannel`` para gerenciar os canais da equipe ( , ``remove-teamchannel`` ). Todos esses cmdlets podem ser executados como usuários finais, mas funcionarão somente nas equipes das que você possui ou das que são membros. Se você for um Administrador Global ou Administrador de Serviços do Teams, poderá atuar em todas as equipes de sua organização.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> O **GroupId** usado nos cmdlets de módulo do Microsoft Teams PowerShell é igual à propriedade **Identity** retornada no módulo ``Get-UnifiedGroup`` exchange PowerShell.

## <a name="manage-policies-via-powershell"></a>Gerenciar políticas por meio do PowerShell

> [!NOTE]
> - O Skype for Business Online Connector está sendo consolidado no PowerShell do Teams. No momento, ele está disponível na visualização pública. Com o tempo, os cmdlets do Skype for Business Online que se aplicam ao Teams estarão disponíveis de forma nativa no módulo do PowerShell do Teams. As etapas de instalação estão disponíveis no artigo [Instalar o PowerShell do Teams.](teams-powershell-install.md)
>
> - Os cmdlets estarão disponíveis na sessão do PowerShell assim que você se conectar ao Skype for Business Online. Para obter mais informações, consulte [Gerenciar o Skype for Business Online com o PowerShell do Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Encontre os cmdlets para gerenciar políticas no módulo [de cmdlet do Skype for Business.](https://www.microsoft.com/download/details.aspx?id=39366)

Uma política é um grupo de configurações que podem ser aplicadas granularmente a usuários individuais. Cada tipo de política tem seu próprio conjunto de cmdlets para criar, exibir, excluir e atualizar as próprias políticas e, em seguida, atribuir essas políticas aos usuários. A estrutura geral é:

- **Comandos GET** (por exemplo, ): retorna os documentos de política que estão disponíveis para você atribuir em sua organização, incluindo as políticas criadas pela Microsoft para você usar, bem como as políticas personalizadas que você ``Get-CsTeamsMeetingPolicy`` criou.
   - Para encontrar apenas as políticas personalizadas que você criou em sua organização, ``-Filter "tag:*"`` use.

- **NOVOS** comandos (por exemplo, ``New-CsTeamsMeetingPolicy`` ): cria novas políticas para a sua organização atribuir aos usuários em sua organização. Nem todas as políticas suportam a criação de políticas personalizadas. Muitas vezes, isso é para garantir que as políticas que você usa em sua organização tenham uma combinação de configurações com suporte.

- **Comandos** SET (por exemplo, ``Set-CsTeamsMeetingPolicy`` ): define valores específicos em uma determinada política. Algumas políticas não têm comandos SET disponíveis ou contêm parâmetros que não podem ser personalizados na política. As descrições do PowerShell dizem quais parâmetros não podem ser personalizados. 
   - Para editar a política que será atribuída por padrão aos usuários em sua organização que não têm uma política personalizada atribuída, ``Set-Cs<PolicyName> -Identity Global`` execute.

- **Comandos REMOVE** (por exemplo, ): exclui uma política personalizada que ``Remove-CsTeamsMeetingPolicy`` foi criada em seu locatário. Se você excluir uma política personalizada que tenha sido atribuída a pelo menos um usuário em sua organização, esse usuário voltará para a política global.
   - Na verdade, não é possível remover a política global em sua organização, mas se você quiser redefinir a política global em sua organização para as configurações padrão fornecidas pela Microsoft, ``Remove-Cs<PolicyName> -Identity Global`` execute.

- **Comando GRANT** (por exemplo, ``Grant-CsTeamsMeetingPolicy`` ): atribui uma política a um determinado usuário.
   - Para remover uma atribuição de política personalizada e fazer com que o usuário volte para a política padrão em sua organização, ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` execute.

> [!TIP]
> Nem todas as políticas permitem que políticas personalizadas sejam criadas, e algumas políticas têm configurações que você não pode personalizar (portanto, você pode exibir a configuração, mas não pode definir um valor personalizado durante ``set-`` e ``new-`` ). A documentação de cada cmdlet solicita se os parâmetros estão disponíveis para uso pelos clientes.

Parâmetros comuns:

- **Identidade:** ``Get-`` ``Set-`` para, ``New-`` e, o ``Remove-`` parâmetro Identidade sempre fará referência a uma instância de política específica.  Para, o parâmetro Identidade se refere a um objeto de usuário específico ao qual a ``Grant`` política está sendo aplicada. 

## <a name="manage-configurations-via-powershell"></a>Gerenciar configurações por meio do PowerShell

Encontre os cmdlets para gerenciar sua configuração no [módulo de cmdlet](https://www.microsoft.com/en-us/download/details.aspx?id=39366)do Skype for Business.

As configurações são buckets de configurações mantidas no serviço que não podem ser especificadas no nível do usuário. As configurações sempre se aplicam em toda a organização. Sua configuração global é a única configuração eficaz em sua organização. Cada tipo de configuração vem com dois cmdlets principais:

- ``Get-Cs<ConfigurationName>`` (por exemplo, ``Get-CsTeamsClientConfiguration`` ):

- Comandos SET (por exemplo, ``Set-CsTeamsClientConfiguration`` ): definir propriedades na configuração desse tipo. Especifique os parâmetros que você deseja modificar.
   > Você pode fazer referência à configuração que está modificando de uma das duas maneiras: especificando -**Identidade Global** ou ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` executando.

## <a name="what-can-each-admin-role-do"></a>O que cada função de administrador pode fazer?

Leia [Use as funções de administrador do Microsoft Teams para gerenciar o Teams](using-admin-roles.md) para entender quais funções de administrador podem executar cada cmdlet do PowerShell.

## <a name="related-topics"></a>Tópicos relacionados

[Instalando o PowerShell do Teams](teams-powershell-install.md)

[Notas de versão do PowerShell do Teams](teams-powershell-release-notes.md)

[Referência de cmdlet do Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência de cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usar as funções de administrador para gerenciar o Teams](using-admin-roles.md)
