---
title: 'Lync Server 2013: Requisitos de DNS para URLs simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfc827a1cd48bdc6a7a15b8ba54f7ac451d1b352
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="c88ba-102">Requisitos de DNS para URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c88ba-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c88ba-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c88ba-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c88ba-104">O Lync Server 2013 oferece suporte a URLs simples, que facilitam o ingresso em reuniões para seus usuários e facilitam a obtenção de ferramentas administrativas do Lync Server para seus administradores.</span><span class="sxs-lookup"><span data-stu-id="c88ba-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="c88ba-105">Para obter detalhes sobre URLs simples, consulte [planejando URLs simples no Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="c88ba-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="c88ba-106">O Lync Server oferece suporte a estas três URLs simples: atender, discagem e administrador. Você é obrigado a configurar URLs simples para atender e discagem, e a URL simples de administrador é opcional.</span><span class="sxs-lookup"><span data-stu-id="c88ba-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="c88ba-107">Os registros de sistema de nome de domínio (DNS) que você precisa para dar suporte a URLs simples dependem de como você definiu essas URLs simples e se deseja dar suporte à recuperação de desastres para URLs simples.</span><span class="sxs-lookup"><span data-stu-id="c88ba-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="c88ba-108">Opção de URL simples 1</span><span class="sxs-lookup"><span data-stu-id="c88ba-108">Simple URL Option 1</span></span>

<span data-ttu-id="c88ba-109">Na opção 1, você cria uma nova URL base para cada URL simples.</span><span class="sxs-lookup"><span data-stu-id="c88ba-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="c88ba-110">Quando um usuário clica em um link de reunião de URL simples, o servidor ao qual o registro DNS é resolvido determina o software cliente correto para iniciar.</span><span class="sxs-lookup"><span data-stu-id="c88ba-110">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start.</span></span> <span data-ttu-id="c88ba-111">Depois que o software cliente é iniciado, ele se comunica automaticamente com o pool em que a conferência está hospedada.</span><span class="sxs-lookup"><span data-stu-id="c88ba-111">After the client software is started, it automatically communicates with the pool where the conference is hosted.</span></span> <span data-ttu-id="c88ba-112">Dessa forma, os usuários são direcionados ao servidor apropriado para o conteúdo da reunião, independentemente de qual servidor ou pool a URL simples dos registros DNS a resolver.</span><span class="sxs-lookup"><span data-stu-id="c88ba-112">This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="c88ba-113">Opção de URL simples 1</span><span class="sxs-lookup"><span data-stu-id="c88ba-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c88ba-114"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="c88ba-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c88ba-115"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="c88ba-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c88ba-116">Atendimento</span><span class="sxs-lookup"><span data-stu-id="c88ba-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="c88ba-117">https://meet.contoso.com, https://meet.fabrikam.come assim por diante (um para cada domínio SIP em sua organização)</span><span class="sxs-lookup"><span data-stu-id="c88ba-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c88ba-118">Discagem</span><span class="sxs-lookup"><span data-stu-id="c88ba-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c88ba-119">Locatário</span><span class="sxs-lookup"><span data-stu-id="c88ba-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c88ba-120">Se você usar a opção 1, deverá definir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c88ba-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="c88ba-121">Para cada uma das URLs mais simples, você precisa de um registro de DNS que resolva a URL para o endereço IP do diretor, se você tiver implantado.</span><span class="sxs-lookup"><span data-stu-id="c88ba-121">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="c88ba-122">Caso contrário, ele deve ser resolvido para o endereço IP do balanceador de carga de um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="c88ba-122">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="c88ba-123">Se você não implantou um pool e está usando uma implantação do servidor Standard Edition, o registro DNS a deve ser resolvido para o endereço IP de um servidor Standard Edition em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c88ba-123">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="c88ba-124">Se você tiver mais de um domínio SIP em sua organização e usar essa opção, será necessário criar URLs simples para cada domínio SIP e precisará de um registro DNS A para cada URL simples.</span><span class="sxs-lookup"><span data-stu-id="c88ba-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="c88ba-125">Por exemplo, se você tiver contoso.com e fabrikam.com, criará registros DNS A para ambos https://meet.contoso.com e. https://meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c88ba-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="c88ba-126">Como alternativa, se você tiver vários domínios SIP e quiser minimizar o registro DNS e os requisitos de certificado para essas URLs simples, use a opção 3 conforme descrito mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c88ba-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="c88ba-127">Para a URL simples de discagem, você precisa de um registro de DNS que resolva a URL para o endereço IP do diretor, se você tiver uma implantação.</span><span class="sxs-lookup"><span data-stu-id="c88ba-127">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="c88ba-128">Caso contrário, ele deve ser resolvido para o endereço IP do balanceador de carga de um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="c88ba-128">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="c88ba-129">Se você não implantou um pool e está usando uma implantação do servidor Standard Edition, o registro DNS a deve ser resolvido para o endereço IP de um servidor Standard Edition em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c88ba-129">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="c88ba-130">A URL simples de administrador é somente interna.</span><span class="sxs-lookup"><span data-stu-id="c88ba-130">The Admin simple URL is internal only.</span></span> <span data-ttu-id="c88ba-131">Ele exige um registro de DNS que resolva a URL para o endereço IP do diretor, se você tiver uma implantação.</span><span class="sxs-lookup"><span data-stu-id="c88ba-131">It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="c88ba-132">Caso contrário, ele deve ser resolvido para o endereço IP do balanceador de carga de um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="c88ba-132">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="c88ba-133">Se você não implantou um pool e está usando uma implantação do servidor Standard Edition, o registro DNS a deve ser resolvido para o endereço IP de um servidor Standard Edition em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c88ba-133">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="c88ba-134">Opção de URL simples 2</span><span class="sxs-lookup"><span data-stu-id="c88ba-134">Simple URL Option 2</span></span>

<span data-ttu-id="c88ba-135">Com a opção 2, as URLs de reunião, discada e administrador simples têm uma URL base comum, como lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c88ba-135">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com.</span></span> <span data-ttu-id="c88ba-136">Portanto, você precisa de apenas um registro de DNS para essas URLs simples, o que resolve lync.contoso.com para o endereço IP de um pool de directors ou de front-end.</span><span class="sxs-lookup"><span data-stu-id="c88ba-136">Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span> <span data-ttu-id="c88ba-137">Se você não implantou um pool e está usando uma implantação do servidor Standard Edition, o registro DNS a deve ser resolvido para o endereço IP de um servidor Standard Edition em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c88ba-137">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="c88ba-138">Observe que, se você tiver mais de um domínio SIP em sua organização, ainda deverá criar URLs simples para cada domínio SIP e precisará de um registro DNS A para cada uma das URLs simples.</span><span class="sxs-lookup"><span data-stu-id="c88ba-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="c88ba-139">Neste exemplo, enquanto três URLs simples são todas baseadas no lync.contoso.com, uma URL simples de reunião simples para fabrikam.com é configurada com uma URL base diferente.</span><span class="sxs-lookup"><span data-stu-id="c88ba-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="c88ba-140">Neste exemplo, você deve criar registros DNS A para ambos https://lync.contoso.com e. https://lync.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c88ba-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="c88ba-141">A opção de URL simples 3 mostra outra maneira de lidar com nomes e registros DNS A, se você tiver vários domínios SIP.</span><span class="sxs-lookup"><span data-stu-id="c88ba-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="c88ba-142">Opção de URL simples 2</span><span class="sxs-lookup"><span data-stu-id="c88ba-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c88ba-143"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="c88ba-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c88ba-144"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="c88ba-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c88ba-145">Atendimento</span><span class="sxs-lookup"><span data-stu-id="c88ba-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="c88ba-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meete assim por diante (um para cada domínio SIP em sua organização)</span><span class="sxs-lookup"><span data-stu-id="c88ba-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c88ba-147">Discagem</span><span class="sxs-lookup"><span data-stu-id="c88ba-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c88ba-148">Locatário</span><span class="sxs-lookup"><span data-stu-id="c88ba-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="c88ba-149">Opção de URL simples 3</span><span class="sxs-lookup"><span data-stu-id="c88ba-149">Simple URL Option 3</span></span>

<span data-ttu-id="c88ba-150">A opção 3 será mais útil se você tiver muitos domínios SIP e quiser que eles tenham URLs simples separadas, mas desejem minimizar o registro DNS e os requisitos de certificado para essas URLs simples.</span><span class="sxs-lookup"><span data-stu-id="c88ba-150">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> <span data-ttu-id="c88ba-151">Neste exemplo, você precisa apenas de um registro DNS A, que resolve lync.contoso.com para o endereço IP de um pool de directors ou um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="c88ba-151">In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="c88ba-152">Opção de URL simples 3</span><span class="sxs-lookup"><span data-stu-id="c88ba-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c88ba-153"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="c88ba-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c88ba-154"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="c88ba-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c88ba-155">Atendimento</span><span class="sxs-lookup"><span data-stu-id="c88ba-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c88ba-156">Discagem</span><span class="sxs-lookup"><span data-stu-id="c88ba-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c88ba-157">Locatário</span><span class="sxs-lookup"><span data-stu-id="c88ba-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="c88ba-158">Opção de recuperação de desastres para URLs simples</span><span class="sxs-lookup"><span data-stu-id="c88ba-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="c88ba-159">Se você tiver vários sites que contenham pools de front-end e o seu provedor de DNS oferecer suporte a GeoDNS, você poderá configurar seus registros DNS para URLs simples para dar suporte à recuperação de desastres, para que a funcionalidade de URL simples continue mesmo que um pool de front-end inteiro seja desligado.</span><span class="sxs-lookup"><span data-stu-id="c88ba-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="c88ba-160">Este recurso de recuperação de desastres dá suporte a URLs simples e de reunião discada.</span><span class="sxs-lookup"><span data-stu-id="c88ba-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="c88ba-161">Para configurar isso, crie dois endereços do GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="c88ba-161">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="c88ba-162">Cada endereço tem dois registros DNS A ou CNAME que são resolvidos para dois pools que são emparelhados para fins de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="c88ba-162">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="c88ba-163">Um endereço GeoDNS é usado para acesso interno e é resolvido para o FQDN da Web interna ou o endereço IP do balanceador de carga para os dois pools.</span><span class="sxs-lookup"><span data-stu-id="c88ba-163">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="c88ba-164">O outro endereço GeoDNS é usado para acesso externo e resolve para o FQDN da Web externo ou o endereço IP do balanceador de carga para os dois pools.</span><span class="sxs-lookup"><span data-stu-id="c88ba-164">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="c88ba-165">Veja a seguir um exemplo de URL simples de reunião, usando os FQDNs dos grupos.</span><span class="sxs-lookup"><span data-stu-id="c88ba-165">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="c88ba-166">Em seguida, crie registros CNAME que resolvem sua URL simples de reunião (como meet.contoso.com) para os dois endereços GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="c88ba-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="c88ba-167">Se a sua rede usa <EM>hairpinning</EM> (direcionar todo o tráfego de URL simples por meio do link externo, incluindo o tráfego que vem de dentro da sua organização), você pode apenas configurar o endereço de GeoDNS externo e resolver seu encontro URL simples para apenas esse endereço externo.</span><span class="sxs-lookup"><span data-stu-id="c88ba-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="c88ba-168">Ao usar esse método, você pode configurar cada endereço do GeoDNS para usar um método de rodízio para distribuir solicitações para os dois pools ou para se conectar principalmente a um pool (como o pool localizado geograficamente) e usar o outro pool somente em caso de falha na conectividade.</span><span class="sxs-lookup"><span data-stu-id="c88ba-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="c88ba-169">Você pode configurar a mesma configuração para a URL simples de discagem.</span><span class="sxs-lookup"><span data-stu-id="c88ba-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="c88ba-170">Para fazer isso, crie registros adicionais como os do exemplo anterior, substituindo `dialin` para `meet` os registros DNS.</span><span class="sxs-lookup"><span data-stu-id="c88ba-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="c88ba-171">Para a URL simples do administrador, use uma das três opções listadas anteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="c88ba-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="c88ba-172">Depois que essa configuração é configurada, você deve usar um aplicativo de monitoramento para configurar o monitoramento HTTP para observar falhas.</span><span class="sxs-lookup"><span data-stu-id="c88ba-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="c88ba-173">Para acesso externo, monitor para ter certeza de que o HTTPS Obtém solicitações de descoberta automática para o FQDN da Web externa ou o endereço IP do balanceador de carga para os dois pools são bem-sucedidos.</span><span class="sxs-lookup"><span data-stu-id="c88ba-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="c88ba-174">Por exemplo, as seguintes solicitações não devem conter cabeçalho **Accept** e devem retornar **200 OK**.</span><span class="sxs-lookup"><span data-stu-id="c88ba-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

<span data-ttu-id="c88ba-175">Para acesso interno, você deve monitorar a porta 5061 no FQDN da Web interno ou o endereço IP do balanceador de carga para os dois pools.</span><span class="sxs-lookup"><span data-stu-id="c88ba-175">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="c88ba-176">Se alguma falha de conectividade for detectada, o VIP para esses pools deverá fechar as portas 80, 443 e 444.</span><span class="sxs-lookup"><span data-stu-id="c88ba-176">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

