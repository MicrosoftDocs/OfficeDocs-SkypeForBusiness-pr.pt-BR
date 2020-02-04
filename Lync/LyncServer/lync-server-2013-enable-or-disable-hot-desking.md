---
title: 'Lync Server 2013: habilitar ou desabilitar o hot desk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c56d7ae13be9afa3af7e4732242a86f4be4c458
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="68244-102">Habilitar ou desabilitar o hot desk no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68244-102">Enable or disable hot desking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68244-103">_**Tópico da última modificação:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="68244-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="68244-104">Você pode configurar telefones de área comuns como *telefones de mesa ativa*.</span><span class="sxs-lookup"><span data-stu-id="68244-104">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="68244-105">Com telefones de mesa ativa, os usuários podem fazer logon em sua própria conta de usuário e, depois de conectados, usar os recursos do Lync Server e suas próprias configurações de perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="68244-105">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="68244-106">A divisão de acesso é gerenciada usando políticas de cliente: para habilitar ou desabilitar o uso de redes de mesa, você precisa modificar as políticas de cliente que são usadas pelos seus telefones comuns.</span><span class="sxs-lookup"><span data-stu-id="68244-106">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="68244-107">Para obter detalhes sobre como determinar as políticas de conferência que foram atribuídas a seus telefones de área comuns, consulte [Exibir informações de telefone de área comum no Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span><span class="sxs-lookup"><span data-stu-id="68244-107">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="68244-108">Você usa o parâmetro EnableHotdesking do cmdlet **New-CSClientPolicy** ou o cmdlet **set-CSClientPolicy** para habilitar ou desabilitar o uso de uma mesa em um telefone, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="68244-108">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="68244-109">Execute esses cmdlets a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68244-109">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="68244-110">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="68244-110">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="68244-111">Habilitando o acesso à mesa</span><span class="sxs-lookup"><span data-stu-id="68244-111">Enabling hot desking</span></span>

  - <span data-ttu-id="68244-112">Para habilitar o hot desk para um telefone de mesa comum, você deve modificar a política de cliente que foi atribuída a esse telefone (ou conjunto de telefones).</span><span class="sxs-lookup"><span data-stu-id="68244-112">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="68244-113">Depois de ter identificado a política que precisa ser modificada, a próxima etapa é usar o cmdlet **set-CsClientPolicy** para definir o parâmetro EnableHotdesking como true.</span><span class="sxs-lookup"><span data-stu-id="68244-113">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="68244-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68244-114">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="68244-115">Ou, se preferir, você pode usar o cmdlet **New-CsClientPolicy** para criar uma nova política de cliente que permite o uso de mesas de acesso.</span><span class="sxs-lookup"><span data-stu-id="68244-115">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="68244-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68244-116">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68244-117">Após a criação da política, você deve atribuí-la aos telefones de área comuns apropriados.</span><span class="sxs-lookup"><span data-stu-id="68244-117">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="68244-118">Para obter detalhes, consulte <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">atribuir políticas no Lync Server 2013 a um telefone de área comum</A>.</span><span class="sxs-lookup"><span data-stu-id="68244-118">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="68244-119">Desativando o hot desk</span><span class="sxs-lookup"><span data-stu-id="68244-119">Disabling hot desking</span></span>

  - <span data-ttu-id="68244-120">Para desativar o hot desk para um telefone de área comum, redefina o parâmetro EnableHotdesking do cmdlet **set-CsClientPolicy** como o valor padrão de false.</span><span class="sxs-lookup"><span data-stu-id="68244-120">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="68244-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68244-121">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="68244-122">Para obter detalhes, consulte os tópicos da ajuda para o cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="68244-122">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

