---
title: 'Lync Server 2013: problemas com o teste de topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0492f53692230bf02b3b66d91ba7fdf14b01c23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="6b32d-102">Problemas com o teste de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b32d-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b32d-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6b32d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6b32d-104">Assim como o cmdlet **Test-CsTopology** , o analisador de práticas recomendadas fornece uma maneira de verificar se o Lync Server 2013 está funcionando corretamente em um nível global.</span><span class="sxs-lookup"><span data-stu-id="6b32d-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="6b32d-105">Por padrão, o analisador de práticas recomendadas, como o cmdlet, verifica toda a infraestrutura do Lync Server 2013, verificando se os serviços necessários estão em execução e se as permissões e os direitos de usuário adequados foram definidos para esses serviços e para o universal grupos de segurança criados quando você instala o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b32d-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="6b32d-106">Além de verificar a validade do Lync Server como um todo, o **Test-CsTopology** também verifica a validade de um serviço específico.</span><span class="sxs-lookup"><span data-stu-id="6b32d-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="6b32d-107">Para obter detalhes sobre como usar o cmdlet para testar serviços específicos, consulte [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6b32d-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="6b32d-108">Use as informações a seguir para ajudar a solucionar problemas com a sua topologia.</span><span class="sxs-lookup"><span data-stu-id="6b32d-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b32d-109">Dependendo da configuração dos seus servidores de borda e das configurações de rede de perímetro relacionadas, incluindo configurações de firewall e permissões, o analisador de práticas recomendadas pode não conseguir acessar e examinar seus servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="6b32d-109">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers.</span></span> <span data-ttu-id="6b32d-110">Se você incluir servidores de borda na digitalização e os relatórios indicarem que há um problema ao acessar os servidores de borda, desmarque a caixa de seleção <STRONG>servidores de borda</STRONG> e execute a digitalização novamente para impedir que o problema apareça nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="6b32d-110">If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="6b32d-111">Solucionando problemas com a sua topologia</span><span class="sxs-lookup"><span data-stu-id="6b32d-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="6b32d-112">Se o teste de topologia encontrar problemas com a sua topologia, esses problemas provavelmente são causados por problemas que ocorreram quando você publicou ou habilitou sua topologia.</span><span class="sxs-lookup"><span data-stu-id="6b32d-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="6b32d-113">Quando você faz alterações na sua topologia, as alterações só entram em vigor quando foram publicadas e habilitadas.</span><span class="sxs-lookup"><span data-stu-id="6b32d-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="6b32d-114">Você deve usar o construtor de topologias para fazer alterações de topologia.</span><span class="sxs-lookup"><span data-stu-id="6b32d-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="6b32d-115">Depois de fazer as alterações, você pode publicar e habilitar essas alterações usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="6b32d-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="6b32d-116">Quando você publica as alterações, as novas informações (por exemplo, um novo site ou uma nova função de servidor) são gravadas no repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="6b32d-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="6b32d-117">No entanto, esses objetos novos (ou os recém modificados) não se unem imediatamente à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="6b32d-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="6b32d-118">Os objetos entram em sua topologia somente quando você habilita a topologia atualizada.</span><span class="sxs-lookup"><span data-stu-id="6b32d-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="6b32d-119">Se você selecionar a opção publicar no construtor de topologia, essas duas etapas ocorrerão: as alterações serão publicadas (isto é, serão gravadas no repositório de gerenciamento central) e a nova topologia será habilitada.</span><span class="sxs-lookup"><span data-stu-id="6b32d-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="6b32d-120">Por padrão, os membros do grupo RTCUniversalServerAdmins são autorizados a executar o cmdlet **Publish-CsTopology** e o cmdlet **Enable-CsTopology** .</span><span class="sxs-lookup"><span data-stu-id="6b32d-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="6b32d-121">No entanto, se as permissões de configuração não tiverem sido delegadas, você deverá estar conectado como um administrador de domínio para executar **Publish-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="6b32d-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="6b32d-122">Para dar à RTCUniversalServerAdmins o direito de realmente usar o cmdlet **Publish-CsTopology** , você deve executar o cmdlet **Grant-CsSetupPermission** em cada contêiner do Active Directory que contém computadores que executam serviços do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6b32d-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="6b32d-123">Para dar à RTCUniversalServerAdmins o direito de usar o cmdlet **Enable-CsTopology** , você deve executar o cmdlet **set-CsSetupPermission** em todos os contêineres de serviços de domínio Active Directory que contenham computadores executando os serviços do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6b32d-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="6b32d-124">Observe que isso se aplica à habilitação e publicação de uma topologia usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="6b32d-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="6b32d-125">Se você não tiver delegado permissões usando **set-CsSetupPermission**, apenas um administrador de domínio poderá habilitar e publicar uma topologia por meio do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="6b32d-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

