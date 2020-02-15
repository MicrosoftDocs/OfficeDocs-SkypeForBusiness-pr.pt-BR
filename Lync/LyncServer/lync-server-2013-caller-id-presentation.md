---
title: 'Lync Server 2013: apresentação da ID do chamador'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6962035f5de6b1b3885db3ff31b23058a71bdc4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a><span data-ttu-id="5a811-102">Apresentação da ID de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a811-102">Caller ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a811-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="5a811-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="5a811-104">Com o Lync Server 2010, o número de telefone do participante chamado (ou seja, o número de telefone chamado) pode ser convertido no formato E. 164 no formato de discagem local necessário para o par de troncos (ou seja, o gateway associado, o PBX (central privada de comutação telefônica) ou o tronco SIP).</span><span class="sxs-lookup"><span data-stu-id="5a811-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="5a811-105">Para fazer isso, você deve definir uma ou mais regras de conversão para converter o URI de solicitação antes de roteá-lo para o par de tronco.</span><span class="sxs-lookup"><span data-stu-id="5a811-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="5a811-106">O Lync Server 2013 introduz a opção para também traduzir o número de telefone da pessoa que está chamando (ou seja, o número de telefone que o chamador está chamando) do formato E. 164 para o formato de discagem local exigido pelo par de tronco.</span><span class="sxs-lookup"><span data-stu-id="5a811-106">Lync Server 2013 introduces the option to also translate the calling party’s phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="5a811-107">Por exemplo, você pode criar uma regra de conversão para remover +44 do começo de uma sequência de caracteres de discagem e o substituir por 0144.</span><span class="sxs-lookup"><span data-stu-id="5a811-107">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="5a811-108">**Para configurar a ID de chamadas usando o painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="5a811-108">**To configure Caller ID by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="5a811-109">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5a811-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="5a811-110">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5a811-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="5a811-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a811-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5a811-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5a811-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5a811-113">Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.</span><span class="sxs-lookup"><span data-stu-id="5a811-113">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="5a811-114">Na página **configuração do tronco** , clique duas vezes em um tronco existente (por exemplo, o tronco **global** ) para exibir a caixa de diálogo **Editar configuração do tronco** .</span><span class="sxs-lookup"><span data-stu-id="5a811-114">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

5.  <span data-ttu-id="5a811-115">Para configurar a apresentação da ID de chamadas:</span><span class="sxs-lookup"><span data-stu-id="5a811-115">To configure caller ID presentation:</span></span>
    
      - <span data-ttu-id="5a811-116">Para escolher uma ou mais regras de uma lista de todas as regras de conversão disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="5a811-116">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="5a811-117">Em **regras de conversão de número de chamada**, clique nas regras que você deseja associar ao tronco e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a811-117">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="5a811-118">Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5a811-118">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="5a811-119">Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="5a811-119">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="5a811-120">Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5a811-120">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="5a811-121">Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="5a811-121">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="5a811-122">Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="5a811-122">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="5a811-123">Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="5a811-123">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="5a811-124">Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em \*\*Remover \*\*.</span><span class="sxs-lookup"><span data-stu-id="5a811-124">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="5a811-125">Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="5a811-125">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

