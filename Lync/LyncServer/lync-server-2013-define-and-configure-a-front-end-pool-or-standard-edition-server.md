---
title: Definir e configurar um pool de front-ends ou servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 847aeda66657b2bd665964d6fec3276dc22807ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531508"
---
# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="6c2c0-102">Definir e configurar um pool Front-end ou um servidor Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2c0-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c2c0-103">_**Última modificação do tópico:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="6c2c0-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="6c2c0-p101">Este procedimento não exige associação a um grupo de administradores locais ou de domínio privilegiado. Você deve fazer logon em um computador como usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="6c2c0-106">Se você estiver implantando um servidor corporativo, um número mínimo de servidores front-end em um pool deve estar sempre em execução.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="6c2c0-107">A tabela a seguir resume esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c2c0-108">Número total de servidores front-end em um pool</span><span class="sxs-lookup"><span data-stu-id="6c2c0-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="6c2c0-109">Número de servidores que devem estar em execução para o pool ser funcional</span><span class="sxs-lookup"><span data-stu-id="6c2c0-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c2c0-110">1-2</span><span class="sxs-lookup"><span data-stu-id="6c2c0-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="6c2c0-111">1</span><span class="sxs-lookup"><span data-stu-id="6c2c0-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c2c0-112">3-4</span><span class="sxs-lookup"><span data-stu-id="6c2c0-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="6c2c0-113">duas</span><span class="sxs-lookup"><span data-stu-id="6c2c0-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c2c0-114">5-6</span><span class="sxs-lookup"><span data-stu-id="6c2c0-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="6c2c0-115">3D</span><span class="sxs-lookup"><span data-stu-id="6c2c0-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c2c0-116">7-8</span><span class="sxs-lookup"><span data-stu-id="6c2c0-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="6c2c0-117">4 </span><span class="sxs-lookup"><span data-stu-id="6c2c0-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c2c0-118">9-10</span><span class="sxs-lookup"><span data-stu-id="6c2c0-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="6c2c0-119">5 </span><span class="sxs-lookup"><span data-stu-id="6c2c0-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c2c0-120">11-12</span><span class="sxs-lookup"><span data-stu-id="6c2c0-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="6c2c0-121">6 </span><span class="sxs-lookup"><span data-stu-id="6c2c0-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="6c2c0-122">Para o Lync Server 2013, sempre que você adicionar ou remover um servidor front-end do pool, você deve reiniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="6c2c0-123">A remoção e adição de servidores devem ser feitas como operações separadas.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="6c2c0-124">Por exemplo, se você for adicionar dois servidores front-end e remover dois servidores front-end, use o seguinte processo:</span><span class="sxs-lookup"><span data-stu-id="6c2c0-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="6c2c0-125">Remova os dois servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="6c2c0-126">Publique e reative a topologia.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="6c2c0-127">Reinicie os serviços</span><span class="sxs-lookup"><span data-stu-id="6c2c0-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="6c2c0-128">Adicione os dois servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="6c2c0-129">Publique e reative a topologia.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="6c2c0-130">Reinicie os serviços.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="6c2c0-131">Após ter definido sua topologia, use o procedimento a seguir para definir um pool de front-ends para o site.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="6c2c0-132">Para obter detalhes sobre como definir a topologia, consulte [definir e configurar uma topologia no construtor de topologias para o Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="6c2c0-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="6c2c0-133">Para definir um pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="6c2c0-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="6c2c0-134">No Assistente para Definir Novo Pool de Front-Ends, na página **Defina um Novo Pool de Front-Ends**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="6c2c0-135">Na página **definir o FQDN do pool de front-ends** , digite um FQDN (nome de domínio totalmente qualificado) para o pool que você está criando, clique em **pool de front-ends Enterprise Edition**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="6c2c0-136">Na página **definir os computadores neste pool** , digite um FQDN de computador para o primeiro servidor front-end no pool e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="6c2c0-137">Repita essa etapa para todos os computadores adicionais (até doze) que você deseja adicionar ao pool e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="6c2c0-138">Na página **Selecionar recursos**, marque as caixas de seleção para os recursos que você deseja neste pool de Front-Ends.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="6c2c0-139">Por exemplo, se você estiver implantando apenas recursos de mensagens instantâneas (IM) e presença, marque a caixa de seleção **conferência** para permitir mensagens instantâneas com vários participantes, mas não selecionaria as caixas de seleção **conferência de discagem (PSTN)**, **Enterprise Voice**ou **controle de admissão de chamada** , pois representam recursos de voz, vídeo e conferência colaborativa.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="6c2c0-140">**Conferência**     Essa seleção permite um conjunto avançado de recursos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="6c2c0-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="6c2c0-141">IM com mais de duas partes em uma sessão de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="6c2c0-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="6c2c0-142">Conferência, que inclui a colaboração de documento, o compartilhamento de aplicativo e o compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="6c2c0-143">Conferência a/V, que permite que os usuários tenham conferências de áudio/vídeo (A/V) em tempo real sem a necessidade de serviços externos, como o serviço Live Meeting ou uma ponte de áudio de terceiros.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="6c2c0-144">Conferência discada **(PSTN)**     Permite que os usuários ingressem na parte de áudio de uma conferência do Lync Server 2013 usando um telefone PSTN (rede telefônica pública comutada) sem exigir um provedor de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="6c2c0-145">**Enterprise Voice**     O Enterprise Voice é a solução de voz sobre IP (VoIP) no Lync Server 2013 que permite que os usuários façam e recebam chamadas telefônicas.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="6c2c0-146">Você implantaria esse recurso se planeja usar o Lync Server 2013 para chamadas de voz, caixa postal e outras funções que usam um dispositivo de hardware ou um cliente de software.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="6c2c0-147">**Controle de admissão de chamadas (CAC)**     O CAC determina, com base na largura de banda de rede disponível, se permitirá sessões de comunicação em tempo real, como chamadas de voz ou vídeo a serem estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="6c2c0-148">Se você implantou apenas IM e presença, o CAC não é necessário porque nenhum destes dois recursos usam o CAC.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="6c2c0-149">**Arquivamento**     O arquivamento oferece uma maneira de arquivar conteúdo de IM, de conferência (reunião) ou ambos enviados por meio do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="6c2c0-150">**Monitoramento**     O Monitoring Server permite coletar dados numéricos que descrevem a qualidade de mídia em sua rede e pontos de extremidade, informações de uso relacionadas a chamadas de VoIP, mensagens de IM, conversas de A/V, reuniões, compartilhamento de aplicativos e transferências de arquivos, e informações de erro e de solução de problemas para chamadas com falha.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6c2c0-p109">Se você deseja habilitar o CAC na implantação, é necessário habilitar o CAC em exatamente um pool por site central. O CAC é recomendado se você está implantando os recursos de voz ou conferência de A/V.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-p109">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site. CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="6c2c0-p110">A tabela a seguir mostra os recursos disponíveis (superior) e as funções oferecidas aos usuários (esquerdo). As seleções na tabela são aquelas que você deve selecionar para habilitar estes recursos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-p110">The following table shows the available features (top) and the functions offered to users (left). The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th><span data-ttu-id="6c2c0-155">Conferências</span><span class="sxs-lookup"><span data-stu-id="6c2c0-155">Conferencing</span></span></th>
    <th><span data-ttu-id="6c2c0-156">Conferência discada</span><span class="sxs-lookup"><span data-stu-id="6c2c0-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="6c2c0-157">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="6c2c0-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="6c2c0-158">Serviço de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="6c2c0-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="6c2c0-159">Sistema de mensagens instantâneas e presença</span><span class="sxs-lookup"><span data-stu-id="6c2c0-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="6c2c0-160">X</span><span class="sxs-lookup"><span data-stu-id="6c2c0-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6c2c0-161">Conferências</span><span class="sxs-lookup"><span data-stu-id="6c2c0-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="6c2c0-162">X</span><span class="sxs-lookup"><span data-stu-id="6c2c0-162">X</span></span></p></td>
    <td><p><span data-ttu-id="6c2c0-163">X</span><span class="sxs-lookup"><span data-stu-id="6c2c0-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6c2c0-164">Conferências A/V</span><span class="sxs-lookup"><span data-stu-id="6c2c0-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="6c2c0-165">X</span><span class="sxs-lookup"><span data-stu-id="6c2c0-165">X</span></span></p></td>
    <td><p><span data-ttu-id="6c2c0-166">X</span><span class="sxs-lookup"><span data-stu-id="6c2c0-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="6c2c0-167">X</span><span class="sxs-lookup"><span data-stu-id="6c2c0-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6c2c0-168">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="6c2c0-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="6c2c0-169">X</span><span class="sxs-lookup"><span data-stu-id="6c2c0-169">X</span></span></p></td>
    <td><p><span data-ttu-id="6c2c0-170">X</span><span class="sxs-lookup"><span data-stu-id="6c2c0-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="6c2c0-171">Na página **selecionar funções de servidor posicionadas** , você pode colocar o servidor de mediação no servidor front-end ou implantá-lo como um servidor autônomo.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="6c2c0-172">Você pode colocar o servidor de mediação no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="6c2c0-173">Se você pretende colocar o servidor de mediação no pool de front-ends Enterprise Edition, verifique se a caixa de seleção está marcada.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="6c2c0-174">As funções de servidor serão implantadas nos servidores do pool.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="6c2c0-175">Se você pretende implantar o servidor de mediação como um servidor autônomo, desmarque a caixa de seleção apropriada.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="6c2c0-176">Você implantará o servidor de mediação em uma etapa de implantação separada após a implantação completa do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6c2c0-177">Recomendamos colocar o servidor de mediação, se possível.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="6c2c0-178">Para obter detalhes sobre o suporte a servidores de mediação posicionados ou autônomos, consulte <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologias for Mediation Server in Lync server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="6c2c0-179">A página **associar funções de servidor a este pool de front-ends** permite definir e associar funções de servidor ao pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="6c2c0-180">A seguinte função está disponível:</span><span class="sxs-lookup"><span data-stu-id="6c2c0-180">The following role is available:</span></span>
    
    <span data-ttu-id="6c2c0-181">**Habilitar um pool**     de borda Define e associa um único servidor de borda ou um pool de servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="6c2c0-182">Um servidor de borda facilita a comunicação e a colaboração entre usuários dentro da organização e pessoas de fora da organização, incluindo usuários federados.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="6c2c0-183">Existem dois cenários possíveis que você pode usar para implantar e associar as funções do servidor:</span><span class="sxs-lookup"><span data-stu-id="6c2c0-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="6c2c0-p116">Para o cenário um, você está definindo uma nova topologia para uma nova instalação. É possível abordar a instalação em uma das duas seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="6c2c0-p116">For scenario one, you are defining a new topology for a new installation. You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="6c2c0-186">Desmarque a caixa de seleção e prossiga com a definição da topologia.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="6c2c0-187">Após publicar, configurar e testar as funções de servidor front-end e back-end, você poderá executar o construtor de topologias novamente para adicionar os servidores de função à topologia.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="6c2c0-188">Essa estratégia permitirá que você teste o pool de front-ends e o servidor que executa o SQL Server sem complicações adicionais de funções adicionais.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="6c2c0-189">Depois de concluir o teste inicial, você poderá executar o construtor de topologias novamente para selecionar as funções que precisa implantar.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="6c2c0-190">Selecione as funções que você precisa instalar e configure o hardware para acomodar as funções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="6c2c0-191">Para o cenário dois, você tem uma implantação existente e sua infraestrutura está pronta para novas funções ou você precisa associar as funções existentes a um novo servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="6c2c0-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="6c2c0-192">Nesse caso, você selecionará as funções que pretende implantar ou associar ao novo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="6c2c0-193">Em qualquer caso, você continuará com a definição das funções, configurar qualquer hardware necessário e continuar com a instalação.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="6c2c0-194">Na página **Definir o repositório SQL**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6c2c0-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="6c2c0-195">Para usar um repositório de SQL Server existente que já foi definido em sua topologia, selecione uma instância do **Repositório SQL**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="6c2c0-196">Para definir uma nova instância do SQL Server para armazenar informações de pool, clique em **novo** e ESPECIFIQUE o **FQDN do SQL Server**na caixa de diálogo **definir novo repositório SQL** .</span><span class="sxs-lookup"><span data-stu-id="6c2c0-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="6c2c0-197">Para especificar o nome de uma instância de SQL Server, selecione **Instância nomeada** e especifique o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="6c2c0-198">Para usar a instância padrão, clique em **Instância padrão**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="6c2c0-199">Para usar o espelhamento SQL, selecione **Habilitar espelhamento do SQL** e selecione uma instância existente ou crie uma nova instância.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="6c2c0-200">Na página **Definir o compartilhamento de arquivo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6c2c0-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="6c2c0-201">Para usar um compartilhamento de arquivo que já foi definido na sua topologia, selecione **Usar um compartilhamento de arquivos definido anteriormente**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="6c2c0-202">Para definir um novo compartilhamento de arquivo, selecione **Definir um novo compartilhamento de arquivo** na caixa **FQDN do Servidor de Arquivos**, insira o FQDN do servidor de arquivos existente onde o compartilhamento de arquivo deve residir e insira um nome para o compartilhamento de arquivo na caixa **Compartilhamento de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6c2c0-203">O compartilhamento de arquivos do Lync Server 2013 não pode ser localizado no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="6c2c0-204">Observe que neste exemplo, o compartilhamento de arquivo foi localizado no servidor Back-End com base no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="6c2c0-205">Este pode não ser um local ideal para as necessidades da sua organização, um servidor de arquivos pode ser uma escolha melhor.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="6c2c0-206">Você pode definir o compartilhamento de arquivos sem que este tenha sido criado.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="6c2c0-207">Será necessário criar o compartilhamento de arquivos no local que você definir antes de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="6c2c0-208">Na página **Especificar a URL dos serviços Web**, execute um ou estes dois procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6c2c0-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6c2c0-209">A URL base é a identidade dos Serviços Web para a URL, menos o https://.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="6c2c0-210">Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net , a URL base será pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="6c2c0-211">Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN de serviços Web externos deverá ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="6c2c0-212">Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="6c2c0-213">Se você estiver configurando o balanceamento de carga DNS, marque a caixa de seleção **substituir o FQDN do pool de serviços Web interno** , digite a URL base interna (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interna \<your base URL\> ) na **URL base interna**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="6c2c0-214">Se você decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="6c2c0-215"><STRONG>Use apenas caracteres padrão</STRONG> (incluindo a – z, A – z, 0 – 9 e hifens) ao definir URLs ou nomes de domínio totalmente qualificados.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="6c2c0-216">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="6c2c0-217">Não há suporte para caracteres não padrão em uma URL ou FQDN em CAs externas e CAs públicas (ou seja, quando a URL ou FQDN deve ser atribuído ao nome da entidade ou ao nome alternativo da entidade no certificado).</span><span class="sxs-lookup"><span data-stu-id="6c2c0-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="6c2c0-218">Opcionalmente, insira a URL base externa em **URL base externa**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="6c2c0-219">Insira a URL base externa para diferenciá-la da nomeação de domínio interna.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="6c2c0-220">Por exemplo, seu domínio interno é contoso.net, mas seu nome de domínio externo é contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="6c2c0-221">Você deve definir a URL usando o nome do domínio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="6c2c0-222">Isso também é importante no caso de um proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="6c2c0-223">O nome de domínio da URL base externa seria igual ao nome de domíniodo  FQDN do proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="6c2c0-224">Mensagens instantâneas e presença exigem acesso HTTP ao pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6c2c0-225">Para usar o balanceamento de carga DNS, você deve criar os registros DNS apropriados.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="6c2c0-226">Para obter detalhes, consulte <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configurar o DNS para balanceamento de carga no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="6c2c0-227">Se você selecionou **conferência** na página **selecionar recursos** , na página **selecionar um servidor do Office Web Apps** , selecione **associar pool com um servidor do Office Web Apps** e clique em **novo** (ou selecione um servidor do Office Web Apps existente na lista suspensa).</span><span class="sxs-lookup"><span data-stu-id="6c2c0-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="6c2c0-228">Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor Office Web Apps na caixa **FQDN do Servidor Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="6c2c0-229">Se o servidor do Office Web Apps estiver instalado no local e na mesma zona de rede do Lync Server 2013, a opção **Office Web Apps Server é implantada em uma rede externa (ou seja, perímetro/Internet)** não deve ser selecionada.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="6c2c0-230">Se o Servidor Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6c2c0-231">Para obter detalhes, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="6c2c0-232">Na página **Definir o Repositório do SQL de Arquivamento**, selecione uma instância existente do SQL Server ou defina uma nova instância para armazenar os dados associados a arquivamento.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="6c2c0-233">Na página **Definir o Repositório do SQL de Monitoramento**, selecione uma instância existente do SQL Server ou defina uma nova instância para armazenar os dados associados a monitoramento.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="6c2c0-234">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-234">Click **Next**.</span></span> <span data-ttu-id="6c2c0-235">Se você definiu outros servidores de função na página **associar funções de servidor a este pool de front-ends** , as páginas do assistente de configuração de função separada serão abertas para permitir que você configure as funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="6c2c0-236">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="6c2c0-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="6c2c0-237">Implantando o acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c2c0-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="6c2c0-238">Se você não selecionou funções do servidor adicionais para configurar e implantar ou quando você finalizou a configuração dos servidores de função adicionais, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="6c2c0-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

