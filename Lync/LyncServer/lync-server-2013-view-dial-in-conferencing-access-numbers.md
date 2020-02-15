---
title: 'Lync Server 2013: exibir números de acesso de conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 851ac4d48a5242355baa1f25499dcaf26e8ef099
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="d868c-102">Exibir números de acesso de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d868c-102">View dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d868c-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d868c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d868c-104">No painel de controle do Lync Server 2013, você fornece números de acesso de discagem aos usuários para que eles possam ingressar em uma reunião externamente.</span><span class="sxs-lookup"><span data-stu-id="d868c-104">In Lync Server 2013 Control Panel, you provide dial-in access numbers to users so that they can join a meeting externally.</span></span>

<div>

## <a name="to-view-dial-in-access-numbers"></a><span data-ttu-id="d868c-105">Para visualizar números de acesso por discagem</span><span class="sxs-lookup"><span data-stu-id="d868c-105">To view dial-in access numbers</span></span>

1.  <span data-ttu-id="d868c-106">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d868c-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d868c-107">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d868c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d868c-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d868c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d868c-109">Na barra de navegação à esquerda, clique em **Conferência** e, então, em **Número de acesso de discagem**.</span><span class="sxs-lookup"><span data-stu-id="d868c-109">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="d868c-110">Na página **Número de acesso de discagem**, clique no número de acesso que gostaria de visualizar.</span><span class="sxs-lookup"><span data-stu-id="d868c-110">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>

5.  <span data-ttu-id="d868c-p102">Em **Editar**, selecione a caixa de verificação **Exibir detalhes…**.</span><span class="sxs-lookup"><span data-stu-id="d868c-p102">In **Edit**, select the **Show Details…** check box.</span></span>

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d868c-113">Exibindo números de acesso de conferência discada usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d868c-113">Viewing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d868c-114">Os números de acesso de conferência discada podem ser exibidos usando o Windows PowerShell e o cmdlet Get-CsDialInConferencingAccessNumber.</span><span class="sxs-lookup"><span data-stu-id="d868c-114">Dial-in conferencing access numbers can be viewed by using Windows PowerShell and the Get-CsDialInConferencingAccessNumber cmdlet.</span></span> <span data-ttu-id="d868c-115">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d868c-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d868c-116">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="d868c-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="d868c-117">Para exibir os números de acesso de conferência discada</span><span class="sxs-lookup"><span data-stu-id="d868c-117">To view dial-in conferencing access numbers</span></span>

  - <span data-ttu-id="d868c-118">Para exibir informações sobre todos os números de acesso de conferência discada, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="d868c-118">To view information about all your dial-in conferencing access numbers, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsDialInConferencingAccessNumber
    
    <span data-ttu-id="d868c-119">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="d868c-119">That will return information similar to this:</span></span>
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

</div>

<span data-ttu-id="d868c-120">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) .</span><span class="sxs-lookup"><span data-stu-id="d868c-120">For more information, see the help topic for the [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

