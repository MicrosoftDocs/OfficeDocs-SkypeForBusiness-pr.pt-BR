---
title: 'Lync Server 2013: excluir uma política de conferência existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 511f6e9c3b0b4e3caf614fdd00d71fc0ac84e524
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="39b2b-102">Excluir uma política de conferência existente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b2b-102">Delete an existing conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39b2b-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="39b2b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="39b2b-104">Siga estas etapas para excluir uma política de conferência no nível do usuário ou no nível do local.</span><span class="sxs-lookup"><span data-stu-id="39b2b-104">Follow these steps to delete a user-level or a site-level conferencing policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39b2b-105">Você não pode excluir a política global de conferência.</span><span class="sxs-lookup"><span data-stu-id="39b2b-105">You cannot delete the global conferencing policy.</span></span>



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a><span data-ttu-id="39b2b-106">Para excluir uma política de conferência de site ou usuário</span><span class="sxs-lookup"><span data-stu-id="39b2b-106">To delete a site or user conferencing policy</span></span>

1.  <span data-ttu-id="39b2b-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="39b2b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="39b2b-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="39b2b-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="39b2b-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="39b2b-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="39b2b-110">Na barra de navegação esquerda, clique em **Conferência** e em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="39b2b-110">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="39b2b-111">Na lista de políticas de conferência, clique na política de site ou de usuário que deseja excluir, clique em **Editar**e em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="39b2b-111">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="39b2b-112">Removendo políticas de conferência usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39b2b-112">Removing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="39b2b-113">Você pode excluir políticas de conferência usando o Shell de gerenciamento do Lync Server e o cmdlet **Remove-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="39b2b-113">You can delete conferencing policies by using Lync Server Management Shell and the **Remove-CsConferencingPolicy** cmdlet.</span></span> <span data-ttu-id="39b2b-114">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39b2b-114">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="39b2b-115">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="39b2b-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a><span data-ttu-id="39b2b-116">Para remover uma política de conferência especificada</span><span class="sxs-lookup"><span data-stu-id="39b2b-116">To remove a specified conferencing policy</span></span>

  - <span data-ttu-id="39b2b-117">O comando a seguir remove a política de conferência com a identidade RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="39b2b-117">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="39b2b-118">Para remover todas as políticas de conferência aplicadas ao escopo por usuário</span><span class="sxs-lookup"><span data-stu-id="39b2b-118">To remove all of the conferencing policies applied to the per-user scope</span></span>

  - <span data-ttu-id="39b2b-119">O comando a seguir remove todas as políticas de conferência configuradas no escopo por usuário:</span><span class="sxs-lookup"><span data-stu-id="39b2b-119">The following command removes all the conferencing policies configured at the per-user scope:</span></span>
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a><span data-ttu-id="39b2b-120">Para remover todas as políticas de conferência que permitem a gravação por usuários externos</span><span class="sxs-lookup"><span data-stu-id="39b2b-120">To remove all of the conferencing polices that allow recording by external users</span></span>

  - <span data-ttu-id="39b2b-121">O comando a seguir exclui todas as políticas de conferência que permitem que os usuários externos registrem a conferência:</span><span class="sxs-lookup"><span data-stu-id="39b2b-121">The following command deletes any conferencing policies that allow external users to record the conference:</span></span>
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

<span data-ttu-id="39b2b-122">Para obter detalhes, consulte [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span><span class="sxs-lookup"><span data-stu-id="39b2b-122">For details, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

