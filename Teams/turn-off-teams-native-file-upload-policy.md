---
title: Desativar a política de Upload de Arquivo Nativo do Teams
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
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1993371099d0712d21106987f21575e85e181ad7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268923"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Desativar a política de Upload de Arquivo Nativo do Teams

O Microsoft Teams usa o OneDrive e o SharePoint para armazenar e compartilhar conteúdo, mas algumas organizações e usuários podem preferir usar provedores de armazenamento de terceiros.  

Se sua organização escolher um terceiro para o armazenamento de conteúdo, `NativeFileEntryPoints` você precisará desativar o parâmetro na política de Arquivos do Teams. Esse parâmetro é habilitado por padrão, que mostra a opção de carregar conteúdo do OneDrive ou do SharePoint para chats ou canais do Teams.

Este artigo ajudará você a criar, definir, atribuir e remover o `NativeFileEntryPoints` parâmetro usando o PowerShell.

>[!NOTE]
>Quando a política de Arquivos do Teams estiver desativada, os usuários não verão pontos de acesso para o OneDrive e o SharePoint no Teams, mas a criação de novas equipes e canais continuará a disparar a geração de bibliotecas do SharePoint correspondentes.

## <a name="prepare-to-update-the-teams-files-policy"></a>Preparar-se para atualizar a política de Arquivos do Teams

### <a name="set-up-microsoft-powershell"></a>Configurar o Microsoft PowerShell

Atualmente, essa política não pode ser alterada no centro de administração do Teams. O administrador de locatários do Microsoft 365 da sua organização precisará fazer as alterações usando os cmdlets do PowerShell detalhados mais adiante neste artigo.

Saiba como instalar o módulo do PowerShell Teams usando o Galeria do PowerShell lendo [Instalar o Módulo do PowerShell do Microsoft Teams](teams-powershell-install.md).

Para instalar ou baixar o módulo do PowerShell do Teams, [Galeria do PowerShell para o Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Para obter mais informações sobre como configurar o PowerShell para gerenciamento do Teams, consulte [Gerenciar Equipes com o Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Permitir aplicativos de terceiros no Teams Administração Center

Esta etapa não é necessária para alterar a política de Arquivos do Teams, mas é necessária quando você está pronto para integrar seu provedor de armazenamento de terceiros na experiência do Teams dos usuários.

O administrador de locatários do Microsoft 365 precisará habilitar a política "Permitir aplicativos de terceiros" no centro de administração do Teams.

Para saber como permitir aplicativos personalizados ou de terceiros, consulte Gerenciar configurações de aplicativos em toda a organização em Gerenciar seus aplicativos no Centro de administração [do Microsoft Teams](/microsoftteams/manage-apps#manage-org-wide-app-settings).

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Desativar NativeFileEntryPoints para todo o locatário

Definir o `-Identity` parâmetro para `Global` aplicar as configurações de política a todos os usuários em sua organização.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Cmdlet de política do PowerShell de exemplo para todo o locatário

Este exemplo de comando do PowerShell definirá o`NativeFileEntryPoints` parâmetro para `Disabled` todo o locatário.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Verificar o status do seu locatário  

Para exibir o status atual da política de Arquivos do Teams do locatário, use o `Get-CsTeamsFilesPolicy` cmdlet.

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

Para remover a política de Arquivos do Teams para seus usuários, use o `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Desativar NativeFileEntryPoints para usuários específicos

Você também pode atualizar a política de Arquivos do Teams para usuários específicos criando uma nova cadeia de caracteres de política de Arquivos do Teams `-Identity` e atribuindo a política recém-criada aos usuários.

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

Se você precisar alterar a configuração da nova Política de Arquivos do `UserPolicy`Teams, use o `Set-CsTeamsFilePolicy` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Remover a política para a lista completa de usuários

Para remover a política de todos os usuários atribuídos à política de Arquivos do `UserPolicy`Teams, use o `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Depois de fazer alterações na política, aguarde até 12 horas para que as alterações sejam mostradas nos clientes do Teams dos usuários.
