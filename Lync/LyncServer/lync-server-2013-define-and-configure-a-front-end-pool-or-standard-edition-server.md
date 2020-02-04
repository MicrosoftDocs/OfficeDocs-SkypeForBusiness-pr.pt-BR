---
title: Definir e configurar um pool Front-End ou um servidor Standard Edition
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
ms.openlocfilehash: ddc430370c59e279e0e36aa662da0f33973e0d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="e7888-102">Definir e configurar um pool Front-End ou um servidor Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7888-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7888-103">_**Tópico da última modificação:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="e7888-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="e7888-104">Esse procedimento não requer associação em um administrador local ou em um grupo de domínio privilegiado.</span><span class="sxs-lookup"><span data-stu-id="e7888-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="e7888-105">Você deve fazer logon em um computador como usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="e7888-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="e7888-106">Se você estiver implantando um servidor corporativo, um número mínimo de servidores front-end em um pool deve estar sempre em execução.</span><span class="sxs-lookup"><span data-stu-id="e7888-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="e7888-107">A tabela a seguir resume esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="e7888-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7888-108">Número total de servidores front-end no pool</span><span class="sxs-lookup"><span data-stu-id="e7888-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="e7888-109">Número de servidores que devem estar em execução para o pool ser funcional</span><span class="sxs-lookup"><span data-stu-id="e7888-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7888-110">1-2</span><span class="sxs-lookup"><span data-stu-id="e7888-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="e7888-111">1</span><span class="sxs-lookup"><span data-stu-id="e7888-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7888-112">3-4</span><span class="sxs-lookup"><span data-stu-id="e7888-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="e7888-113">2</span><span class="sxs-lookup"><span data-stu-id="e7888-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7888-114">5-6</span><span class="sxs-lookup"><span data-stu-id="e7888-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="e7888-115">3</span><span class="sxs-lookup"><span data-stu-id="e7888-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7888-116">7-8</span><span class="sxs-lookup"><span data-stu-id="e7888-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="e7888-117">4</span><span class="sxs-lookup"><span data-stu-id="e7888-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7888-118">9-10</span><span class="sxs-lookup"><span data-stu-id="e7888-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="e7888-119">5</span><span class="sxs-lookup"><span data-stu-id="e7888-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7888-120">11-12</span><span class="sxs-lookup"><span data-stu-id="e7888-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="e7888-121">6</span><span class="sxs-lookup"><span data-stu-id="e7888-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="e7888-122">Para o Lync Server 2013, a qualquer momento em que você adicionar ou remover um servidor front-end do pool, você deve reiniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="e7888-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="e7888-123">Remover e adicionar servidores deve ser feito como operações separadas.</span><span class="sxs-lookup"><span data-stu-id="e7888-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="e7888-124">Por exemplo, se você vai adicionar dois servidores front-end e remover dois servidores front-end, use o seguinte processo:</span><span class="sxs-lookup"><span data-stu-id="e7888-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="e7888-125">Remova os dois servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="e7888-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7888-126">Publique e ative novamente a topologia.</span><span class="sxs-lookup"><span data-stu-id="e7888-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7888-127">Reiniciar os serviços</span><span class="sxs-lookup"><span data-stu-id="e7888-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="e7888-128">Adicione os dois servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="e7888-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7888-129">Publique e ative novamente a topologia.</span><span class="sxs-lookup"><span data-stu-id="e7888-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7888-130">Reinicie os serviços.</span><span class="sxs-lookup"><span data-stu-id="e7888-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="e7888-131">Depois de definir sua topologia, use o procedimento a seguir para definir um pool de front-ends para seu site.</span><span class="sxs-lookup"><span data-stu-id="e7888-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="e7888-132">Para obter detalhes sobre como definir a topologia, consulte [definir e configurar uma topologia no construtor de topologias para o Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e7888-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="e7888-133">Para definir um pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="e7888-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="e7888-134">No assistente definir novo pool de front-end, na página **definir o novo pool de front-ends** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e7888-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="e7888-135">Na página **definir o FQDN do pool de front-end** , insira um nome de domínio totalmente qualificado (FQDN) para o pool que você está criando, clique em **pool de front-end Enterprise Edition**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e7888-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="e7888-136">Na página **definir os computadores neste pool** , insira um FQDN do computador para o primeiro servidor front-end do pool e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e7888-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="e7888-137">Repita essa etapa para qualquer computador adicional (até doze) que você deseja adicionar ao pool e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e7888-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="e7888-138">Na página **selecionar recursos** , marque as caixas de seleção dos recursos que você deseja neste pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e7888-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="e7888-139">Por exemplo, se você estiver implantando apenas mensagens instantâneas e recursos de presença, marque a caixa de seleção **conferência** para permitir mensagens instantâneas com vários participantes, mas não marque as caixas de seleção **conferência de discagem (PSTN)**, **Enterprise Voice**ou **controle de admissão de chamadas** , pois representam recursos de voz, vídeo e conferência colaborativa.</span><span class="sxs-lookup"><span data-stu-id="e7888-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="e7888-140">**Conferência**   essa seleção permite um conjunto avançado de recursos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="e7888-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="e7888-141">Mensagens instantâneas com mais de duas partes em uma sessão de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="e7888-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="e7888-142">Conferência, que inclui colaboração de documentos, compartilhamento de aplicativos e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e7888-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="e7888-143">Conferência a/V, que permite que os usuários tenham conferências de áudio/vídeo (A/V) em tempo real sem a necessidade de serviços externos, como o serviço Live Meeting ou uma ponte de áudio de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e7888-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="e7888-144">**A conferência**   discada (PSTN) permite que os usuários ingressem na parte de áudio de uma conferência do Lync Server 2013 usando um telefone PSTN (rede telefônica pública comutada) sem precisar de um provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="e7888-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="e7888-145">**O Enterprise Voice**   Enterprise Voice é a solução de voz sobre IP (VoIP) no Lync Server 2013, que permite aos usuários fazer e receber chamadas telefônicas.</span><span class="sxs-lookup"><span data-stu-id="e7888-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="e7888-146">Você pode implantar esse recurso se planeja usar o Lync Server 2013 para chamadas de voz, caixa postal e outras funções que usam um dispositivo de hardware ou um cliente de software.</span><span class="sxs-lookup"><span data-stu-id="e7888-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="e7888-147">**O controle de admissão de chamadas (CAC)**   o CAC determina, com base na largura de banda de rede disponível, se permite que sessões de comunicação em tempo real, como chamadas de voz ou com vídeo, sejam estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="e7888-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="e7888-148">Se você implantou apenas mensagens instantâneas e presença, o CAC não é necessário porque nenhum desses dois recursos usa o CAC.</span><span class="sxs-lookup"><span data-stu-id="e7888-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="e7888-149">**O arquivamento**de arquivamento fornece uma maneira de arquivar conteúdo de mensagens de chat, conteúdo de conferência (reunião) ou ambos enviados pelo Lync Server 2013.   </span><span class="sxs-lookup"><span data-stu-id="e7888-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="e7888-150">**Monitorando**   o monitoramento do servidor permite que você colete dados numéricos que descrevem a qualidade da mídia em sua rede e pontos de extremidade, informações de uso relacionadas a chamadas de VoIP, mensagens de chat, conversas de A/V, reuniões, compartilhamento de aplicativos e transferências de arquivos, além de informações de erro e de solução de problemas para chamadas com falha.</span><span class="sxs-lookup"><span data-stu-id="e7888-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e7888-151">Se você quiser habilitar o CAC em sua implantação, será necessário habilitar o CAC em exatamente um pool por site central.</span><span class="sxs-lookup"><span data-stu-id="e7888-151">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site.</span></span> <span data-ttu-id="e7888-152">O CAC será recomendado se você estiver implantando recursos de voz ou conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="e7888-152">CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="e7888-153">A tabela a seguir mostra os recursos disponíveis (superior) e as funções oferecidas aos usuários (à esquerda).</span><span class="sxs-lookup"><span data-stu-id="e7888-153">The following table shows the available features (top) and the functions offered to users (left).</span></span> <span data-ttu-id="e7888-154">As seleções na tabela são o que você deve selecionar para habilitar esses recursos para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="e7888-154">The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
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
    <th><span data-ttu-id="e7888-155">Conferência</span><span class="sxs-lookup"><span data-stu-id="e7888-155">Conferencing</span></span></th>
    <th><span data-ttu-id="e7888-156">Conferência discada</span><span class="sxs-lookup"><span data-stu-id="e7888-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="e7888-157">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="e7888-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="e7888-158">Serviço de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="e7888-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="e7888-159">Mensagens instantâneas e presença</span><span class="sxs-lookup"><span data-stu-id="e7888-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="e7888-160">X</span><span class="sxs-lookup"><span data-stu-id="e7888-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e7888-161">Conferência</span><span class="sxs-lookup"><span data-stu-id="e7888-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="e7888-162">X</span><span class="sxs-lookup"><span data-stu-id="e7888-162">X</span></span></p></td>
    <td><p><span data-ttu-id="e7888-163">X</span><span class="sxs-lookup"><span data-stu-id="e7888-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e7888-164">Conferências de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="e7888-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="e7888-165">X</span><span class="sxs-lookup"><span data-stu-id="e7888-165">X</span></span></p></td>
    <td><p><span data-ttu-id="e7888-166">X</span><span class="sxs-lookup"><span data-stu-id="e7888-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="e7888-167">X</span><span class="sxs-lookup"><span data-stu-id="e7888-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e7888-168">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="e7888-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="e7888-169">X</span><span class="sxs-lookup"><span data-stu-id="e7888-169">X</span></span></p></td>
    <td><p><span data-ttu-id="e7888-170">X</span><span class="sxs-lookup"><span data-stu-id="e7888-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="e7888-171">Na página **selecionar funções de servidor posicionadas** , você pode posicionar o servidor de mediação no servidor front-end ou implantá-lo como um servidor autônomo.</span><span class="sxs-lookup"><span data-stu-id="e7888-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="e7888-172">Você pode posicionar o servidor de mediação no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e7888-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="e7888-173">Se você pretende posicionar o servidor de mediação no pool de front-end do Enterprise Edition, certifique-se de que a caixa de seleção esteja marcada.</span><span class="sxs-lookup"><span data-stu-id="e7888-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="e7888-174">A função de servidor será implantada nos servidores do pool.</span><span class="sxs-lookup"><span data-stu-id="e7888-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="e7888-175">Se você pretende implantar o servidor de mediação como um servidor autônomo, desmarque a caixa de seleção apropriada.</span><span class="sxs-lookup"><span data-stu-id="e7888-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="e7888-176">Você vai implantar o servidor de mediação em uma etapa de implantação separada após a implantação completa do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e7888-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e7888-177">Recomendamos que você se colocação do servidor de mediação, se possível.</span><span class="sxs-lookup"><span data-stu-id="e7888-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="e7888-178">Para obter detalhes sobre o suporte a servidores de mediação posicionados ou autônomos, consulte <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">componentes e topologias do servidor de mediação no Lync server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="e7888-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="e7888-179">A página **associar funções de servidor a esta página de pool de front-end** permite definir e associar funções de servidor ao pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="e7888-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="e7888-180">A seguinte função está disponível:</span><span class="sxs-lookup"><span data-stu-id="e7888-180">The following role is available:</span></span>
    
    <span data-ttu-id="e7888-181">**Habilitar um pool**   de bordas define e associa um servidor de borda único ou um pool de servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="e7888-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="e7888-182">O servidor de borda intermedia a comunicação e colaboração entre os usuários dentro da organização e as pessoas de fora da organização, inclusive usuários federados.</span><span class="sxs-lookup"><span data-stu-id="e7888-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="e7888-183">Há dois cenários possíveis que você pode usar para implantar e associar as funções de servidor:</span><span class="sxs-lookup"><span data-stu-id="e7888-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="e7888-184">No cenário um, você está definindo uma nova topologia para uma nova instalação.</span><span class="sxs-lookup"><span data-stu-id="e7888-184">For scenario one, you are defining a new topology for a new installation.</span></span> <span data-ttu-id="e7888-185">Você pode abordar a instalação de uma destas duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="e7888-185">You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="e7888-186">Deixe a caixa de seleção desmarcada e prossiga com a definição da topologia.</span><span class="sxs-lookup"><span data-stu-id="e7888-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="e7888-187">Após publicar, configurar e testar as funções de servidor front-end e back-end, execute o Construtor de Topologias novamente para adicionar os servidores de função à topologia.</span><span class="sxs-lookup"><span data-stu-id="e7888-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="e7888-188">Essa estratégia permitirá testar o pool de front-ends e o servidor que executa o SQL Server sem complicações adicionais das funções adicionais.</span><span class="sxs-lookup"><span data-stu-id="e7888-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="e7888-189">Depois de concluir o teste inicial, execute o Construtor de Topologias novamente para selecionar as funções necessárias para implantação.</span><span class="sxs-lookup"><span data-stu-id="e7888-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="e7888-190">Selecione as funções que você precisa instalar e configure o hardware para acomodar as funções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="e7888-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="e7888-191">Para o cenário dois, você tem uma implantação existente e sua infraestrutura está pronta para novas funções ou você precisa associar funções existentes a um novo servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="e7888-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="e7888-192">Nesse caso, você selecionará as funções que pretende implantar ou associar ao novo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e7888-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="e7888-193">Em qualquer um dos casos, você continuará com a definição das funções, a configuração do hardware necessário e a instalação.</span><span class="sxs-lookup"><span data-stu-id="e7888-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="e7888-194">Na página **definir a SQL Store** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e7888-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e7888-195">Para usar um repositório de SQL Server existente que já foi definido em sua topologia, selecione uma instância do **Repositório SQL**.</span><span class="sxs-lookup"><span data-stu-id="e7888-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="e7888-196">Para definir uma nova instância do SQL Server para armazenar informações do pool, clique em **novo** e, em seguida, ESPECIFIQUE o **FQDN do SQL Server**na caixa de diálogo **definir novo repositório SQL** .</span><span class="sxs-lookup"><span data-stu-id="e7888-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="e7888-197">Para especificar o nome de uma instância de SQL Server, selecione **Instância Nomeada** e especifique o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="e7888-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="e7888-198">Para usar a instância padrão, clique em **Instância padrão**.</span><span class="sxs-lookup"><span data-stu-id="e7888-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="e7888-199">Para usar o espelhamento do SQL, selecione **habilitar o espelhamento do SQL** e selecione uma instância existente ou crie uma nova instância.</span><span class="sxs-lookup"><span data-stu-id="e7888-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="e7888-200">Na página **definir o compartilhamento de arquivos** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e7888-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e7888-201">Para usar um compartilhamento de arquivo que já foi definido na sua topologia, selecione **Usar um compartilhamento de arquivos previamente definido**.</span><span class="sxs-lookup"><span data-stu-id="e7888-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="e7888-202">Para definir um novo compartilhamento de arquivo, selecione **Definir um novo compartilhamento de arquivo** na caixa **FQDN do Servidor de Arquivos**, insira o FQDN do servidor de arquivos existente onde o compartilhamento de arquivo deve residir e insira um nome para o compartilhamento de arquivo na caixa **Compartilhamento de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="e7888-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e7888-203">O compartilhamento de arquivos do Lync Server 2013 não pode ser localizado no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e7888-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="e7888-204">Observe que, neste exemplo, o compartilhamento de arquivos foi localizado no servidor back-end baseado no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e7888-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="e7888-205">Isso pode não ser um local ideal para os requisitos da sua organização, e um servidor de arquivos pode ser uma opção melhor.</span><span class="sxs-lookup"><span data-stu-id="e7888-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="e7888-206">Você pode definir o compartilhamento de arquivos sem que ele tenha sido criado.</span><span class="sxs-lookup"><span data-stu-id="e7888-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="e7888-207">Além disso, você precisará criar o compartilhamento de arquivos no local definido para poder publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="e7888-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="e7888-208">Na página **especificar a URL dos serviços Web** , siga um destes procedimentos ou ambos:</span><span class="sxs-lookup"><span data-stu-id="e7888-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e7888-209">A URL base é a identidade dos serviços Web para a URL, menos "https://".</span><span class="sxs-lookup"><span data-stu-id="e7888-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="e7888-210">Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="e7888-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="e7888-211">Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN dos serviços Web externos deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="e7888-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="e7888-212">Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-end ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e7888-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="e7888-213">Se você estiver configurando o balanceamento de carga de DNS, marque a caixa de seleção **substituir FQDN do pool de serviços Web internos** , insira a URL base interna (que deve ser diferente da FQDN do pool e\<, por exemplo\>, interna-sua URL base) em **URL base interna**.</span><span class="sxs-lookup"><span data-stu-id="e7888-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="e7888-214">Se você decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.</span><span class="sxs-lookup"><span data-stu-id="e7888-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="e7888-215"><STRONG>Use apenas caracteres padrão</STRONG> (incluindo A–Z, a–z, 0–9 e hifens) ao definir URLs ou nomes de domínio totalmente qualificados.</span><span class="sxs-lookup"><span data-stu-id="e7888-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="e7888-216">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="e7888-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="e7888-217">Normalmente, caracteres não padrão no URL ou FQDN não são suportados por DNS externo e CAs públicas (ou seja, quando o URL ou FQDN deve ser atribuído ao nome da entidade ou ao nome alternativo da entidade no certificado).</span><span class="sxs-lookup"><span data-stu-id="e7888-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="e7888-218">Opcionalmente, insira a URL base externa na **URL base externa**.</span><span class="sxs-lookup"><span data-stu-id="e7888-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="e7888-219">Você digitaria a URL base externa para diferenciá-la de seu nome de domínio interno.</span><span class="sxs-lookup"><span data-stu-id="e7888-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="e7888-220">Por exemplo, seu domínio interno é contoso.net, mas o seu nome de domínio externo é contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e7888-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="e7888-221">Você definiria a URL usando o nome de domínio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e7888-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="e7888-222">Isso também é importante no caso de um proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="e7888-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="e7888-223">O nome de domínio da URL base externa seria igual ao nome de domínio do FQDN do proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="e7888-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="e7888-224">As mensagens instantâneas e a presença exigem acesso HTTP ao pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e7888-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e7888-225">Para usar o balanceamento de carga de DNS, você deve criar os registros DNS apropriados.</span><span class="sxs-lookup"><span data-stu-id="e7888-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="e7888-226">Para obter detalhes, consulte <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configurar o DNS para balanceamento de carga no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e7888-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="e7888-227">Se você selecionou **conferência** na página **selecionar recursos** , na página **selecionar um servidor do Office Web Apps** , selecione **associar pool com um servidor do Office Web Apps** e clique em **novo** (ou selecione um servidor existente do Office Web Apps na lista suspensa).</span><span class="sxs-lookup"><span data-stu-id="e7888-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="e7888-228">Na caixa de diálogo **Definir Novo Servidor do Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor do Office Web Apps na caixa **FQDN do Servidor do Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor do Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor do Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="e7888-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="e7888-229">Se o Office Web Apps Server estiver instalado no local e na mesma zona de rede do Lync Server 2013, a opção **Office Web Apps Server será implantada em uma rede externa (isto é, perímetro/Internet)** não deve ser selecionada.</span><span class="sxs-lookup"><span data-stu-id="e7888-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="e7888-230">Se o Servidor do Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor do Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="e7888-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e7888-231">Para obter detalhes, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e7888-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="e7888-232">Na página **definir a repositório do SQL Store** , selecione uma instância existente ou SQL Server, ou defina uma nova instância para armazenar os dados associados ao arquivamento de dados.</span><span class="sxs-lookup"><span data-stu-id="e7888-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="e7888-233">Na página **definir a loja do SQL Store** , selecione uma instância existente ou SQL Server, ou defina uma nova instância para armazenar os dados associados a dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="e7888-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="e7888-234">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="e7888-234">Click **Next**.</span></span> <span data-ttu-id="e7888-235">Se você definiu outros servidores de função na página **associar funções de servidor a esta página de pool de front-end** , as páginas do assistente de configuração de função separado serão abertas para permitir que você configure as funções do servidor.</span><span class="sxs-lookup"><span data-stu-id="e7888-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="e7888-236">Para obter detalhes, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="e7888-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="e7888-237">Implantação de acesso do usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7888-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="e7888-238">Se você não selecionou funções de servidor adicionais para configurar e implantar, ou quando tiver terminado a configuração dos servidores de função adicionais, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="e7888-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

