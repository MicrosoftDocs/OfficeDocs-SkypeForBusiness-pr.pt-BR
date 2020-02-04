---
title: Suporte do Lync Server 2013 para conectividade de mensagem instantânea pública
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
ms.openlocfilehash: 2cd3c8cf89b9d5e1637db893b57e6b5955fbcee9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="dc7be-102">Suporte para conectividade de mensagem instantânea pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc7be-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc7be-103">_**Tópico da última modificação:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="dc7be-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="dc7be-104">Suporte para conectividade de mensagem instantânea pública</span><span class="sxs-lookup"><span data-stu-id="dc7be-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="dc7be-105">Este artigo fornece informações sobre o suporte para a PIC (conectividade pública de IM).</span><span class="sxs-lookup"><span data-stu-id="dc7be-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="dc7be-106">A PIC é um recurso do Microsoft Lync que permite que as organizações habilitem seus usuários do Lync para se conectar com usuários de determinados serviços de mensagens instantâneas (IM) públicas por meio de seus clientes e identidades do Lync.</span><span class="sxs-lookup"><span data-stu-id="dc7be-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="dc7be-107">Os usuários finais se beneficiam da capacidade de se conectar com clientes, parceiros e fornecedores em termos de seus termos.</span><span class="sxs-lookup"><span data-stu-id="dc7be-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="dc7be-108">Ele se beneficia do suporte a um único cliente de comunicação em tempo real, mantendo os recursos de controle, conformidade e arquivamento do Lync.</span><span class="sxs-lookup"><span data-stu-id="dc7be-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="dc7be-109">Lync-conectividade do Skype, [disponível publicamente em maio de 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), depende do herdado que o Lync/Office Communications Server (OCS)/Live Communications Server (LCs) primeiro estabeleceu com a PIC na conexão com o MSN/Windows Live, AOL e Yahoo.</span><span class="sxs-lookup"><span data-stu-id="dc7be-109">Lync-Skype connectivity, [publicly available in May 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="dc7be-110">Para obter mais informações sobre o Lync-conectividade com o Skype, consulte a [conectividade do Lync](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span><span class="sxs-lookup"><span data-stu-id="dc7be-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="dc7be-111">A Federação com o Windows Live, o AOL e o Yahoo são cada um deles em um caminho até o fim da vida útil.</span><span class="sxs-lookup"><span data-stu-id="dc7be-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="dc7be-112">Esta página documenta o status de cada serviço.</span><span class="sxs-lookup"><span data-stu-id="dc7be-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="dc7be-113">Para usar a PIC, os clientes precisam ativar o serviço para cada provedor de serviço de mensagens de chat públicas.</span><span class="sxs-lookup"><span data-stu-id="dc7be-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="dc7be-114">Os requisitos e os detalhes de como fazer isso dependem do provedor de serviços de mensagens instantâneas e do programa de licenciamento subjacente do cliente.</span><span class="sxs-lookup"><span data-stu-id="dc7be-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="dc7be-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="dc7be-115">Windows Live Messenger</span></span>

