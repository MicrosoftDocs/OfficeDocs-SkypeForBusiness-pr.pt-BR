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
ms.openlocfilehash: 66f873b163222d3d9745e68881da2b8071f60eec
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396522"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Gerenciar o Teams com o Microsoft Teams PowerShell

Este artigo mostra como usar o Microsoft Teams PowerShell para gerenciar o Teams e Skype for Business.

Use essas diretrizes em conjunto com a referência [de cmdlet do Microsoft Teams](/powershell/teams/?view=teams-ps) [e Skype for Business de cmdlet.](/powershell/skype/intro?view=skype-ps)

Para gerenciar o Teams no centro de administração do Teams, confira [Gerenciar o Teams com o Azure Cloud Shell](#manage-teams-with-azure-cloud-shell).

## <a name="create-and-manage-teams-using-powershell"></a>Criar e gerenciar equipes usando o PowerShell

Os cmdlets para criar e gerenciar equipes estão no módulo [PowerShell do Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/).

As equipes são apoiadas Office 365 grupos, portanto, quando você cria uma equipe, cria um grupo. Há um conjunto de cmdlets fornecidos para operar na equipe principal e suas configurações (``new-team``, ``get-team``,  ``set-team``), gerenciar usuários da equipe (``add-teamuser``, ``remove-teamuser``), bem como cmdlets para gerenciar os canais da equipe (``new-teamchannel``, ``remove-teamchannel``). Todos esses cmdlets podem ser executados como usuários finais, mas funcionarão apenas nas equipes das quais você possui ou é membro. Se você for um Administração global ou administrador do Teams, poderá atuar em todas as equipes em sua organização.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> [!NOTE]
> A **GroupId** usada nos cmdlets do módulo do PowerShell do Microsoft Teams é a mesma que a propriedade **Identity** retornada ``Get-UnifiedGroup`` no módulo do Exchange PowerShell.

## <a name="manage-teams-with-azure-cloud-shell"></a>Gerenciar o Teams com o Azure Cloud Shell

Cloud Shell é um shell interativo, autenticado e acessível pelo navegador que permite gerenciar seus recursos. Para obter mais informações sobre Cloud Shell, consulte [o Azure Cloud Shell](/azure/cloud-shell/overview).

Para acessar o Azure Cloud Shell e usar o PowerShell para gerenciar o Teams, entre no centro de administração do Teams.

1. Selecione o Cloud Shell ícone no canto superior direito.

    ![Captura de tela do cabeçalho do Centro de administração do Teams com Cloud Shell ícone.](media/cloud-shell-icon-select.png)

1. Quando solicitado, escolha **PowerShell**.

    ![Captura de tela do prompt de Cloud Shell Azure.](media/cloud-shell.png)

1. Execute o seguinte comando para iniciar uma sessão do Teams PowerShell:

    ```powershell
    Connect-MicrosoftTeams
    ```

Depois de concluir essas etapas, você estará pronto para executar comandos do PowerShell do Teams.

> [!IMPORTANT]
> Se você quiser usar cmdlets Cs*, primeiro precisará se conectar ao Teams usando o ``Connect-MicrosoftTeams -UseDeviceAuthentication`` comando.

## <a name="manage-policies-via-powershell"></a>Gerenciar políticas por meio do PowerShell

> [!NOTE]
> - Skype for Business Online Connector está sendo consolidado no Teams PowerShell. Ele está disponível atualmente em versão prévia pública. Com o tempo, Skype for Business cmdlets Online que se aplicam ao Teams estarão nativamente disponíveis no módulo do PowerShell do Teams. As etapas de instalação estão disponíveis no artigo [Instalar o PowerShell do Teams](teams-powershell-install.md) .
> - Os cmdlets estarão disponíveis em sua sessão do PowerShell depois que você se conectar ao Skype for Business Online. Para obter mais informações, consulte [Gerenciar Skype for Business Online com Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Localize os cmdlets para gerenciar políticas [no módulo Skype for Business cmdlet.](/powershell/module/teams)

Uma política é um grupo de configurações que podem ser aplicadas granularmente a usuários individuais. Cada tipo de política tem seu próprio conjunto de cmdlets para criar, exibir, excluir e atualizar as próprias políticas e, em seguida, atribuir essas políticas aos usuários. A estrutura geral é:

- **Comandos GET** (por exemplo): retorna os documentos de política que estão disponíveis para você atribuir em sua organização, incluindo as políticas criadas pela Microsoft para você usar, ``Get-CsTeamsMeetingPolicy``bem como as políticas personalizadas que você criou.
  - Para localizar apenas as políticas personalizadas que você criou em sua organização, use ``-Filter "tag:*"``.

- **Novos** comandos (por exemplo: ``New-CsTeamsMeetingPolicy``cria novas políticas para sua organização atribuir aos usuários em sua organização. Nem todas as políticas dão suporte à criação de políticas personalizadas. Geralmente, isso é para garantir que as políticas usadas em sua organização tenham uma combinação de configurações com suporte.

- **Comandos SET** (por exemplo): ``Set-CsTeamsMeetingPolicy``define valores específicos em uma determinada política. Algumas políticas não têm comandos SET disponíveis ou contêm parâmetros que não podem ser personalizados na política. As descrições do PowerShell informam quais parâmetros não podem ser personalizados.
  - Para editar a política que, por padrão, será atribuída aos usuários em sua organização que não têm uma política personalizada atribuída, execute ``Set-Cs<PolicyName> -Identity Global``.

- **Comandos REMOVE** (por exemplo): ``Remove-CsTeamsMeetingPolicy``exclui uma política personalizada que foi criada em seu locatário. Se você excluir uma política personalizada que foi atribuída a pelo menos um usuário em sua organização, esse usuário retornará à política global.
  - Você não pode realmente remover a política global em sua organização, mas se quiser redefinir a política global em sua organização para as configurações padrão fornecidas pela Microsoft, execute ``Remove-Cs<PolicyName> -Identity Global``.

- **Comando GRANT** (por exemplo): ``Grant-CsTeamsMeetingPolicy``atribui uma política a um usuário específico.
  - Para remover uma atribuição de política personalizada e fazer com que o usuário volte para a política padrão em sua organização, execute ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.

> [!TIP]
> Nem todas as políticas permitem que políticas personalizadas sejam criadas, e algumas políticas têm configurações que você não pode personalizar (portanto, você pode exibir a ``set-`` configuração, mas não pode definir um valor personalizado durante e ``new-``). A documentação de cada cmdlet indica se os parâmetros estão disponíveis para uso pelos clientes.

Parâmetros comuns:

- **Identidade**: para ``Get-``, ``Set-``, ``New-``e , o ``Remove-``parâmetro **Identity** sempre se referirá a uma instância de política específica. For ``Grant``, o **parâmetro Identity** refere-se a um objeto de usuário específico ao qual a política está sendo aplicada.

## <a name="manage-configurations-via-powershell"></a>Gerenciar configurações por meio do PowerShell

Localize os cmdlets para gerenciar sua configuração [no módulo Skype for Business cmdlet.](/powershell/module/skype)

As configurações são buckets de configurações mantidas no serviço que não podem ser especificadas em um nível de usuário. As configurações sempre se aplicam em toda a organização. Sua configuração global é a única configuração efetiva em sua organização. Cada tipo de configuração vem com dois cmdlets principais:

- ``Get-Cs<ConfigurationName>`` (por exemplo, ``Get-CsTeamsClientConfiguration``):

- Comandos SET (por exemplo: ``Set-CsTeamsClientConfiguration``definir propriedades na configuração desse tipo. Especifique os parâmetros que você deseja modificar.
    > [!NOTE]
    > Você pode referenciar a configuração que está modificando de uma das duas maneiras: especificando -**Identity Global** ou executando ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.

## <a name="what-can-each-admin-role-do"></a>O que cada função de administrador pode fazer?

Leia [Use as funções de administrador do Microsoft Teams para gerenciar o Teams](using-admin-roles.md) para entender quais funções de administrador podem executar cada cmdlet do PowerShell.

## <a name="related-topics"></a>Tópicos relacionados

[Instalando o PowerShell do Teams](teams-powershell-install.md)

[Notas de versão do PowerShell do Teams](teams-powershell-release-notes.md)

[Referência de cmdlet Teams](/powershell/teams/?view=teams-ps)

[Skype for Business de cmdlet](/powershell/skype/intro?view=skype-ps)

[Usar as funções de administrador para gerenciar o Teams](using-admin-roles.md)
