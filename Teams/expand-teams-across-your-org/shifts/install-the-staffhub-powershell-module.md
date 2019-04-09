---
title: Instale o módulo StaffHub PowerShell
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como instalar e conectar ao módulo do Microsoft StaffHub PowerShell.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31555125"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="1425a-103">Instale o módulo do Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="1425a-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1425a-104">A partir de 1 de outubro de 2019, Microsoft StaffHub será desativada.</span><span class="sxs-lookup"><span data-stu-id="1425a-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="1425a-105">Estamos compilando recursos StaffHub em Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1425a-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="1425a-106">Hoje, equipes inclui o aplicativo desloca para o gerenciamento de agenda e recursos adicionais serão distribuir ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="1425a-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="1425a-107">StaffHub irá parar de funcionar para todos os usuários em 1 de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="1425a-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="1425a-108">Qualquer pessoa que tenta abrir StaffHub será mostrada uma mensagem direcionando-os para baixar as equipes.</span><span class="sxs-lookup"><span data-stu-id="1425a-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="1425a-109">Para saber mais, consulte [Microsoft StaffHub para ser retirado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="1425a-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="1425a-110">Use as etapas neste artigo para instalar e conectar ao módulo do Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1425a-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="1425a-111">Você precisará isso para gerenciar StaffHub usando o PowerShell e mover suas equipes StaffHub a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1425a-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="1425a-112">Instale o módulo do Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="1425a-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="1425a-113">Baixe o [módulo de StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="1425a-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="1425a-114">Abra o Windows PowerShell 3.0 ou posterior como administrador.</span><span class="sxs-lookup"><span data-stu-id="1425a-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="1425a-115">Para fazer isso, clique em **Iniciar**, digite o **Windows PowerShell**, com o botão direito **Do Windows PowerShell**e, em seguida, selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="1425a-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="1425a-116">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1425a-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```

4. <span data-ttu-id="1425a-117">O caminho da pasta na saída e certifique-se de que todas as pastas no caminho existem no seu computador antes de ir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="1425a-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="1425a-118">Se não existirem pastas, criá-los.</span><span class="sxs-lookup"><span data-stu-id="1425a-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="1425a-119">Execute o seguinte, onde &lt;caminho&gt; é o caminho na saída da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="1425a-119">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="1425a-120">Por exemplo, o caminho pode parecer com C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="1425a-120">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="1425a-121">Conectar ao módulo do Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="1425a-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="1425a-122">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1425a-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="1425a-123">Quando solicitado, faça login como um administrador de global.</span><span class="sxs-lookup"><span data-stu-id="1425a-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1425a-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1425a-124">Related topics</span></span>

- [<span data-ttu-id="1425a-125">Referência do Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="1425a-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="1425a-126">Mova as suas equipes do Microsoft StaffHub para Turnos no Teams</span><span class="sxs-lookup"><span data-stu-id="1425a-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
