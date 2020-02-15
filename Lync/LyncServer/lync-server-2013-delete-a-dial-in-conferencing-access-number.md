---
title: 'Lync Server 2013: excluir um número de acesso de conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 365c26221c040b1fae0bafb0221658b9b068609f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="7bb33-102">Excluir um número de acesso de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bb33-102">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bb33-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7bb33-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7bb33-104">Siga estas etapas para excluir um número de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="7bb33-104">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="7bb33-105">Exclusão de um número de acesso de conferências discadas</span><span class="sxs-lookup"><span data-stu-id="7bb33-105">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="7bb33-106">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7bb33-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="7bb33-107">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7bb33-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7bb33-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7bb33-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7bb33-109">Na barra de navegação à esquerda, clique em **Conferências**, e então em **Número de acesso discado**.</span><span class="sxs-lookup"><span data-stu-id="7bb33-109">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="7bb33-110">Na página, clique no número de discagem que deseja excluir da lista, clique em **Editar** e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="7bb33-110">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="7bb33-111">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7bb33-111">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7bb33-112">Removendo números de acesso de conferência discada usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7bb33-112">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7bb33-113">Os números de acesso de conferência discada podem ser excluídos usando o Windows PowerShell e o cmdlet **Remove-CsDialInConferencingAccessNumber** .</span><span class="sxs-lookup"><span data-stu-id="7bb33-113">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="7bb33-114">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7bb33-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7bb33-115">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="7bb33-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="7bb33-116">Para remover um número de acesso de conferência discada específico</span><span class="sxs-lookup"><span data-stu-id="7bb33-116">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="7bb33-117">Este comando exclui o número de acesso de conferência discada com o SIP de Identidade:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="7bb33-117">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="7bb33-118">Para remover todos os números de acesso de conferência discada atribuídos a uma região específica</span><span class="sxs-lookup"><span data-stu-id="7bb33-118">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="7bb33-119">Este comando exclui todos os números de acesso de conferência discada associados com a região Noroeste:</span><span class="sxs-lookup"><span data-stu-id="7bb33-119">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="7bb33-120">Para remover os números de acesso de conferência discada com base no idioma principal</span><span class="sxs-lookup"><span data-stu-id="7bb33-120">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="7bb33-121">Este comando exclui todos os números de acesso de conferência discada em que italiano é o idioma principal:</span><span class="sxs-lookup"><span data-stu-id="7bb33-121">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="7bb33-122">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .</span><span class="sxs-lookup"><span data-stu-id="7bb33-122">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

