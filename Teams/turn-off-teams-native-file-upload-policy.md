---
title: Desativar Teams de Upload de arquivo nativo
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
ms.openlocfilehash: 64bd9d23527ef1a63df4f258e89de5e60862a878
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192476"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Desativar Teams de Upload de arquivo nativo

Microsoft Teams usa OneDrive e SharePoint (ODSP) para armazenar e compartilhar conteúdo, mas algumas organizações e usuários podem preferir usar provedores de armazenamento de terceiros.  

Se a sua organização escolher um terceiro para armazenamento de conteúdo, você precisará desativar o parâmetro na política Teams ``NativeFileEntryPoints`` Arquivos. Esse parâmetro é habilitado por padrão, que mostra a opção de carregar conteúdo do ODSP para Teams chats ou canais.

Este artigo ajudará você a criar, definir, atribuir e remover o ``NativeFileEntryPoints`` parâmetro usando o PowerShell.

>[!NOTE]
>Quando Teams política arquivos do Teams estiver desligada, os usuários não verão pontos de acesso para o OneDrive e o SharePoint (ODSP) no Teams, mas a criação de novas equipes e canais continuará a disparar a geração de bibliotecas de SharePoint correspondentes.

## <a name="prepare-to-update-the-teams-files-policy"></a>Preparar para atualizar a política Teams arquivos

### <a name="set-up-microsoft-powershell"></a>Configurar o Microsoft PowerShell

Atualmente, essa política não pode ser alterada no Teams de administração. O administrador Microsoft 365 locatário da sua organização terá que fazer as alterações usando os cmdlets do PowerShell detalhados mais adiante neste artigo.

Saiba como instalar o módulo de Teams powershell usando a Galeria do PowerShell lendo [Install Microsoft Teams PowerShell Module](teams-powershell-install.md).

Para instalar ou baixar o módulo Teams PowerShell, consulte [Galeria do PowerShell para Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Para obter mais informações sobre como configurar o PowerShell para gerenciamento Teams, consulte [Manage Teams with Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Permitir aplicativos de terceiros no Teams Admin Center

Esta etapa não é necessária para alterar a política de arquivos Teams, mas é necessária quando você está pronto para integrar seu provedor de armazenamento de terceiros na experiência de Teams de seus usuários.

Seu Microsoft 365 administrador de locatários precisará habilitar a política "Permitir aplicativos de terceiros" no Teams de administração.

Para saber como permitir aplicativos personalizados ou de [terceiros,](/microsoftteams/manage-apps#manage-org-wide-app-settings)consulte Manage org-wide apps settings in Manage your apps in the Microsoft Teams admin center .

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Desativar NativeFileEntryPoints para todo o locatário

Definir o ``-Identity`` parâmetro para ``Global`` aplicará as configurações de política a todos os usuários em sua organização.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Exemplo de cmdlet de política do PowerShell para locatários inteiros

Este exemplo de comando do PowerShell definirá ``NativeFileEntryPoints`` o parâmetro para todo o ``Disabled`` locatário.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Verifique o status do locatário  

Para exibir o status atual da política de arquivos Teams do locatário, use ``Get-CsTeamsFilesPolicy`` o cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Ativar ou desativar o ponto de carregamento de arquivo nativo

Para ativar ou desativar o ponto de carregamento de arquivo nativo para todo o locatário, de definir o ``NativeFileEntryPoints`` parâmetro como ``Enabled`` ou ``Disabled`` .

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Remover a política para seus usuários

Para remover a política Teams arquivos para seus usuários, use ``Remove-CsTeamsFilesPolicy`` o cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Desativar NativeFileEntryPoints para usuários específicos

Você também pode atualizar a política Teams arquivos para usuários específicos criando uma nova cadeia de caracteres de política arquivos Teams e atribuindo a política recém-criada ``-Identity`` aos usuários.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Exemplo de cmdlet de política do PowerShell para usuários específicos

Este comando do PowerShell de exemplo criará um novo com o ``CsTeamsFilesPolicy`` nome e o parâmetro definido como ``-Identity`` ``UserPolicy`` ``NativeFileEntryPoints`` ``Disabled`` .

Quando um usuário recebe o com , seus pontos de entrada de arquivo nativos ``CsTeamsFilesPolicy`` ``-Identity UserPolicy`` serão desligados.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Atribuir uma política ao usuário

Depois de criar a nova política, você pode atribuir essa política aos usuários que usam ``Grant-CsTeamsFilesPolicy`` o cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Atualizar a política

Se você precisar alterar a configuração da nova política de arquivos ``UserPolicy`` Teams, use o ``Set-CsTeamsFilePolicy`` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Remover a política para a lista completa de usuários

Para remover a política de todos os usuários atribuídos à política de arquivos Teams ``UserPolicy`` , use ``Remove-CsTeamsFilesPolicy`` o cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Depois de fazer alterações na política, permita até 12 horas para que as alterações mostrem nos clientes Teams usuários.
