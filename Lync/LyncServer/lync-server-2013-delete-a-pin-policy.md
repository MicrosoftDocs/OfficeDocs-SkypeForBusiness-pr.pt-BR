---
title: 'Lync Server 2013: excluir uma política de PIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 044c8a6ac5d87723a58c1f692c5e969701b72a37
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a><span data-ttu-id="e1ba3-102">Excluir uma política de PIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1ba3-102">Delete a PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1ba3-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e1ba3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e1ba3-104">Siga estas etapas para excluir uma política de PIN (número de identificação pessoal).</span><span class="sxs-lookup"><span data-stu-id="e1ba3-104">Follow these steps to delete a personal identification number (PIN) policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1ba3-105">Não é possível excluir a política PIN global.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a><span data-ttu-id="e1ba3-106">Para excluir uma política de PIN no painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1ba3-106">To delete a PIN policy in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="e1ba3-107">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e1ba3-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e1ba3-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e1ba3-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e1ba3-110">Na barra de navegação esquerda, clique em **Segurança** e em **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="e1ba3-111">Na página **Política de PIN** e no campo de pesquisa, digite o nome todo ou parcial da política que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="e1ba3-112">Na lista de políticas, clique na política que você deseja, em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="e1ba3-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-113">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e1ba3-114">Removendo políticas de PIN usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1ba3-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e1ba3-115">Você pode excluir políticas de PIN usando o Windows PowerShell e o cmdlet Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="e1ba3-116">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e1ba3-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="e1ba3-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="e1ba3-118">Para remover uma política de PIN específica</span><span class="sxs-lookup"><span data-stu-id="e1ba3-118">To remove a specific PIN policy</span></span>

  - <span data-ttu-id="e1ba3-119">Este comando remove a política de PIN com a Identidade RedmondPinPolicy:</span><span class="sxs-lookup"><span data-stu-id="e1ba3-119">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="e1ba3-120">Para remover todas as políticas de PIN aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="e1ba3-120">To remove all the PIN policies applied to the site scope</span></span>

  - <span data-ttu-id="e1ba3-121">Este comando remove todas as políticas de PIN configuradas no escopo do site:</span><span class="sxs-lookup"><span data-stu-id="e1ba3-121">This command removes all the PIN policies configured at the site scope:</span></span>
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="e1ba3-122">Para remover todas as políticas de PIN que permitem o uso de padrões comuns</span><span class="sxs-lookup"><span data-stu-id="e1ba3-122">To remove all the PIN policies that allow the use of common patterns</span></span>

  - <span data-ttu-id="e1ba3-123">Isso remove todas as políticas de PIN que permitem o uso dos padrões comuns:G</span><span class="sxs-lookup"><span data-stu-id="e1ba3-123">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

<span data-ttu-id="e1ba3-124">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) .</span><span class="sxs-lookup"><span data-stu-id="e1ba3-124">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

