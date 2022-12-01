---
title: Desativar a política de Carregamento de Arquivos Nativos do Teams
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Saiba como criar, definir, atribuir e ajustar a Política de Arquivos do Teams usando o PowerShell.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.openlocfilehash: 6c7d5c89c780fa5c9286f5d7f7d2304f2e6c6220
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198523"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Desativar a política de Carregamento de Arquivos Nativos do Teams

Microsoft o Teams usa o OneDrive e o SharePoint para armazenar e compartilhar conteúdo, mas algumas organizações e usuários podem preferir usar provedores de armazenamento de terceiros.  

Se sua organização escolher um terceiro para armazenamento de conteúdo, você precisará desativar o `NativeFileEntryPoints` parâmetro na política Arquivos do Teams. Esse parâmetro está habilitado por padrão, o que mostra a opção de carregar conteúdo do OneDrive ou do SharePoint para chats ou canais do Teams.

Este artigo ajudará você a criar, definir, atribuir e remover o parâmetro usando o `NativeFileEntryPoints` PowerShell.

>[!NOTE]
>Quando a política Arquivos do Teams for desativada, os usuários não verão pontos de acesso para o OneDrive e o SharePoint no Teams, mas a criação de novas equipes e canais continuará a disparar a geração de bibliotecas correspondentes do SharePoint.

## <a name="prepare-to-update-the-teams-files-policy"></a>Prepare-se para atualizar a política de Arquivos do Teams

### <a name="set-up-microsoft-powershell"></a>Configurar Microsoft PowerShell

Atualmente, essa política não pode ser alterada no centro de administração do Teams. O administrador de locatários Microsoft 365 da sua organização terá que fazer as alterações usando os cmdlets do PowerShell detalhados posteriormente neste artigo.

Saiba como instalar o módulo do PowerShell Teams usando Galeria do PowerShell lendo [Instalar Microsoft Módulo do Teams PowerShell](teams-powershell-install.md).

Para instalar ou baixar o módulo do Teams PowerShell, consulte [Galeria do PowerShell para Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Para obter mais informações sobre como configurar o gerenciamento do PowerShell para Teams, consulte [Gerenciar o Teams com Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Permitir aplicativos de terceiros no Teams Administração Center

Essa etapa não é necessária para alterar a política de Arquivos do Teams, mas é necessária quando você estiver pronto para integrar seu provedor de armazenamento de terceiros na experiência do Teams dos usuários.

Seu Microsoft administrador de locatário 365 precisará habilitar a política "Permitir aplicativos de terceiros" no centro de administração do Teams.

Para saber como permitir aplicativos personalizados ou de terceiros, consulte Gerenciar configurações de aplicativos em toda a organização em [Gerenciar seus aplicativos no centro de administração do Microsoft Teams](/microsoftteams/manage-apps#manage-org-wide-app-settings).

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Desative NativeFileEntryPoints para todo o locatário

Definir o `-Identity` parâmetro para `Global` aplicará as configurações de política a todos os usuários da sua organização.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Cmdlet de política do PowerShell de exemplo para locatário inteiro

Este comando do PowerShell de exemplo definirá o`NativeFileEntryPoints` parâmetro como para `Disabled` todo o locatário.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Verifique o status do seu locatário  

Para exibir o status atual da política de Arquivos do Teams do locatário, use o `Get-CsTeamsFilesPolicy` cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Ativar ou desativar o ponto de carregamento de arquivo nativo

Para ativar ou desativar o ponto de carregamento de arquivo nativo para todo o locatário, defina o `NativeFileEntryPoints` parâmetro como `Enabled` ou `Disabled`.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Remover a política para seus usuários

Para remover a política Arquivos do Teams para seus usuários, use o `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Desativar NativeFileEntryPoints para usuários específicos

Você também pode atualizar a política de Arquivos do Teams para usuários específicos criando uma nova cadeia de caracteres de política `-Identity` do Teams Files e atribuindo a política recém-criada aos usuários.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Cmdlet de política do PowerShell de exemplo para usuários específicos

Este comando do PowerShell de exemplo criará um novo com o `-Identity` nome como e o `NativeFileEntryPoints` parâmetro definido como `UserPolicy` `Disabled`.`CsTeamsFilesPolicy`

Quando um usuário recebe o com `-Identity UserPolicy`, seus `CsTeamsFilesPolicy` pontos de entrada de arquivo nativo serão desativados.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Atribuir uma política ao usuário

Depois de criar a nova política, você pode atribuir essa política aos usuários usando o `Grant-CsTeamsFilesPolicy` cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Atualizar a política

Se você precisar alterar a configuração da nova Política `UserPolicy`de Arquivos do Teams, use o `Set-CsTeamsFilePolicy` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Remover a política para a lista completa de usuários

Para remover a política de todos os usuários atribuídos à política `UserPolicy`Arquivos do Teams, use o `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Depois de fazer alterações na política, permita até 12 horas para que as alterações sejam exibidas nos clientes do Teams dos usuários.
