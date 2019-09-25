---
title: Instalar o módulo PowerShell do StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como instalar e se conectar à versão de pré-lançamento do módulo do PowerShell do Microsoft StaffHub.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142029"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b198a-103">Instalar o módulo PowerShell do Microsoft PowerHub</span><span class="sxs-lookup"><span data-stu-id="b198a-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b198a-104">A partir de 1 ° de outubro de 2019, o Microsoft StaffHub será desativado.</span><span class="sxs-lookup"><span data-stu-id="b198a-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="b198a-105">Estamos criando recursos de StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b198a-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="b198a-106">Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="b198a-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="b198a-107">O StaffHub deixará de funcionar para todos os usuários em 1 ° de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="b198a-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="b198a-108">Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams.</span><span class="sxs-lookup"><span data-stu-id="b198a-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="b198a-109">Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="b198a-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="b198a-110">Use as etapas neste artigo para instalar e se conectar à versão de pré-lançamento do módulo Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b198a-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="b198a-111">Você precisará disso para [mover suas equipes do StaffHub para o Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b198a-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b198a-112">Instalar a versão de pré-lançamento do módulo do PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="b198a-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="b198a-113">Abra o Windows PowerShell 3,0 ou posterior como administrador. Para fazer isso, clique em **Iniciar**, digite **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell**e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="b198a-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b198a-114">Para obter a versão mais recente do Windows PowerShell, consulte [instalando o Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b198a-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="b198a-115">Execute o seguinte para instalar a versão de pré-lançamento do módulo StaffHub PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b198a-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="b198a-116">Você pode ver a mensagem de aviso:</span><span class="sxs-lookup"><span data-stu-id="b198a-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="b198a-117">Digite `Y`e clique em `Enter`.</span><span class="sxs-lookup"><span data-stu-id="b198a-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="b198a-118">Saia do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b198a-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b198a-119">Conectar-se ao módulo do Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="b198a-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="b198a-120">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b198a-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="b198a-121">Quando for solicitado, faça logon como um administrador global.</span><span class="sxs-lookup"><span data-stu-id="b198a-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b198a-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b198a-122">Related topics</span></span>

- [<span data-ttu-id="b198a-123">Referência do Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="b198a-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="b198a-124">Mova as suas equipes do Microsoft StaffHub para Turnos no Teams</span><span class="sxs-lookup"><span data-stu-id="b198a-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
