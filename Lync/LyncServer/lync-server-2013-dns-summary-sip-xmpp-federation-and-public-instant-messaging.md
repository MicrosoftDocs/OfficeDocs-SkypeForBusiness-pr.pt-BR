---
title: Resumo de DNS-SIP, Federação de XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c927836377a0c7c14054073a9cf17ce638662450
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="5ea09-102">Resumo de DNS-SIP, Federação de XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea09-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea09-103">_**Tópico da última modificação:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="5ea09-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="5ea09-104">Os registros DNS (sistema de nomes de domínio) que serão necessários para definir uma federação com o Office Communications Server ou com os parceiros do Lync Server são determinados pela sua decisão de permitir a descoberta automática de DNS do seu domínio por outros parceiros de perspectiva.</span><span class="sxs-lookup"><span data-stu-id="5ea09-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="5ea09-105">Se você publicar o \_sipfederationtls. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="5ea09-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="5ea09-106">\* \<Nome\> de domínio SIP\* Registro SRV, qualquer outro domínio federado SIP poderá "descobrir" sua Federação.</span><span class="sxs-lookup"><span data-stu-id="5ea09-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="5ea09-107">Você pode controlar quais domínios federados podem se comunicar com você usando as configurações permitir domínios e domínios bloqueados no painel de controle do Lync Server, ou definindo a configuração de domínios permitidos ou bloqueados usando o Shell de gerenciamento do Lync e os cmdlets **Get**, **set**, **New**, **Remove-CsAllowedDomain** e **-CsBlockedDomain** do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ea09-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="5ea09-108">Para obter informações adicionais sobre como definir as configurações de contratação e o uso dos cmdlets do PowerShell, consulte **Tópicos relacionados** no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="5ea09-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="5ea09-109">A tabela de Resumo de registros DNS mostra as entradas necessárias para uma federação aberta ou detectável.</span><span class="sxs-lookup"><span data-stu-id="5ea09-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="5ea09-110">Se você não quiser implementar a descoberta de Federação, poderá decidir não configurar o \_sipfederationtls. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="5ea09-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="5ea09-111">Registro de *nome\> de domínio SIP. \<*</span><span class="sxs-lookup"><span data-stu-id="5ea09-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5ea09-112">Há cenários específicos nos quais você deve ter o _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="5ea09-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="5ea09-113"><EM> &lt;Nome&gt; de domínio SIP</EM> SRV Record, mas você não quer ter uma federação detectável.</span><span class="sxs-lookup"><span data-stu-id="5ea09-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="5ea09-114">Uma dessas instâncias é onde você implantou a mobilidade para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="5ea09-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="5ea09-115">A PNCH (Mobility Push Notification Clearinghouse) é um tipo especial de Federação usado para clientes móveis do Microsoft Lync no iPhone ou iPad com o Lync 2010 usando o cliente móvel do Lync ou o Windows Phone usando os clientes móveis do Lync 2010 ou Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5ea09-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="5ea09-116">O _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="5ea09-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="5ea09-117"><EM> &lt;Nome&gt; de domínio SIP</EM> O registro SRV é usado no caso de mobilidade e notificação por push.</span><span class="sxs-lookup"><span data-stu-id="5ea09-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="5ea09-118">Para reduzir esse problema e controlar sua descoberta, desmarque a configuração <STRONG>habilitar descoberta de domínio parceiro</STRONG> para desativar a descoberta.</span><span class="sxs-lookup"><span data-stu-id="5ea09-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="5ea09-119">Para configurar o protocolo de presença e mensagens extensíveis (XMPP) para a sua implantação, crie dois registros DNS (sistema de nomes de domínio) em um servidor DNS externo que resolverá os registros para o serviço de borda de acesso do servidor de borda ou do pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="5ea09-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="5ea09-120">Ao configurar o sistema de nomes de domínio (DNS) para conectividade de mensagens instantâneas públicas, você verá que a configuração que dá suporte a usuários externos será compatível com a conectividade de mensagens de chat públicas.</span><span class="sxs-lookup"><span data-stu-id="5ea09-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="5ea09-121">Se você já configurou o servidor de borda ou o pool de bordas, deve ter os registros DNS necessários para dar suporte à conectividade de IM pública.</span><span class="sxs-lookup"><span data-stu-id="5ea09-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="5ea09-122">Resumo de DNS-Federação SIP incluindo conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="5ea09-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ea09-123">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="5ea09-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5ea09-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="5ea09-124">FQDN</span></span></th>
<th><span data-ttu-id="5ea09-125">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="5ea09-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="5ea09-126">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="5ea09-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ea09-127">DNS/SRV/5061 externo</span><span class="sxs-lookup"><span data-stu-id="5ea09-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="5ea09-128">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ea09-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5ea09-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ea09-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5ea09-130">A interface externa do serviço de borda do Access é necessária para a descoberta automática de DNS da sua Federação para outros parceiros de Federação potenciais e é conhecida como "domínios SIP permitidos" (chamado de Federação aprimorada em versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="5ea09-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="5ea09-131">Esse registro SRV é necessário para a mobilidade e a equipe de compensação da notificação por push.</span><span class="sxs-lookup"><span data-stu-id="5ea09-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="5ea09-132">Nos casos em que há mais de um domínio SIP, crie e publique um registro SRV para cada domínio que terá clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="5ea09-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="5ea09-133">O serviço de notificação por push e o serviço de notificação por push da Apple podem não funcionar como esperado se não houver um registro SRV explícito para cada domínio SIP compatível com a implantação.</span><span class="sxs-lookup"><span data-stu-id="5ea09-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="5ea09-134">Resumo de DNS-mensagens extensíveis e protocolo de presença (XMPP)</span><span class="sxs-lookup"><span data-stu-id="5ea09-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ea09-135">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="5ea09-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5ea09-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="5ea09-136">FQDN</span></span></th>
<th><span data-ttu-id="5ea09-137">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="5ea09-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="5ea09-138">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="5ea09-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ea09-139">DNS/SRV/5269 externo</span><span class="sxs-lookup"><span data-stu-id="5ea09-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="5ea09-140">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ea09-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5ea09-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ea09-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5ea09-142">Interface externa de proxy XMPP no serviço de borda do Access ou no pool de bordas. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync nos quais o contato com contatos do XMPP é permitido pela configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao Usuário compatível com o Lync.</span><span class="sxs-lookup"><span data-stu-id="5ea09-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="5ea09-143">Um domínio XMPP permitido também deve ser configurado na política de parceiros federados do XMPP.</span><span class="sxs-lookup"><span data-stu-id="5ea09-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="5ea09-144">Consulte os tópicos em <strong>Consulte também</strong> para obter detalhes adicionais</span><span class="sxs-lookup"><span data-stu-id="5ea09-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ea09-145">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="5ea09-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5ea09-146">xmpp.contoso.com (por exemplo)</span><span class="sxs-lookup"><span data-stu-id="5ea09-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="5ea09-147">Endereço IP do serviço de borda de acesso em seu servidor de borda ou em um pool de bordas que hospeda o proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="5ea09-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="5ea09-148">Aponta para o serviço de borda de acesso ou o pool de bordas que hospeda o serviço de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="5ea09-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="5ea09-149">Geralmente, o registro SRV que você cria aponta para esse registro de host (A ou AAAA)</span><span class="sxs-lookup"><span data-stu-id="5ea09-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ea09-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="5ea09-150">See Also</span></span>


[<span data-ttu-id="5ea09-151">Configurando federação de XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea09-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="5ea09-152">Configurando notificações por push no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea09-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="5ea09-153">Habilitar ou desabilitar descoberta de parceiros de federação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea09-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="5ea09-154">Cenários de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea09-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="5ea09-155">Determinar requisitios de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea09-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="5ea09-156">Gerenciar domínios SIP federados para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea09-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

