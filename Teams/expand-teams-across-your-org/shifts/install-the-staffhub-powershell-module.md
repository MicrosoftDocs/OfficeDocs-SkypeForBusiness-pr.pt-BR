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
description: Saiba como instalar e se conectar ao módulo do PowerShell do Microsoft StaffHub.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75ed6840b409f391b87759e2004c0f1ea475ce69
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827559"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b2e43-103">Instalar o módulo PowerShell do Microsoft PowerHub</span><span class="sxs-lookup"><span data-stu-id="b2e43-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2e43-104">A partir de 31 de dezembro de 2019, o Microsoft StaffHub será desativado.</span><span class="sxs-lookup"><span data-stu-id="b2e43-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="b2e43-105">Estamos criando recursos de StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2e43-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="b2e43-106">Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="b2e43-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="b2e43-107">O StaffHub deixará de funcionar para todos os usuários em 31 de dezembro de 2019.</span><span class="sxs-lookup"><span data-stu-id="b2e43-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="b2e43-108">Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams.</span><span class="sxs-lookup"><span data-stu-id="b2e43-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="b2e43-109">Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="b2e43-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="b2e43-110">Use as etapas neste artigo para instalar e se conectar ao módulo do PowerShell do Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b2e43-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="b2e43-111">Você precisará disso para [mover suas equipes do StaffHub para o Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b2e43-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b2e43-112">Instalar o módulo PowerShell do Microsoft PowerHub</span><span class="sxs-lookup"><span data-stu-id="b2e43-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="b2e43-113">Baixe o [módulo StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span><span class="sxs-lookup"><span data-stu-id="b2e43-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span></span>
2. <span data-ttu-id="b2e43-114">Abra o Windows PowerShell 3,0 ou posterior como administrador. Para fazer isso, clique em **Iniciar**, digite **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell**e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="b2e43-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b2e43-115">Para obter a versão mais recente do Windows PowerShell, consulte [instalando o Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b2e43-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span>
3. <span data-ttu-id="b2e43-116">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b2e43-116">Run the following:</span></span>

    ```PowerShell
    $ENV:PSModulePath
    ```
4. <span data-ttu-id="b2e43-117">Verifique o caminho da pasta na saída e certifique-se de que todas as pastas no caminho existem em seu computador antes de ir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="b2e43-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="b2e43-118">Se estiverem faltando pastas, crie-as.</span><span class="sxs-lookup"><span data-stu-id="b2e43-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="b2e43-119">Execute o seguinte para permitir a instalação do módulo StaffHub PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b2e43-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. <span data-ttu-id="b2e43-120">Execute o seguinte, em &lt;que&gt; Path é o caminho na saída da etapa 3.</span><span class="sxs-lookup"><span data-stu-id="b2e43-120">Run the following, where &lt;path&gt; is the path in the output from step 3.</span></span> <span data-ttu-id="b2e43-121">Por exemplo, o caminho pode se parecer como C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="b2e43-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="b2e43-122">Certifique-se de executar cada comando separadamente.</span><span class="sxs-lookup"><span data-stu-id="b2e43-122">Be sure to run each command separately.</span></span>

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. <span data-ttu-id="b2e43-123">Saia do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2e43-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="b2e43-124">Abra o Windows PowerShell 3,0 ou posterior como um administrador global e, em seguida, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b2e43-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b2e43-125">Conectar-se ao módulo do Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2e43-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="b2e43-126">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b2e43-126">Run the following:</span></span>

    ```PowerShell
    Connect-StaffHub
    ```

2. <span data-ttu-id="b2e43-127">Quando for solicitado, faça logon como um administrador global.</span><span class="sxs-lookup"><span data-stu-id="b2e43-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b2e43-128">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b2e43-128">Related topics</span></span>

- [<span data-ttu-id="b2e43-129">Referência do Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2e43-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="b2e43-130">Mova as suas equipes do Microsoft StaffHub para o Shifts no Teams</span><span class="sxs-lookup"><span data-stu-id="b2e43-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
