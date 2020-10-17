---
title: 'Lync Server 2013: requisitos de DNS para URLs simples'
description: 'Lync Server 2013: requisitos de DNS para URLs simples.'
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
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564957"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="68ac2-103">Requisitos de DNS para URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68ac2-103">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68ac2-104">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="68ac2-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="68ac2-105">O Lync Server 2013 oferece suporte a URLs simples, que facilitam a associação de reuniões para seus usuários e facilitam o acesso às ferramentas administrativas do Lync Server para seus administradores.</span><span class="sxs-lookup"><span data-stu-id="68ac2-105">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="68ac2-106">Para obter detalhes sobre URLs simples, consulte [Planning for Simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="68ac2-106">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="68ac2-107">O Lync Server suporta as seguintes três URLs simples: atender, discar e administrador. É necessário configurar URLs simples para a reunião e discagem, e a URL simples do administrador é opcional.</span><span class="sxs-lookup"><span data-stu-id="68ac2-107">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="68ac2-108">Os registros de DNS (Sistema de Nomes de Domínio) necessários para dar suporte às URLs simples dependem de como elas foram definidas e de você deseja dar suporte à recuperação de desastre para URLs simples.</span><span class="sxs-lookup"><span data-stu-id="68ac2-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="68ac2-109">Opção 1 de URL simples</span><span class="sxs-lookup"><span data-stu-id="68ac2-109">Simple URL Option 1</span></span>

<span data-ttu-id="68ac2-110">Na Opção 1, você cria uma nova URL de base para cada URL simples.</span><span class="sxs-lookup"><span data-stu-id="68ac2-110">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="68ac2-p103">Quando um usuário clica no link de reunião de uma URL simples, o servidor que o registro do DNS A resolve determina o software do cliente correto para iniciar. Depois que o software de cliente é iniciado, ele se comunica automaticamente com o pool em que a conferência está hospedada. Assim, os usuários são encaminhados ao servidor apropriado para o conteúdo da reunião, independente do servidor ou pool para o qual os registros de DNS A da URL resolvem.</span><span class="sxs-lookup"><span data-stu-id="68ac2-p103">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start. After the client software is started, it automatically communicates with the pool where the conference is hosted. This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="68ac2-114">Opção 1 de URL simples</span><span class="sxs-lookup"><span data-stu-id="68ac2-114">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68ac2-115"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="68ac2-115"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="68ac2-116"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="68ac2-116"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ac2-117">Cumpra</span><span class="sxs-lookup"><span data-stu-id="68ac2-117">Meet</span></span></p></td>
<td><p><span data-ttu-id="68ac2-118">https://meet.contoso.com, https://meet.fabrikam.com e assim por diante (um para cada domínio SIP em sua organização)</span><span class="sxs-lookup"><span data-stu-id="68ac2-118">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ac2-119">Discagem</span><span class="sxs-lookup"><span data-stu-id="68ac2-119">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ac2-120">Administrador</span><span class="sxs-lookup"><span data-stu-id="68ac2-120">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="68ac2-121">Se você usar a Opção 1, defina o seguinte:</span><span class="sxs-lookup"><span data-stu-id="68ac2-121">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="68ac2-p104">Para cada URL simples Reunir, você precisa de um registro DNS A que resolva a URL para o endereço IP do Diretor, se estiver implantado. Do contrário, ele deve resolver para o endereço IP do balanceador de carga ou do pool de Front-End. Se você não implantou um pool e está usando a implantação de servidor do Standard Edition, o registro de DNS A deve resolver para o endereço IP do servidor do Standard Edition na sua organização.</span><span class="sxs-lookup"><span data-stu-id="68ac2-p104">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="68ac2-125">Se você tiver mais de um domínio SIP em sua organização e usar essa opção, crie URLs simples Reunir para cada domínio SIP; um registro de DNS A é necessário para cada uma dessas URLs.</span><span class="sxs-lookup"><span data-stu-id="68ac2-125">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="68ac2-126">Por exemplo, se você tiver o contoso.com e o fabrikam.com, criará registros DNS A para o https://meet.contoso.com e o https://meet.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="68ac2-126">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="68ac2-127">Ou então, se você tiver vários domínios SIP e deseja minimizar os registros de DNS e requisitos de certificado para essas URLs simples, use a Opção 3 descrita adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="68ac2-127">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="68ac2-p106">Para a URL simples Discar, você precisa de um registro DNS A que resolva a URL para o endereço IP do Diretor, se estiver implantado. Do contrário, ele deve resolver para o endereço IP do balanceador de carga ou do pool de Front-End. Se você não implantou um pool e está usando a implantação de servidor do Standard Edition, o registro de DNS A deve resolver para o endereço IP do servidor do Standard Edition na sua organização.</span><span class="sxs-lookup"><span data-stu-id="68ac2-p106">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="68ac2-p107">A URL simples Admin é apenas interna. Ela exige um registro DNS A que resolva a URL para o endereço IP do Diretor, se estiver implantado. Do contrário, ele deve resolver para o endereço IP do balanceador de carga ou do pool de Front-End. Se você não implantou um pool e está usando a implantação de servidor do Standard Edition, o registro de DNS A deve resolver para o endereço IP do servidor do Standard Edition na sua organização.</span><span class="sxs-lookup"><span data-stu-id="68ac2-p107">The Admin simple URL is internal only. It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="68ac2-135">Opção 2 de URL simples</span><span class="sxs-lookup"><span data-stu-id="68ac2-135">Simple URL Option 2</span></span>

<span data-ttu-id="68ac2-p108">Na Opção 2, as URLs simples Reunir, Discar e Admin têm uma URL de base comum, como lync.contoso.com. Portanto, você só precisa de um registro de DNS A para essas URLs simples, que resolve lync.contoso.com para o endereço IP de um pool do Diretor ou pool de Front-End. Se você não implantou um pool e está usando a implantação de servidor do Standard Edition, o registro de DNS A deve resolver para o endereço IP do servidor do Standard Edition na sua organização.</span><span class="sxs-lookup"><span data-stu-id="68ac2-p108">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com. Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="68ac2-139">Observe que se você tiver mais de um domínio SIP em sua organização, deve criar URLs simples Reunir para cada domínio SIP; um registro de DNS A é necessário para cada uma dessas URLs.</span><span class="sxs-lookup"><span data-stu-id="68ac2-139">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="68ac2-140">Neste exemplo, embora três URLs simples sejam baseadas no lync.contoso.com, uma URL simples Reunir adicional para fabrikam.com é configurada com uma URL de base diferente.</span><span class="sxs-lookup"><span data-stu-id="68ac2-140">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="68ac2-141">Neste exemplo, você deve criar registros DNS A para o https://lync.contoso.com e o https://lync.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="68ac2-141">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="68ac2-142">A Opção 3 de URL Simples mostra outra maneira de manipular a nomeação e os registros de DNS A, se você tiver vários domínios SIP.</span><span class="sxs-lookup"><span data-stu-id="68ac2-142">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="68ac2-143">Opção 2 de URL simples</span><span class="sxs-lookup"><span data-stu-id="68ac2-143">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68ac2-144"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="68ac2-144"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="68ac2-145"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="68ac2-145"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ac2-146">Cumpra</span><span class="sxs-lookup"><span data-stu-id="68ac2-146">Meet</span></span></p></td>
<td><p><span data-ttu-id="68ac2-147">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet e assim por diante (um para cada domínio SIP em sua organização)</span><span class="sxs-lookup"><span data-stu-id="68ac2-147">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ac2-148">Discagem</span><span class="sxs-lookup"><span data-stu-id="68ac2-148">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ac2-149">Administrador</span><span class="sxs-lookup"><span data-stu-id="68ac2-149">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="68ac2-150">Opção 3 de URL simples</span><span class="sxs-lookup"><span data-stu-id="68ac2-150">Simple URL Option 3</span></span>

<span data-ttu-id="68ac2-p110">A Opção 3 é muito útil se você tem diversos domínios SIP, e deseja que eles tenham URLs simples separadas, mas deseja minimizar os registros de DNS e requisitos de certificado para essas URLs simples. Neste exemplo, você só precisa de um registro de DNS A que resolve lync.contoso.com para o endereço IP de um pool do Diretor ou pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="68ac2-p110">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs. In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="68ac2-153">Opção 3 de URL simples</span><span class="sxs-lookup"><span data-stu-id="68ac2-153">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68ac2-154"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="68ac2-154"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="68ac2-155"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="68ac2-155"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ac2-156">Cumpra</span><span class="sxs-lookup"><span data-stu-id="68ac2-156">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68ac2-157">Discagem</span><span class="sxs-lookup"><span data-stu-id="68ac2-157">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ac2-158">Administrador</span><span class="sxs-lookup"><span data-stu-id="68ac2-158">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="68ac2-159">Opção de recuperação de desastres para URLs simples</span><span class="sxs-lookup"><span data-stu-id="68ac2-159">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="68ac2-160">Se você tiver vários sites que contenham pools de front-ends e o seu provedor de DNS oferecer suporte ao GeoDNS, você poderá configurar seus registros DNS para URLs simples para oferecer suporte à recuperação de desastres, de modo que a funcionalidade de URL simples continue mesmo que um pool de front-ends inteiro seja desativado.</span><span class="sxs-lookup"><span data-stu-id="68ac2-160">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="68ac2-161">Este recurso de recuperação de desastres dá suporte às URLs simples Meet e Dial-In.</span><span class="sxs-lookup"><span data-stu-id="68ac2-161">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="68ac2-p112">Para fazer essa configuração, crie dois endereços de GeoDNS. Cada endereço contém dois registros DNS A ou CNAME que são decompostos em dois pools que são unidos para fins de recuperação de desastres. Um endereço de GeoDNS é usado para acesso interno e é decomposto no FQDN da Web interno ou endereço IP do balanceador de carga dos dois pools. O outro endereço GeoDNS é usado para acesso externo e é decomposto no FQDN da Web externo ou endereço IP do balanceador de carga dos dois pools. Veja a seguir um exemplo da URL simples Meet, usando os FQDNs dos pools:</span><span class="sxs-lookup"><span data-stu-id="68ac2-p112">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="68ac2-167">Em seguida, crie registros CNAME que decomponham sua URL simples Meet (como meet.contoso.com) nos dois endereços de GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="68ac2-167">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="68ac2-168">Se sua rede usar <EM>grampeamento</EM> (roteamento de todo o tráfego de URLs simples pelos links externos, inclusive o tráfego que vem de dentro de sua organização), será possível simplesmente configurar os endereços de GeoDNS externos e decompor sua URL simples Meet apenas nesses endereços externos.</span><span class="sxs-lookup"><span data-stu-id="68ac2-168">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="68ac2-169">Quando esse método é usado, é possível configurar cada endereço de GeoDNS para usar um método de round robin e distribuir solicitações nos dois pools ou para fazer a conexão principalmente com um pool (como o pool localizado geograficamente mais perto) e usar o outro pool apenas em caso de falhas de conectividade.</span><span class="sxs-lookup"><span data-stu-id="68ac2-169">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="68ac2-170">Você pode definir a mesma configuração para a URL simples Dial-In.</span><span class="sxs-lookup"><span data-stu-id="68ac2-170">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="68ac2-171">Para fazer isso, crie registros adicionais como os do exemplo anterior, substituindo `dialin` para `meet` nos registros DNS.</span><span class="sxs-lookup"><span data-stu-id="68ac2-171">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="68ac2-172">Para a URL simples Admin, use uma das três opções listadas anteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="68ac2-172">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="68ac2-173">Depois que esta configuração é definida, é preciso usar um aplicativo de monitoramento para definir que o monitoramento de HTTP rastreie as falhas.</span><span class="sxs-lookup"><span data-stu-id="68ac2-173">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="68ac2-174">Para acesso externo, monitor para garantir que o HTTPS Obtém solicitações de descoberta automática para o FQDN da Web externo ou o endereço IP do balanceador de carga para os dois pools são bem-sucedidos.</span><span class="sxs-lookup"><span data-stu-id="68ac2-174">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="68ac2-175">Por exemplo, as solicitações a seguir não devem conter nenhum cabeçalho **ACCEPT** e devem retornar **200 OK**.</span><span class="sxs-lookup"><span data-stu-id="68ac2-175">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="68ac2-p115">Para acesso interno, é preciso monitorar a porta 5061 no FQDN da Web interno ou endereço IP do balanceador de carga dos dois pools. Se alguma falha de conectividade for detectada, o VIP desses pools deverão fechar as portas 80, 443 e 444.</span><span class="sxs-lookup"><span data-stu-id="68ac2-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

