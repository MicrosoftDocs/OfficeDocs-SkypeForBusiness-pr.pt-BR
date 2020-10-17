---
title: 'Lync Server 2013: excluir uma política de site ou de usuário para acesso de usuário externo'
description: 'Lync Server 2013: excluir uma política de site ou de usuário para acesso de usuário externo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aac81e7b50603e5eb80cde8877cdc06f138d872
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553707"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="0a308-103">Excluir uma política de site ou de usuário para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a308-103">Delete a site or user policy for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a308-104">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0a308-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0a308-105">Você pode excluir qualquer política de site ou de usuário que esteja listada no painel de controle do Lync Server na página **política de acesso externo** .</span><span class="sxs-lookup"><span data-stu-id="0a308-105">You can delete any site or user policy that is listed in Lync Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="0a308-106">Excluir a política global não causa sua exclusão propriamente dita, mas apenas a redefine para suas configurações padrão, que não incluem suporte para nenhuma opção de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="0a308-106">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="0a308-107">Para obter detalhes sobre como redefinir a política global, consulte [Reset The Global Policy for External User Access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0a308-107">For details about resetting the global policy, see [Reset the global policy for external user access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span></span>

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="0a308-108">Para excluir uma política de site ou de usuário para o acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="0a308-108">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="0a308-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="0a308-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a308-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a308-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0a308-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a308-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0a308-112">Clique em **Acesso de Usuário Externo**, em **Política de Acesso Externo**.</span><span class="sxs-lookup"><span data-stu-id="0a308-112">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="0a308-113">Na guia **Política de Acesso Externo**, clique na política de site ou de usuário que deseja excluir, clique em **Editar**e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0a308-113">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="0a308-114">Quando for solicitado que você confirme a exclusão, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a308-114">When prompted to confirm the deletion, click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0a308-115">Removendo políticas de PIN usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a308-115">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0a308-116">As políticas de acesso externo podem ser excluídas usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="0a308-116">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="0a308-117">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a308-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0a308-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="0a308-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="0a308-119">Para remover uma política de acesso externo específica</span><span class="sxs-lookup"><span data-stu-id="0a308-119">To remove a specific external access policy</span></span>

  - <span data-ttu-id="0a308-120">Este comando remove a política de acesso externo aplicada ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="0a308-120">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="0a308-121">Para remover todas as políticas de acesso externo aplicadas ao escopo por usuário</span><span class="sxs-lookup"><span data-stu-id="0a308-121">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="0a308-122">Este comando remove todas as políticas de acesso externo configuradas no escopo por usuário:</span><span class="sxs-lookup"><span data-stu-id="0a308-122">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="0a308-123">Para remover todas as políticas de acesso externo onde o acesso de usuário externo está desabilitado</span><span class="sxs-lookup"><span data-stu-id="0a308-123">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="0a308-124">Este comando exclui todas as políticas de acesso externo com acesso de usuário externo desabilitado:</span><span class="sxs-lookup"><span data-stu-id="0a308-124">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

<span data-ttu-id="0a308-125">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="0a308-125">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

