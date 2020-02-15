---
title: 'Lync Server 2013: alterar a URL dos serviços Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 872f971537205826a8927b77563476181f3001c4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="44dc9-102">Alterar a URL de serviços Web no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44dc9-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44dc9-103">_**Última modificação do tópico:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="44dc9-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="44dc9-104">Ao configurar os pools de Front-Ends e os servidores Standard Edition, você tem a opção de configurar um FQDN (nome de domínio totalmente qualificado) de Web farm externo e as portas associadas.</span><span class="sxs-lookup"><span data-stu-id="44dc9-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="44dc9-105">Se você não configurou esta URL quando executou o assistente de implantação do Lync Server, precisará definir manualmente essas configurações.</span><span class="sxs-lookup"><span data-stu-id="44dc9-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="44dc9-106">Um administrador normalmente não precisa alterar essas configurações, pois essas são as portas recomendadas e padrão.</span><span class="sxs-lookup"><span data-stu-id="44dc9-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44dc9-107">A captura de tela a seguir foi feita durante a configuração de um servidor Standard Edition, portanto, a opção substituir FQDN está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="44dc9-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="44dc9-108">Essa opção é habilitada ao configurar um servidor Enterprise Edition em um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="44dc9-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="44dc9-109">![Editar configurações do pool de serviços Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Editar configurações do pool de serviços Web")</span><span class="sxs-lookup"><span data-stu-id="44dc9-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="44dc9-110">Para configurar serviços Web</span><span class="sxs-lookup"><span data-stu-id="44dc9-110">To configure web services</span></span>

1.  <span data-ttu-id="44dc9-111">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="44dc9-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="44dc9-112">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="44dc9-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="44dc9-113">No construtor de topologias, na árvore de console em **servidores front-end Standard Edition**, **pools de front-ends Enterprise Edition**e **pools de diretório**, selecione o nome do pool.</span><span class="sxs-lookup"><span data-stu-id="44dc9-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="44dc9-114">Clique com o botão direito do mouse no nome, clique em **Editar Propriedades** e em **Serviços Web**.</span><span class="sxs-lookup"><span data-stu-id="44dc9-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="44dc9-115">Adicione ou edite o **FQDN de Serviços Web Externos** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="44dc9-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="44dc9-116">Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN de serviços Web externos deverá ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="44dc9-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="44dc9-117">Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="44dc9-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="44dc9-118">Se você também estiver implantando diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deverá ser exclusivo de qualquer outro diretor ou pool de diretores, bem como de qualquer pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="44dc9-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="44dc9-119">Verifique se as portas de escuta e publicadas estão configuradas corretamente para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="44dc9-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="44dc9-120">Repita estas etapas para todos os servidores Standard Edition, Pools de Front-Ends e pools de Diretores em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="44dc9-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="44dc9-121">Na árvore de console, clique em **Lync Server 2013** e, no painel **Ações** clique em **Publicar Topologia**.</span><span class="sxs-lookup"><span data-stu-id="44dc9-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="44dc9-122">Existem alguns requisitos que você deve estar ciente ao configurar as portas de Escuta e Publicação:</span><span class="sxs-lookup"><span data-stu-id="44dc9-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="44dc9-123">As portas de escuta mostradas são as portas configuradas para o IIS (Internet Information Server) em cada Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="44dc9-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="44dc9-p105">As portas de escuta internas e externas devem ser diferentes para o IIS. Para as portas de escuta externas, geralmente são iguais porque uma representa o balanceador de carga de hardware para tráfego da Web interno e a outra representa o servidor proxy inverso para tráfego da Web externo.</span><span class="sxs-lookup"><span data-stu-id="44dc9-p105">The internal and external listening ports must be different for IIS. For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="44dc9-126">Você pode substituir os serviços Web internos em um pool de front-ends, diretor ou um pool de diretor e definir seu próprio FQDN.</span><span class="sxs-lookup"><span data-stu-id="44dc9-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="44dc9-127">Se você decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="44dc9-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="44dc9-128">As portas publicadas devem ser configuradas no balanceador de carga de hardware ou de proxy reverso como portas de escuta.</span><span class="sxs-lookup"><span data-stu-id="44dc9-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="44dc9-p106">Para um pool de Front-End (não mostrado no exemplo), o FQDN do pool SIP interno deve ser diferente do FQDN de serviços Web internos, pois o tráfego da Web passa pelo balanceador de carga de hardware e o tráfego de pool SIP interno passa pelo balanceador de carga de DNS. Este requisito deve ser atendido.</span><span class="sxs-lookup"><span data-stu-id="44dc9-p106">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer. This requirement must be met.</span></span>

  - <span data-ttu-id="44dc9-131">Uma implantação do Lync Server Standard Edition não precisa ou permite que um FQDN de serviços Web internos seja substituído porque esse servidor não pode ser carregado com balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="44dc9-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="44dc9-132">Se você tiver um balanceador de carga de hardware no seu ambiente que você usa para o SIP interno e o tráfego da Web, o construtor de topologias não poderá fazer distinção.</span><span class="sxs-lookup"><span data-stu-id="44dc9-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="44dc9-133">Os FQDNs do serviço Web devem ser facilmente diferenciados uns dos outros; Isso ajuda a garantir que o redirecionamento de URL aponte para os clientes em direção ao servidor apropriado.</span><span class="sxs-lookup"><span data-stu-id="44dc9-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="44dc9-134">Por exemplo, se você tiver dois FQDNs, poderá considerar o nome de um meeting.contoso.com e o outro conferencing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="44dc9-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="44dc9-135">Você pode potencialmente executar problemas de redirecionamento se tiver FQDNs com nomes mais semelhantes, como meet1.contoso.com e meet2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="44dc9-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="44dc9-136">Os serviços Web externos funcionam em conjunto com um proxy reverso na rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="44dc9-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="44dc9-137">Ele fornece aos clientes acesso externo ao usando esses serviços Web.</span><span class="sxs-lookup"><span data-stu-id="44dc9-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="44dc9-138">Os FQDNs configurados aqui são enviados aos clientes quando eles fazem logon e são usados para estabelecer uma conexão HTTPS com o proxy reverso ao conectar remotamente.</span><span class="sxs-lookup"><span data-stu-id="44dc9-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="44dc9-139">O servidor proxy reverso encaminha o FQDN do serviço Web externo para um balanceador de carga de hardware interno ou diretamente para o pool.</span><span class="sxs-lookup"><span data-stu-id="44dc9-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="44dc9-140">O proxy reverso deve ser capaz de resolver o FQDN de serviços Web externos para o endereço IP do servidor Web interno.</span><span class="sxs-lookup"><span data-stu-id="44dc9-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="44dc9-141">O FQDN de serviços Web externos deve ser resolvido na Internet pública.</span><span class="sxs-lookup"><span data-stu-id="44dc9-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="44dc9-142">Se o seu servidor interno for um servidor Standard Edition, o FQDN interno será o FQDN do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="44dc9-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="44dc9-143">Se seu servidor interno for um pool de Front-End, o FQDN será um VIP (IP virtual) do balanceador de carga de hardware que faz o balanceamento de carga dos servidores de Web farm IP virtual (VIP) que o equilíbrio de carga de servidores de web farm internos.</span><span class="sxs-lookup"><span data-stu-id="44dc9-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="44dc9-144">É necessário um balanceador de carga de hardware em um pool de Front-End com mais de um servidor Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="44dc9-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="44dc9-145">Um balanceador de carga não é necessário para um servidor Standard Edition ou um único Servidor Front-End Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="44dc9-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

