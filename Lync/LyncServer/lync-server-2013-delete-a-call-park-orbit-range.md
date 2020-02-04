---
title: 'Lync Server 2013: excluir um conjunto de órbitas de estacionamento de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Call Park orbit range
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182546(v=OCS.15)
ms:contentKeyID: 48184713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934559f1b67c1325684ee5b477be18ed112224df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="d9077-102">Excluir uma faixa de opções do parque de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9077-102">Delete a Call Park orbit range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9077-103">_**Tópico da última modificação:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="d9077-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="d9077-104">Use um dos procedimentos a seguir para excluir um intervalo de linha de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="d9077-104">Use one of the following procedures to delete a Call Park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="d9077-105">Para usar o painel de controle do Lync Server para excluir um intervalo de linha de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="d9077-105">To use Lync Server Control Panel to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="d9077-106">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d9077-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d9077-107">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d9077-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d9077-108">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9077-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9077-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d9077-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d9077-110">Na barra de navegação esquerda, clique em **Recursos de Voz** e em **Estacionamento de Chamada(Call Park)**.</span><span class="sxs-lookup"><span data-stu-id="d9077-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="d9077-111">Na página **estacionamento de chamada** , no campo de pesquisa, digite todo ou parte do nome do intervalo de órbita que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="d9077-111">On the **Call Park** page, in the search field, type all or part of the name of the orbit range that you want to delete.</span></span>

5.  <span data-ttu-id="d9077-112">Na lista resultante de órbitas, clique em órbita, clique em **Editar**e, em seguida, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="d9077-112">In the resulting list of orbits, click the orbit, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="d9077-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9077-113">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="d9077-114">Para usar o Windows PowerShell para excluir um intervalo de linha de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="d9077-114">To use Windows PowerShell to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="d9077-115">Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d9077-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d9077-116">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d9077-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d9077-117">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="d9077-117">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    <span data-ttu-id="d9077-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d9077-118">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9077-119">Para obter detalhes sobre mais opções, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span><span class="sxs-lookup"><span data-stu-id="d9077-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9077-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="d9077-120">See Also</span></span>


[<span data-ttu-id="d9077-121">Criar ou modificar uma faixa de opções do parque de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9077-121">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="d9077-122">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="d9077-122">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="d9077-123">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="d9077-123">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

