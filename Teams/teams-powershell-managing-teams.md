---
title: Gerenciar Teams com Microsoft Teams PowerShell
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
description: Aprenda a gerenciar Microsoft Teams usando Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86d5069794d160d4c4241a67f0c8d45fc9cac708
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046017"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Gerenciar Teams com Microsoft Teams PowerShell

Este artigo mostra como usar o Microsoft Teams PowerShell para gerenciar Teams e Skype for Business.

Use essa orientação em conjunto com a referência Microsoft Teams [cmdlet](/powershell/teams/?view=teams-ps) Skype for Business [cmdlet](/powershell/skype/intro?view=skype-ps).

Para gerenciar Teams no centro de administração Teams, consulte [Manage Teams with Azure Cloud Shell](#manage-teams-with-azure-cloud-shell).

## <a name="create-and-manage-teams-using-powershell"></a>Criar e gerenciar equipes usando o PowerShell

Os cmdlets para criar e gerenciar equipes estão no módulo [Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).

Teams são apoiados por grupos Office 365, portanto, quando você cria uma equipe, cria um grupo. Há um conjunto de cmdlets fornecidos para operar na equipe principal e suas configurações ( , , ), gerenciar usuários de equipe ( , ), bem como ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` cmdlets ``new-teamchannel`` para gerenciar os canais da equipe ( , ``remove-teamchannel`` ). Todos esses cmdlets podem ser executados como usuários finais, mas funcionarão apenas nas equipes das que você possui ou são membros. Se você for administrador global ou Teams administrador, poderá atuar em todas as equipes de sua organização.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> [!NOTE]
> O **GroupId** usado nos cmdlets do módulo Microsoft Teams PowerShell é o mesmo que a propriedade **Identity** retornada no módulo ``Get-UnifiedGroup`` Exchange PowerShell.

## <a name="manage-teams-with-azure-cloud-shell"></a>Gerenciar Teams com o Shell de Nuvem do Azure

O Cloud Shell é um shell interativo, autenticado e acessível ao navegador que permite gerenciar seus recursos. Para obter mais informações sobre o Shell de Nuvem, consulte [Azure Cloud Shell](/azure/cloud-shell/overview).

Para acessar o Shell de Nuvem do Azure e usar o PowerShell para gerenciar o Teams, entre no Teams de administração.

1. Selecione o ícone do Shell de Nuvem no canto superior direito.

    ![Captura de tela do Teams de centro de administração com ícone do Shell de Nuvem.](media/cloud-shell-icon-select.png)

1. Quando solicitado, escolha **PowerShell**.

    ![Captura de tela do prompt do Shell de Nuvem do Azure.](media/cloud-shell.png)

1. Execute o seguinte comando para iniciar uma sessão Teams PowerShell:

    ```powershell
    Connect-MicrosoftTeams
    ```

Depois de concluir essas etapas, você estará pronto para executar Teams comandos do PowerShell.

> [!IMPORTANT]
> Se você quiser usar cmdlets Cs*, primeiro precisará se conectar ao Teams usando o ``Connect-MicrosoftTeams -UseDeviceAuthentication`` comando.

## <a name="manage-policies-via-powershell"></a>Gerenciar políticas por meio do PowerShell

> [!NOTE]
> - Skype for Business O Conector Online está sendo consolidado no Teams PowerShell. Atualmente, ele está disponível na visualização pública. Com o tempo, Skype for Business cmdlets online que se aplicam ao Teams estarão disponíveis na verdade no módulo Teams PowerShell. As etapas de instalação estão disponíveis no artigo [Instalar Teams PowerShell.](teams-powershell-install.md)
> - Os cmdlets estarão disponíveis na sessão do PowerShell quando você se conectar ao Skype for Business Online. Para obter mais informações, consulte [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Encontre os cmdlets para gerenciar políticas [no módulo Skype for Business cmdlet](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).

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

Encontre os cmdlets para gerenciar sua configuração [no módulo Skype for Business cmdlet](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).

As configurações são buckets de configurações mantidas no serviço que não podem ser especificadas em um nível de usuário. Configurações sempre se aplicar em toda a organização. Sua configuração global é a única configuração efetiva em sua organização. Cada tipo de configuração vem com dois cmdlets principais:

- ``Get-Cs<ConfigurationName>`` (por exemplo, ``Get-CsTeamsClientConfiguration`` ):

- Comandos SET (por exemplo: ``Set-CsTeamsClientConfiguration`` definir propriedades na configuração desse tipo. Especifique os parâmetros que você deseja modificar.
    > [!NOTE]
    > Você pode fazer referência à configuração que está modificando de duas maneiras: especificando -**Identity Global** ou executando ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>O que cada função de administrador pode fazer?

Leia [Use Microsoft Teams de](using-admin-roles.md) administrador para gerenciar Teams entender quais funções de administrador podem executar cada cmdlet do PowerShell.

## <a name="related-topics"></a>Tópicos relacionados

[Instalando Teams PowerShell](teams-powershell-install.md)

[Teams Notas de versão do PowerShell](teams-powershell-release-notes.md)

[Referência de cmdlet Teams](/powershell/teams/?view=teams-ps)

[Skype for Business de cmdlet](/powershell/skype/intro?view=skype-ps)

[Usar as funções de administrador para gerenciar o Teams](using-admin-roles.md)
