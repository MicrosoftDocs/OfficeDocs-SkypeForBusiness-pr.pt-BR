---
title: Lync Server 2013 suporte para conectividade pública de mensagens instantâneas
description: Lync Server 2013 suporte para conectividade pública de mensagens instantâneas.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4a58d71eb23012da960cf4505f1a55fd08df32c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573247"
---
# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="74d10-103">Suporte para conectividade pública do Messenger no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74d10-103">Support for public instant messenger connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74d10-104">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="74d10-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="74d10-105">Suporte para conectividade pública do Messenger</span><span class="sxs-lookup"><span data-stu-id="74d10-105">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="74d10-106">Este artigo fornece informações sobre o suporte para a PIC (conectividade de IM pública).</span><span class="sxs-lookup"><span data-stu-id="74d10-106">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="74d10-107">O PIC é um recurso do Microsoft Lync que permite às organizações habilitar seus usuários do Lync a se conectarem com usuários de determinados serviços de mensagens instantâneas (IM) públicos através de seus clientes e identidades do Lync.</span><span class="sxs-lookup"><span data-stu-id="74d10-107">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="74d10-108">Os usuários finais se beneficiam da capacidade de se conectar com clientes, parceiros e fornecedores em seus termos.</span><span class="sxs-lookup"><span data-stu-id="74d10-108">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="74d10-109">Ele se beneficia do suporte a um único cliente de comunicação em tempo real, mantendo os recursos de controle, conformidade e arquivamento do Lync.</span><span class="sxs-lookup"><span data-stu-id="74d10-109">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="74d10-110">Lync-Skype conectividade, [publicamente disponível em maio de 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), depende do herdado que o Lync/Office Communications Server (OCS)/Live Communications Server (LCs) primeiro estabeleceu com a PIC na conexão com o MSN/Windows Live, AOL e Yahoo.</span><span class="sxs-lookup"><span data-stu-id="74d10-110">Lync-Skype connectivity, [publicly available in May 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="74d10-111">Para obter mais informações sobre a conectividade de Lync-Skype, consulte [Lync-Skype Connectivity](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span><span class="sxs-lookup"><span data-stu-id="74d10-111">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="74d10-112">A Federação com o Windows Live, AOL e Yahoo é cada uma em um caminho voltado ao fim da vida útil.</span><span class="sxs-lookup"><span data-stu-id="74d10-112">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="74d10-113">Esta página documenta o status de cada serviço.</span><span class="sxs-lookup"><span data-stu-id="74d10-113"> This page documents the status of each service.</span></span>

<span data-ttu-id="74d10-114">Para usar a PIC, os clientes precisam ativar o serviço para cada provedor de serviços públicos de IM.</span><span class="sxs-lookup"><span data-stu-id="74d10-114">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="74d10-115">Os requisitos e detalhes sobre como fazer isso dependem do provedor de serviços de mensagens instantâneas e do programa de licenciamento subjacente do cliente.</span><span class="sxs-lookup"><span data-stu-id="74d10-115">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="74d10-116">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="74d10-116">Windows Live Messenger</span></span>

<span data-ttu-id="74d10-117">A Microsoft colocou o Windows Live Messenger e o Skype juntos.</span><span class="sxs-lookup"><span data-stu-id="74d10-117">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="74d10-118">Em abril de 2013, os usuários do Messenger migraram para o Skype durante a entrada.</span><span class="sxs-lookup"><span data-stu-id="74d10-118">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="74d10-119">Os clientes do Lync que dependem da Federação com o Messenger continuarão a ser capazes de se comunicar com seus contatos do Messenger, mesmo depois que os contatos são atualizados para o Skype.</span><span class="sxs-lookup"><span data-stu-id="74d10-119">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="74d10-120">Não há nada que os administradores do Lync ou os usuários finais do Lync precisem fazer para manter a continuidade de serviço, e o gerenciamento desse recurso no Lync permanece o mesmo que para comunicações com o Messenger.</span><span class="sxs-lookup"><span data-stu-id="74d10-120">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="74d10-121">Quando os usuários do Messenger entram no Skype usando suas contas da Microsoft (ou seja, as mesmas credenciais usadas para o Messenger) todos os contatos do Messenger-incluindo contatos federados do Lync-siga-os para o Skype.</span><span class="sxs-lookup"><span data-stu-id="74d10-121">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="74d10-122">O compartilhamento de presença e mensagens instantâneas entre o Skype e o Lync para esses contatos estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="74d10-122">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="74d10-123">Conectividade Lync-Skype-contato adicionando, compartilhamento de presença, mensagens instantâneas e chamadas de áudio entre usuários do Lync e do Skype, agora está disponível para todos os clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="74d10-123">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="74d10-124">Instant\!</span><span class="sxs-lookup"><span data-stu-id="74d10-124">Yahoo\!</span></span> <span data-ttu-id="74d10-125">e AOL Instant Messenger</span><span class="sxs-lookup"><span data-stu-id="74d10-125">and AOL Instant Messenger</span></span>

