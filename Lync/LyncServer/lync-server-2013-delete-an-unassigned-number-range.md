---
title: 'Lync Server 2013: excluir um intervalo numérico não atribuído'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8bf1bcea1a2f84def783b833d232a44282cab6b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="9274f-102">Excluir um intervalo de números não atribuído no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9274f-102">Delete an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9274f-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9274f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9274f-104">Use um dos procedimentos a seguir para excluir um intervalo de números não atribuído para anúncios.</span><span class="sxs-lookup"><span data-stu-id="9274f-104">Use one of the following procedures to delete an unassigned number range for Announcements.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="9274f-105">Para usar o painel de controle do Lync Server para excluir um intervalo numérico não atribuído</span><span class="sxs-lookup"><span data-stu-id="9274f-105">To use Lync Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="9274f-106">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9274f-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9274f-107">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9274f-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9274f-108">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9274f-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9274f-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9274f-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9274f-110">Na barra de navegação à esquerda, clique em **Recursos de Voz** e depois, em **Número Não Atribuído**.</span><span class="sxs-lookup"><span data-stu-id="9274f-110">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="9274f-111">Na página **Número Não Atribuído**, no campo de pesquisa, digite todo ou parte do nome do intervalo numérico não atribuído que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="9274f-111">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>

5.  <span data-ttu-id="9274f-112">Na lista de resultados de intervalos de número, clique no nome, clique em **Editar** e depois, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="9274f-112">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="9274f-113">Clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="9274f-113">Click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="9274f-114">Para usar o Windows PowerShell para excluir um intervalo numérico não atribuído</span><span class="sxs-lookup"><span data-stu-id="9274f-114">To use Windows PowerShell to delete an unassigned number range</span></span>

1.  <span data-ttu-id="9274f-115">Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9274f-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9274f-116">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9274f-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9274f-117">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="9274f-117">At the command line, type:</span></span>
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    <span data-ttu-id="9274f-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9274f-118">For example:</span></span>
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9274f-119">Para obter detalhes sobre mais opções, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span><span class="sxs-lookup"><span data-stu-id="9274f-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9274f-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="9274f-120">See Also</span></span>


[<span data-ttu-id="9274f-121">Criar ou modificar um intervalo de números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9274f-121">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[<span data-ttu-id="9274f-122">Remove-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="9274f-122">Remove-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[<span data-ttu-id="9274f-123">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="9274f-123">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

