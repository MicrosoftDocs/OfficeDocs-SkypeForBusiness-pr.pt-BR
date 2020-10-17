---
title: 'Lync Server 2013: problemas com o teste de topologia'
description: 'Lync Server 2013: problemas com o teste de topologia.'
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
ms.openlocfilehash: 2a0f24942844bcf371eff94ee04c8faafcf513d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554437"
---
# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="69f09-103">Problemas com o teste de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69f09-103">Issues with the topology test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69f09-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="69f09-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="69f09-105">Como o cmdlet **Test-CsTopology** , o analisador de práticas recomendadas oferece uma maneira de verificar se o Lync Server 2013 está funcionando corretamente em um nível global.</span><span class="sxs-lookup"><span data-stu-id="69f09-105">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="69f09-106">Por padrão, o analisador de práticas recomendadas, como o cmdlet, verifica toda a sua infraestrutura do Lync Server 2013, verificando se os serviços necessários estão em execução e se os direitos e permissões de usuário adequados foram definidos para esses serviços e para os grupos de segurança universal criados quando você instala o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69f09-106">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="69f09-107">Além de verificar a validade do Lync Server como um todo, o **Test-CsTopology** também verifica a validade de um serviço específico.</span><span class="sxs-lookup"><span data-stu-id="69f09-107">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="69f09-108">Para obter detalhes sobre como usar o cmdlet para testar serviços específicos, consulte [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69f09-108">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="69f09-109">Use as informações a seguir para ajudar a resolver problemas com sua topologia.</span><span class="sxs-lookup"><span data-stu-id="69f09-109">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69f09-p103">Dependendo da configurçaão de seus servidores de borda e quasquer definições de rede de perímetro relacionada, incluindo de firewall e permissões, o Analisar de Práticas Recomendadas pode não conseguir acessar e escanear seus servidores de borda. Se incluir servidores de borda no escaneamento e os relatórios indicarem que há um problema no acesso aos servidores de borda, remova a seleção da caixa <STRONG>Servidores de Borda</STRONG> e execute o scan novamente para evitar que o problema conste nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="69f09-p103">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers. If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="69f09-112">Resolver problemas com sua topologia</span><span class="sxs-lookup"><span data-stu-id="69f09-112">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="69f09-113">Se o teste de topologia encontrar problemas com sua topologia, esses problemas são provavelmente causados por problemas que ocorreram quando você publicou ou habilitou sua topologia.</span><span class="sxs-lookup"><span data-stu-id="69f09-113">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="69f09-114">Ao fazer modificações em sua topologia, elas entrarão em efeito somente quando forem publicadas e habilitadas.</span><span class="sxs-lookup"><span data-stu-id="69f09-114">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="69f09-115">Você deve usar o construtor de topologias para fazer alterações na topologia.</span><span class="sxs-lookup"><span data-stu-id="69f09-115">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="69f09-116">Após fazer as alterações, você pode publicar e habilitar essas alterações usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="69f09-116">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="69f09-117">Quando você publica as alterações, as novas informações (por exemplo, um novo site ou uma nova função de servidor) são gravadas no repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="69f09-117">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="69f09-118">Contudo, esses novos (ou recém-modificados) objetos não entrarão imediatamente em sua topologia.</span><span class="sxs-lookup"><span data-stu-id="69f09-118">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="69f09-119">Os objetivos entram em sua topologia somente quando você permite a atualização da topologia.</span><span class="sxs-lookup"><span data-stu-id="69f09-119">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="69f09-120">Se você selecionar a opção publicar no construtor de topologia, essas duas etapas ocorrerão: as alterações serão publicadas (ou seja, serão gravadas no repositório de gerenciamento central) e, em seguida, a nova topologia será habilitada.</span><span class="sxs-lookup"><span data-stu-id="69f09-120">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="69f09-121">Por padrão, membros do grupo RTCUniversalServerAdmins estão autorizados a executar os cmdlets **Publish-CsTopology** e **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="69f09-121">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="69f09-122">Contudo, se permissões de configuração não foram delegadas, você estar logado como administrador do domínio para executar **Publish-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="69f09-122">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="69f09-123">Para dar ao RTCUniversalServerAdmins o direito de realmente usar o cmdlet **Publish-CsTopology** , você deve executar o cmdlet **Grant-CsSetupPermission** em todos os contêineres do Active Directory que contenham computadores executando os serviços do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69f09-123">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="69f09-124">Para dar ao RTCUniversalServerAdmins o direito de usar o cmdlet **Enable-CsTopology** , você deve executar o cmdlet **set-CsSetupPermission** em todos os contêineres de serviços de domínio do Active Directory que contenham computadores que executam os serviços do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69f09-124">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="69f09-125">Observe que isso se aplica à habilitação e publicação de uma topologia usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="69f09-125">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="69f09-126">Se você não tiver delegado permissões usando **set-CsSetupPermission**, somente um administrador de domínio poderá habilitar e publicar uma topologia por meio do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="69f09-126">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

