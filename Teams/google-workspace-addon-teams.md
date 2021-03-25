---
title: Configurar o complemento de reunião do Microsoft Teams para o Google Workspace
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
description: Saiba como configurar o complemento de reunião do Microsoft Teams para o Google Workspace.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e1b7024190ac51b89e09fafced86ffea13f5961
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120692"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="c0dac-103">Configurar o complemento de reunião do Microsoft Teams para o Google Workspace</span><span class="sxs-lookup"><span data-stu-id="c0dac-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="c0dac-104">O uso do complemento de reunião do Microsoft Teams permite que os usuários do calendário do Google agendem e participem de uma reunião do Microsoft Teams diretamente do Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="c0dac-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="c0dac-105">Os usuários terão acesso aos recursos de reuniões do Teams, incluindo vídeo e audioconferência, compartilhamento de tela, chat de reunião, quadro de comunicação digital e muito mais.</span><span class="sxs-lookup"><span data-stu-id="c0dac-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="c0dac-106">Mantenha-se conectado e organizado para fazer mais juntos no trabalho, na escola e na vida.</span><span class="sxs-lookup"><span data-stu-id="c0dac-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="c0dac-107">O complemento de reunião do Microsoft Teams para o Google Workspace deve ser habilitado por um administrador do Teams para que os usuários de locatários possam acessar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c0dac-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="c0dac-108">Habilitar ou desabilitar o complemento de reunião do Microsoft Teams para o Google Workspace no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="c0dac-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="c0dac-109">Como administrador de locatários, você pode habilitar ou desabilitar um complemento de reunião do Microsoft Teams para o Google Workspace a partir da conta de administrador da sua organização usando o portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="c0dac-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="c0dac-110">O complemento está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c0dac-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="c0dac-111">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="c0dac-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="c0dac-112">Selecione **Aplicativos**  >  **Empresariais Todos os aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c0dac-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="c0dac-113">Pesquisar o **complemento de reunião do Microsoft Teams para o Google Workspace**.</span><span class="sxs-lookup"><span data-stu-id="c0dac-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![Portal do Azure mostrando todos os aplicativos](media/aad-add-google-workspace.png)

4. <span data-ttu-id="c0dac-115">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c0dac-115">Select **Yes**.</span></span>

   ![Portal do Azure mostrando as propriedades do espaço de trabalho do google](media/google-workspace-properties.png)

5. <span data-ttu-id="c0dac-117">(Opcional) Para desabilitar o complemento, selecione **Não em** vez de **Sim** na Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="c0dac-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="c0dac-118">Desabilitar o complemento de reunião do Microsoft Teams para o Google Workspace usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0dac-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="c0dac-119">Para obter mais informações, [consulte Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span><span class="sxs-lookup"><span data-stu-id="c0dac-119">For more information, see [Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="c0dac-120">Excluir o complemento de reunião do Microsoft Teams para o Google Workspace</span><span class="sxs-lookup"><span data-stu-id="c0dac-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="c0dac-121">Consulte a documentação do Google [Excluir um aplicativo do Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="c0dac-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>