<span data-ttu-id="74d10-126">Federação com Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="74d10-126">Federation with Yahoo\!</span></span> <span data-ttu-id="74d10-127">e a AOL estão em um caminho voltado para o fim da vida útil para os clientes do Lync (e o Office Communications Server).</span><span class="sxs-lookup"><span data-stu-id="74d10-127">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="74d10-128">A capacidade da Microsoft de fornecer a cada um desses serviços tem o suporte contingente no Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="74d10-128">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="74d10-129">e AOL, e os acordos subjacentes deles estão para baixo.</span><span class="sxs-lookup"><span data-stu-id="74d10-129">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="74d10-130">Para o Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="74d10-130">For both Yahoo\!</span></span> <span data-ttu-id="74d10-131">e AOL, o serviço continuará até junho de 2014.</span><span class="sxs-lookup"><span data-stu-id="74d10-131">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="74d10-132">O **Yahoo** -Service continuará até junho de 2014, e os clientes continuarão a ser licenciados com a licença de assinatura de usuário da conectividade de im pública do Microsoft Lync ("pic USL").</span><span class="sxs-lookup"><span data-stu-id="74d10-132">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="74d10-133">A partir de 1º de setembro de 2012, a PIC USL, não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="74d10-133">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="74d10-134">Os clientes com licenças adquiridas antes desta data poderão continuar a se federar com o Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="74d10-134">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="74d10-135">até o anterior da data de desligamento do serviço ou de sua validade da licença.</span><span class="sxs-lookup"><span data-stu-id="74d10-135">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="74d10-136">Leia [o comunicado](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) no blog da equipe do Lync.</span><span class="sxs-lookup"><span data-stu-id="74d10-136"> Read [the announcement](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="74d10-137">Os clientes que têm licenças de PIC em acordos que vão além de 30 de junho de 2014 receberão um crédito em proporção à quantidade de pagamentos que abrangem o período de tempo após 30 de junho de 2014.</span><span class="sxs-lookup"><span data-stu-id="74d10-137"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="74d10-138">A **AOL** em 30 de junho de 2014, o serviço de conectividade de IM ("pic") do Lync não estará mais disponível.</span><span class="sxs-lookup"><span data-stu-id="74d10-138">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="74d10-139">Para limitar a interrupção do cliente quando o serviço é encerrado, descontinuamos o provisionamento de domínios de clientes adicionais.</span><span class="sxs-lookup"><span data-stu-id="74d10-139"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="74d10-140">Até 30 de junho de 2014, os clientes não precisam fazer nada para continuar a suportar comunicações federadas com o AIM.</span><span class="sxs-lookup"><span data-stu-id="74d10-140">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="74d10-141">Além dessa data (ou para clientes que desejam provisionar domínios adicionais por enquanto), um serviço substituto está disponível diretamente na AOL.</span><span class="sxs-lookup"><span data-stu-id="74d10-141">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="74d10-142">Para obter mais informações sobre o novo serviço da AOL, consulte [establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)    (abre a nova página no AOL.com).</span><span class="sxs-lookup"><span data-stu-id="74d10-142">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="74d10-143">Resumo do provedor de IM público</span><span class="sxs-lookup"><span data-stu-id="74d10-143">Public IM Provider Summary</span></span>

<span data-ttu-id="74d10-144">A tabela a seguir fornece um resumo dos provedores de serviços públicos de mensagens instantâneas, recursos de Federação com Lync e requisitos de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="74d10-144">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74d10-145">Provedor de serviços públicos de IM</span><span class="sxs-lookup"><span data-stu-id="74d10-145">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="74d10-146">Recursos federados</span><span class="sxs-lookup"><span data-stu-id="74d10-146">Federated Capabilities</span></span></th>
<th><span data-ttu-id="74d10-147">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="74d10-147">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74d10-148">Skype</span><span class="sxs-lookup"><span data-stu-id="74d10-148">Skype</span></span></p></td>
<td><p><span data-ttu-id="74d10-149">IM, presença, áudio</span><span class="sxs-lookup"><span data-stu-id="74d10-149">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="74d10-150">Licenças de acesso para cliente do Lync Server, Lync Online Plan 1/2/3</span><span class="sxs-lookup"><span data-stu-id="74d10-150">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d10-151">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="74d10-151">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="74d10-152">IM, presença, áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="74d10-152">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="74d10-153">Licenças de acesso para cliente do Lync Server (com suporte desde que o WLM esteja no mercado)</span><span class="sxs-lookup"><span data-stu-id="74d10-153">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74d10-154">AOL</span><span class="sxs-lookup"><span data-stu-id="74d10-154">AOL</span></span></p></td>
<td><p><span data-ttu-id="74d10-155">IM, presença</span><span class="sxs-lookup"><span data-stu-id="74d10-155">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="74d10-156">Licenças de acesso para cliente do Lync Server; com suporte até junho de 2014 para clientes existentes.</span><span class="sxs-lookup"><span data-stu-id="74d10-156">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d10-157">Toolbar</span><span class="sxs-lookup"><span data-stu-id="74d10-157">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="74d10-158">IM, presença</span><span class="sxs-lookup"><span data-stu-id="74d10-158">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="74d10-159">Requer a licença de assinatura de usuário de conectividade pública de IM ("PIC USL") adicional do Microsoft Lync Server, além de licenças de acesso para cliente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74d10-159">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="74d10-160">A partir da lista de preços de setembro de 2012, o PIC USL não está mais disponível para compra.</span><span class="sxs-lookup"><span data-stu-id="74d10-160">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="74d10-161">Clientes com licenças ativas podem continuar a federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="74d10-161">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="74d10-162">Messenger até a data de encerramento do serviço em 30 de junho de 2014.</span><span class="sxs-lookup"><span data-stu-id="74d10-162">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