<span data-ttu-id="dc7be-116">A Microsoft colocou o Windows Live Messenger e o Skype juntos.</span><span class="sxs-lookup"><span data-stu-id="dc7be-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="dc7be-117">Em abril de 2013, os usuários do Messenger migraram para o Skype quando entrarem.</span><span class="sxs-lookup"><span data-stu-id="dc7be-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="dc7be-118">Os clientes do Lync que confiam na Federação com o Messenger continuarão a ser capazes de se comunicar com seus contatos do Messenger, mesmo depois que esses contatos forem atualizados para o Skype.</span><span class="sxs-lookup"><span data-stu-id="dc7be-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="dc7be-119">Não há nada que os administradores do Lync ou os usuários finais do Lync precisem fazer para manter a continuidade do serviço, e o gerenciamento dessa funcionalidade no Lync permanece o mesmo que para comunicações com o Messenger.</span><span class="sxs-lookup"><span data-stu-id="dc7be-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="dc7be-120">Quando os usuários do Messenger se conectarem ao Skype usando suas contas da Microsoft (ou seja, as mesmas credenciais usadas para o Messenger) todos os seus contatos do Messenger-incluindo contatos federados do Lync-siga-os no Skype.</span><span class="sxs-lookup"><span data-stu-id="dc7be-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="dc7be-121">O compartilhamento de presença e mensagens instantâneas entre o Skype e o Lync para estes contatos está disponível.</span><span class="sxs-lookup"><span data-stu-id="dc7be-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="dc7be-122">Lync-conectividade do Skype-adição de contato, compartilhamento de presença, mensagens instantâneas e chamadas de áudio entre o Lync e usuários do Skype – também está disponível para todos os clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="dc7be-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="dc7be-123">Instant\!</span><span class="sxs-lookup"><span data-stu-id="dc7be-123">Yahoo\!</span></span> <span data-ttu-id="dc7be-124">e mensagem instantânea do AOL</span><span class="sxs-lookup"><span data-stu-id="dc7be-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="dc7be-125">Federação com o Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="dc7be-125">Federation with Yahoo\!</span></span> <span data-ttu-id="dc7be-126">e a AOL estão em um caminho para o fim da vida para os clientes do Lync (e do Office Communications Server).</span><span class="sxs-lookup"><span data-stu-id="dc7be-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="dc7be-127">A capacidade da Microsoft de fornecer a cada um desses serviços tem o suporte contingente no Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="dc7be-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="dc7be-128">e a AOL, e os acordos subjacentes deles estão prestes a ser enrolados.</span><span class="sxs-lookup"><span data-stu-id="dc7be-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="dc7be-129">Para o Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="dc7be-129">For both Yahoo\!</span></span> <span data-ttu-id="dc7be-130">e AOL, o serviço continuará até de junho de 2014.</span><span class="sxs-lookup"><span data-stu-id="dc7be-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="dc7be-131">O **Yahoo** -Service continuará até junho de 2014, e os clientes continuarão precisando ser licenciados com a licença de assinatura de usuário da conectividade de im pública do Microsoft Lync ("pic USL").</span><span class="sxs-lookup"><span data-stu-id="dc7be-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="dc7be-132">A partir de 1º de setembro de 2012, a PIC USL, não está mais disponível para compra de contratos novos ou renovadores.</span><span class="sxs-lookup"><span data-stu-id="dc7be-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="dc7be-133">Os clientes com licenças compradas antes desta data poderão continuar a federar-se com o Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="dc7be-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="dc7be-134">até o anterior da data de encerramento do serviço ou o prazo de expiração da licença.</span><span class="sxs-lookup"><span data-stu-id="dc7be-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="dc7be-135">Leia [o comunicado](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) no blog da equipe do Lync.</span><span class="sxs-lookup"><span data-stu-id="dc7be-135"> Read [the announcement](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="dc7be-136">Os clientes que têm licenças de PIC em contratos que vão até 30 de junho de 2014 receberão um crédito em proporção ao valor dos pagamentos que abrangem o período de 30 de junho de 2014.</span><span class="sxs-lookup"><span data-stu-id="dc7be-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="dc7be-137">A **AOL** – em 30 de junho de 2014, o serviço de conectividade de IM ("pic") do Lync não estará mais disponível.</span><span class="sxs-lookup"><span data-stu-id="dc7be-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="dc7be-138">Para limitar a interrupção do cliente quando o serviço terminar, descontinuamos o provisionamento de domínios adicionais do cliente.</span><span class="sxs-lookup"><span data-stu-id="dc7be-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="dc7be-139">Até 30 de junho de 2014, os clientes não precisam fazer nada para continuar a dar suporte às comunicações federadas com o AIM.</span><span class="sxs-lookup"><span data-stu-id="dc7be-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="dc7be-140">Além dessa data (ou para clientes que queiram provisionar domínios adicionais nesse meio tempo), um serviço substituto está disponível diretamente na AOL.</span><span class="sxs-lookup"><span data-stu-id="dc7be-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="dc7be-141">Para obter mais informações sobre o novo serviço da AOL, consulte [estabelecendo Federação direta com AIM](http://aimenterprise.aol.com/pic.php)  (abre a nova página no AOL.com).</span><span class="sxs-lookup"><span data-stu-id="dc7be-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="dc7be-142">Resumo do provedor de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="dc7be-142">Public IM Provider Summary</span></span>

<span data-ttu-id="dc7be-143">A tabela a seguir fornece um resumo dos provedores de serviços públicos de mensagens instantâneas, recursos de Federação com o Lync e requisitos de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="dc7be-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc7be-144">Provedor de serviço público de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="dc7be-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="dc7be-145">Recursos federados</span><span class="sxs-lookup"><span data-stu-id="dc7be-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="dc7be-146">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="dc7be-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc7be-147">Skype</span><span class="sxs-lookup"><span data-stu-id="dc7be-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="dc7be-148">Mensagens instantâneas, presença, áudio</span><span class="sxs-lookup"><span data-stu-id="dc7be-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="dc7be-149">Licenças de acesso para cliente do Lync Server, plano do Lync Online 1/2/3</span><span class="sxs-lookup"><span data-stu-id="dc7be-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc7be-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="dc7be-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="dc7be-151">Mensagens instantâneas, presença, áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="dc7be-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="dc7be-152">Licenças de acesso para cliente do Lync Server (com suporte desde que o WLM esteja no mercado)</span><span class="sxs-lookup"><span data-stu-id="dc7be-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc7be-153">AOL</span><span class="sxs-lookup"><span data-stu-id="dc7be-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="dc7be-154">Mensagens instantâneas, presença</span><span class="sxs-lookup"><span data-stu-id="dc7be-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="dc7be-155">Licenças de acesso para cliente do Lync Server; compatível até junho de 2014 para clientes atuais.</span><span class="sxs-lookup"><span data-stu-id="dc7be-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc7be-156">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="dc7be-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="dc7be-157">Mensagens instantâneas, presença</span><span class="sxs-lookup"><span data-stu-id="dc7be-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="dc7be-158">Requer licença de assinatura de usuário de conectividade de mensagem pública adicional do Microsoft Lync ("PIC USL"), além de licenças de acesso para cliente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc7be-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="dc7be-159">A partir da lista de preços de setembro de 2012, o PIC USL não está mais disponível para compra.</span><span class="sxs-lookup"><span data-stu-id="dc7be-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="dc7be-160">Os clientes com licenças ativas podem continuar a federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="dc7be-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="dc7be-161">Messenger até a data de encerramento do serviço em 30 de junho de 2014.</span><span class="sxs-lookup"><span data-stu-id="dc7be-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
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

