---
title: 'Lync Server 2013: excluindo uma política de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cac48287063e61be00495077f51042b1810f65
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="aaa0a-102">Excluindo uma política de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aaa0a-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aaa0a-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="aaa0a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="aaa0a-104">Você pode excluir uma política de usuário ou uma política de site.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="aaa0a-105">A política global não pode ser removida.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-105">The global policy cannot be removed.</span></span> <span data-ttu-id="aaa0a-106">Se você tentar excluir a política global, o Lync Server 2013 redefinirá automaticamente a política para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aaa0a-107">Se você habilitou a integração do Microsoft Exchange para sua implantação, as políticas do Exchange controlarão se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e ter suas caixas de correio colocadas no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="aaa0a-108">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="aaa0a-109">Para excluir uma política de usuário ou site para arquivamento</span><span class="sxs-lookup"><span data-stu-id="aaa0a-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="aaa0a-110">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aaa0a-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aaa0a-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aaa0a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aaa0a-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="aaa0a-114">Na lista de políticas de arquivamento, clique na política de usuário ou site que deseja excluir, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="aaa0a-115">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aaa0a-116">Removendo políticas de arquivamento usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aaa0a-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aaa0a-117">As políticas de arquivamento podem ser excluídas usando o Windows PowerShell e o cmdlet **Remove-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="aaa0a-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="aaa0a-118">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aaa0a-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="aaa0a-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="aaa0a-120">Para remover uma política de arquivamento especificada</span><span class="sxs-lookup"><span data-stu-id="aaa0a-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="aaa0a-p105">Como exemplo, o **Remove-CsArchivingPolicy** exclui a política com a Identidade site:Redmond. Observe que quando uma política configurada no escopo do site é excluída, os usuários gerenciados anteriormente pela política do site irão automaticamente ser governados pela política de arquivamento global. O comando a seguir remove o arquivamento aplicado ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="aaa0a-p105">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond. Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead. The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="aaa0a-124">Para remover todas as políticas de arquivamento aplicadas ao escopo por usuário</span><span class="sxs-lookup"><span data-stu-id="aaa0a-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="aaa0a-125">Este comando remove todas as políticas de arquivamento aplicadas ao escopo por usuário:</span><span class="sxs-lookup"><span data-stu-id="aaa0a-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="aaa0a-126">Para remover todas as políticas de arquivamento que desativam o arquivamento interno</span><span class="sxs-lookup"><span data-stu-id="aaa0a-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="aaa0a-127">Este comando remove todas as políticas de arquivamento onde o arquivamento interno foi desativado:</span><span class="sxs-lookup"><span data-stu-id="aaa0a-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="aaa0a-128">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="aaa0a-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aaa0a-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="aaa0a-129">See Also</span></span>


[<span data-ttu-id="aaa0a-130">Gerenciando o arquivamento de comunicações internas e externas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aaa0a-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

