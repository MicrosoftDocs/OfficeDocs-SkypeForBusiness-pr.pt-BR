---
title: 'Lync Server 2013: Exibir regras de política de versão do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b43075fbd730134a9076273009714b682692994
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a><span data-ttu-id="8cfcf-102">Exibir regras de política de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cfcf-102">View client version policy rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cfcf-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8cfcf-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8cfcf-104">Uma política de versão do cliente é composta por um conjunto de regras de política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="8cfcf-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="8cfcf-105">Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.</span><span class="sxs-lookup"><span data-stu-id="8cfcf-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="8cfcf-106">Você pode exibir as regras de política de versão do cliente no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8cfcf-106">You can view client version policy rules from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="8cfcf-107">Para exibir as regras de política de versão do cliente usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="8cfcf-107">To view client version policy rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8cfcf-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8cfcf-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8cfcf-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8cfcf-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8cfcf-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8cfcf-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8cfcf-111">Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **política de versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="8cfcf-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="8cfcf-112">Na página **política de versão do cliente** , clique duas vezes em uma política de versão do cliente que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="8cfcf-112">On the **Client Version Policy** page, double-click a client version policy you want to view.</span></span>

5.  <span data-ttu-id="8cfcf-113">As regras são exibidas na página **Editar política de versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="8cfcf-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="8cfcf-114">Para exibir os detalhes de uma regra, selecione a regra e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="8cfcf-114">To view the details for a rule, select the rule, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8cfcf-115">Exibindo regras de política de versão de cliente usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cfcf-115">Viewing Client Version Policy Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8cfcf-116">Você pode exibir regras de política de versão de cliente usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsClientVersionPolicyRule** .</span><span class="sxs-lookup"><span data-stu-id="8cfcf-116">You can view client version policy rules by using Lync Server Management Shell and the **Get-CsClientVersionPolicyRule** cmdlet.</span></span> <span data-ttu-id="8cfcf-117">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cfcf-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8cfcf-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="8cfcf-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policy-rules"></a><span data-ttu-id="8cfcf-119">Para exibir as regras de política de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="8cfcf-119">To view client version policy rules</span></span>

  - <span data-ttu-id="8cfcf-120">Para exibir as regras de política de versão do cliente, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="8cfcf-120">To view the client version policy rules, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicyRule
    
    <span data-ttu-id="8cfcf-121">Isso retornará informações semelhantes a estas para cada regra configurada:</span><span class="sxs-lookup"><span data-stu-id="8cfcf-121">That will return information similar to this for each configured rule:</span></span>
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

<span data-ttu-id="8cfcf-122">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) .</span><span class="sxs-lookup"><span data-stu-id="8cfcf-122">For details, see the help topic for the [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

