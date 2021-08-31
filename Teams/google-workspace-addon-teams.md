---
title: Configurar um Microsoft Teams de reunião para o Google Workspace
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Saiba como configurar o Microsoft Teams de reunião para o Google Workspace.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb5f7574bd5e07598c412cd7d17f02625de2f095
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729910"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurar um Microsoft Teams de reunião para o Google Workspace

O uso do Microsoft Teams de reunião permite que os usuários do Google calendar agendem e participem de uma reunião Microsoft Teams diretamente do Google Workspace. Os usuários terão acesso a Teams de reuniões, incluindo vídeo e audioconferência, compartilhamento de tela, chat de reunião, quadro de comunicação digital e muito mais. Mantenha-se conectado e organizado para fazer mais juntos no trabalho, na escola e na vida.

O Microsoft Teams de reunião do Google Workspace deve ser habilitado por um administrador Teams para que os usuários de locatários possam acessar o aplicativo.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Habilitar ou desabilitar Microsoft Teams complemento de reunião para o Google Workspace no portal do Azure

Como administrador de locatários, você pode habilitar ou desabilitar um complemento Microsoft Teams reunião do Google Workspace a partir da conta de administrador da sua organização usando o portal do Azure.

O complemento está habilitado por padrão.

1. Entre no portal do Azure.

2. Selecione **Enterprise aplicativos**  >  **Todos os aplicativos**.

3. **Pesquise Microsoft Teams complemento de reunião do Google Workspace**.

   ![Portal do Azure mostrando todos os aplicativos.](media/aad-add-google-workspace.png)

4. Selecione **Sim**.

   ![Portal do Azure mostrando as propriedades do espaço de trabalho do google.](media/google-workspace-properties.png)

5. (Opcional) Para desabilitar o complemento, selecione **Não em** vez de **Sim** na Etapa 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Desabilitar Microsoft Teams complemento de reunião do Google Workspace usando o PowerShell

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Para obter mais informações, [consulte Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Excluir o Microsoft Teams de reunião do Google Workspace

Consulte a documentação do Google [Excluir um aplicativo do Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) para obter instruções.