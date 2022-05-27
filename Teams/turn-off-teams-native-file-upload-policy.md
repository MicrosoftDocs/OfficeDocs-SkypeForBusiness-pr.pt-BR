---
title: Desativar a Teams de Upload Nativa
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Saiba como criar, definir, atribuir e ajustar a política Teams arquivos usando o PowerShell.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b6089e93b4754fa35edaa9befb5cfa6bb176238
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681902"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Desativar a Teams de Upload Nativa

Microsoft Teams usa OneDrive e SharePoint para armazenar e compartilhar conteúdo, mas algumas organizações e usuários podem preferir usar provedores de armazenamento de terceiros.  

Se sua organização escolher um terceiro para armazenamento de conteúdo, `NativeFileEntryPoints` você precisará desativar o parâmetro na política Teams Arquivos. Esse parâmetro é habilitado por padrão, que mostra a opção de carregar conteúdo de OneDrive ou SharePoint para Teams chats ou canais.

Este artigo ajudará você a criar, definir, atribuir e remover o `NativeFileEntryPoints` parâmetro usando o PowerShell.

>[!NOTE]
>Quando a política de Arquivos do Teams estiver desativada, os usuários não verão pontos de acesso para OneDrive e SharePoint no Teams, mas a criação de novas equipes e canais continuará a disparar a geração de bibliotecas SharePoint correspondentes.

## <a name="prepare-to-update-the-teams-files-policy"></a>Preparar para atualizar a política Teams arquivos

### <a name="set-up-microsoft-powershell"></a>Configurar o Microsoft PowerShell

Atualmente, essa política não pode ser alterada no centro Teams administrador. O administrador de locatários Microsoft 365 sua organização precisará fazer as alterações usando os cmdlets do PowerShell detalhados mais adiante neste artigo.

Saiba como instalar o módulo Teams PowerShell usando o Galeria do PowerShell lendo [Instalar Microsoft Teams PowerShell](teams-powershell-install.md).

Para instalar ou baixar o Teams do PowerShell, consulte [Galeria do PowerShell para Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Para obter mais informações sobre como configurar o PowerShell para gerenciamento de Teams, consulte Gerenciar Teams [com Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Permitir aplicativos de terceiros no Teams Administração Center

Esta etapa não é necessária para alterar a política de arquivos Teams, mas é necessária quando você está pronto para integrar seu provedor de armazenamento de terceiros na experiência de Teams de seus usuários.

Seu Microsoft 365 administrador de locatários precisará habilitar a política "Permitir aplicativos de terceiros" no Teams de administração.

Para saber como permitir aplicativos personalizados ou de terceiros, consulte Gerenciar configurações de aplicativos em toda a organização em Gerenciar seus aplicativos no centro de administração do [Microsoft Teams.](/microsoftteams/manage-apps#manage-org-wide-app-settings)

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Desativar NativeFileEntryPoints para todo o locatário

Definir o `-Identity` parâmetro para `Global` aplicar as configurações de política a todos os usuários em sua organização.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Cmdlet de política do PowerShell de exemplo para todo o locatário

Este exemplo de comando do PowerShell definirá o`NativeFileEntryPoints` parâmetro para `Disabled` todo o locatário.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Verificar o status do seu locatário  

Para exibir o status atual da política de arquivos Teams locatário, use o `Get-CsTeamsFilesPolicy` cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Ativar ou desativar o ponto de carregamento de arquivo nativo

Para ativar ou desativar o ponto de carregamento de arquivo nativo para todo o locatário, defina `NativeFileEntryPoints` o parâmetro como um ou `Enabled` `Disabled`.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Remover a política para seus usuários

Para remover a política Teams arquivos para seus usuários, use o `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Desativar NativeFileEntryPoints para usuários específicos

Você também pode atualizar a política Teams arquivos para usuários específicos criando uma nova cadeia de caracteres de política de arquivos Teams e atribuindo a `-Identity` política recém-criada aos usuários.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Cmdlet de política do PowerShell de exemplo para usuários específicos

Este exemplo de comando do PowerShell criará um novo `CsTeamsFilesPolicy` com o nome e `UserPolicy` o parâmetro `NativeFileEntryPoints` definido como `Disabled``-Identity` .

Quando um usuário é atribuído com `CsTeamsFilesPolicy` `-Identity UserPolicy`, seus pontos de entrada de arquivo nativo serão desativados.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Atribuir uma política ao usuário

Depois de criar a nova política, você pode atribuir essa política aos usuários usando o `Grant-CsTeamsFilesPolicy` cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Atualizar a política

Se você precisar alterar a configuração da nova política Teams arquivos`UserPolicy`, use o `Set-CsTeamsFilePolicy` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Remover a política para a lista completa de usuários

Para remover a política de todos os usuários atribuídos à política Teams arquivos`UserPolicy`, use o `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Depois de fazer alterações na política, aguarde até 12 horas para que as alterações sejam mostradas nos clientes Teams usuários.
