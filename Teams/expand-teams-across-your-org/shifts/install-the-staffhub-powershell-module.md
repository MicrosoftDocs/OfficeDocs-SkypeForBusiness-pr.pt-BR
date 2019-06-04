---
title: Instalar o módulo PowerShell do StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como instalar e se conectar ao módulo do PowerShell do Microsoft StaffHub.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6eab331c8d8b2213225ad8c7ee216f9f6ec2b51
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681877"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="e31dd-103">Instalar o módulo PowerShell do Microsoft PowerHub</span><span class="sxs-lookup"><span data-stu-id="e31dd-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e31dd-104">A partir de 1 ° de outubro de 2019, o Microsoft StaffHub será desativado.</span><span class="sxs-lookup"><span data-stu-id="e31dd-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="e31dd-105">Estamos criando recursos de StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e31dd-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="e31dd-106">Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="e31dd-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="e31dd-107">O StaffHub deixará de funcionar para todos os usuários em 1 ° de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="e31dd-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="e31dd-108">Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams.</span><span class="sxs-lookup"><span data-stu-id="e31dd-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="e31dd-109">Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="e31dd-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="e31dd-110">Use as etapas neste artigo para instalar e se conectar ao módulo do PowerShell do Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="e31dd-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="e31dd-111">Você precisará disso para gerenciar o StaffHub usando o PowerShell e para mover suas equipes do StaffHub para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e31dd-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="e31dd-112">Instalar o módulo PowerShell do Microsoft PowerHub</span><span class="sxs-lookup"><span data-stu-id="e31dd-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="e31dd-113">Baixe o [módulo StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="e31dd-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="e31dd-114">Abra o Windows PowerShell 3,0 ou posterior como administrador.</span><span class="sxs-lookup"><span data-stu-id="e31dd-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="e31dd-115">Para fazer isso, clique em **Iniciar**, digite **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell**e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e31dd-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="e31dd-116">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e31dd-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
    

4. <span data-ttu-id="e31dd-117">Verifique o caminho da pasta na saída e certifique-se de que todas as pastas no caminho existem em seu computador antes de ir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="e31dd-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="e31dd-118">Se estiverem faltando pastas, crie-as.</span><span class="sxs-lookup"><span data-stu-id="e31dd-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="e31dd-119">Execute o seguinte para permitir a instalação do módulo StaffHub do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e31dd-119">Run the following to allow for the installation of the StaffHub PowerShell module:</span></span>

```
Set-ExecutionPolicy RemoteSigned
```

6. <span data-ttu-id="e31dd-120">Execute o seguinte, em &lt;que&gt; Path é o caminho na saída da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="e31dd-120">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="e31dd-121">Por exemplo, o caminho pode se parecer como C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="e31dd-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="e31dd-122">Conectar-se ao módulo do Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="e31dd-122">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="e31dd-123">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e31dd-123">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="e31dd-124">Quando for solicitado, faça logon como um administrador global.</span><span class="sxs-lookup"><span data-stu-id="e31dd-124">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e31dd-125">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e31dd-125">Related topics</span></span>

- [<span data-ttu-id="e31dd-126">Referência do Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="e31dd-126">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="e31dd-127">Mova as suas equipes do Microsoft StaffHub para Turnos no Teams</span><span class="sxs-lookup"><span data-stu-id="e31dd-127">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
