---
title: 'Lync Server 2013: exibir informações de política de PIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f73d3ccf2ebf1083b834ab711ae43f582063520c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518448"
---
# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a><span data-ttu-id="317c6-102">Exibir informações de política de PIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="317c6-102">View PIN policy inforrmation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="317c6-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="317c6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="317c6-104">Você pode usar a guia **política de PIN** para exibir a autenticação de PIN (número de identificação pessoal) de usuários que estão se conectando ao Lync 2013 com telefones IP.</span><span class="sxs-lookup"><span data-stu-id="317c6-104">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="317c6-105">Para usar a autenticação PIN, certifique-se de que **Habilitar Autenticação PIN** esteja selecionado nas configurações do Web Service.</span><span class="sxs-lookup"><span data-stu-id="317c6-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="317c6-106">Para obter detalhes, consulte [Modificar definições de configuração do serviço da Web existente no Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="317c6-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="317c6-107">Siga estas etapas para modificar uma política de PIN de nível do usuário ou nível local.</span><span class="sxs-lookup"><span data-stu-id="317c6-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a><span data-ttu-id="317c6-108">Para exibir informações sobre uma política de PIN no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="317c6-108">To view information about a PIN policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="317c6-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="317c6-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="317c6-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="317c6-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="317c6-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="317c6-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="317c6-112">Na barra de navegação esquerda, clique em **Segurança** e em **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="317c6-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="317c6-113">Na página **Política de PIN**, clique em uma política, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="317c6-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="317c6-114">Exibindo políticas de PIN usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="317c6-114">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="317c6-115">Você também pode exibir políticas de PIN usando o Windows PowerShell e o cmdlet Get-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="317c6-115">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="317c6-116">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="317c6-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="317c6-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="317c6-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pin-policies"></a><span data-ttu-id="317c6-118">Para exibir políticas de PIN</span><span class="sxs-lookup"><span data-stu-id="317c6-118">To view PIN policies</span></span>

  - <span data-ttu-id="317c6-119">Para exibir informações sobre todas as suas políticas de PIN, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="317c6-119">To view information about all your PIN policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPinPolicy
    
    <span data-ttu-id="317c6-120">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="317c6-120">That will return information similar to this:</span></span>
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

<span data-ttu-id="317c6-121">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) .</span><span class="sxs-lookup"><span data-stu-id="317c6-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="317c6-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="317c6-122">See Also</span></span>


[<span data-ttu-id="317c6-123">Modificar definições de configuração do serviço Web existente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="317c6-123">Modify existing Web Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[<span data-ttu-id="317c6-124">Criar uma nova política de PIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="317c6-124">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

