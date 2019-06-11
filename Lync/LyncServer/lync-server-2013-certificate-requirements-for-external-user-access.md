---
title: 'Lync Server 2013: Requisitos de certificado para acesso do usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e7a0802cee8b91e18eaf50e5c2c3942ca54308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="b7a34-102">Requisitos de certificado para acesso do usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7a34-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7a34-103">_**Tópico da última modificação:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="b7a34-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="b7a34-104">O software de comunicação do Microsoft Lync Server 2013 dá suporte ao uso de um único certificado público para interfaces externas Edge de acesso e Web Conferencing, além do serviço de autenticação A/V.</span><span class="sxs-lookup"><span data-stu-id="b7a34-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="b7a34-105">A interface interna Edge geralmente usa um certificado particular emitido por uma autoridade de certificação interna (CA), mas também pode usar um certificado público, desde que ele seja de uma autoridade de certificação pública confiável.</span><span class="sxs-lookup"><span data-stu-id="b7a34-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="b7a34-106">O proxy inverso em sua implantação usa um certificado público e criptografa a comunicação do proxy reverso para os clientes e o proxy reverso para servidores internos usando HTTP (ou seja, Transport Layer Security via HTTP).</span><span class="sxs-lookup"><span data-stu-id="b7a34-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="b7a34-107">Veja a seguir os requisitos para o certificado público usado para interfaces externas de Edge de acesso e Web proconferência e o serviço de autenticação A/V:</span><span class="sxs-lookup"><span data-stu-id="b7a34-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="b7a34-108">O certificado deve ser emitido por uma autoridade de certificação pública aprovada que seja compatível com o nome alternativo do assunto.</span><span class="sxs-lookup"><span data-stu-id="b7a34-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="b7a34-109">Para obter detalhes, consulte o artigo 929395 da base de dados de conhecimento Microsoft, "parceiros de certificado de comunicação unificada [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)para Exchange Server e Communications Server" em.</span><span class="sxs-lookup"><span data-stu-id="b7a34-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="b7a34-110">Se o certificado for usado em um pool de bordas, ele deverá ser criado como exportável, com o mesmo certificado usado em cada servidor de borda no pool de borda.</span><span class="sxs-lookup"><span data-stu-id="b7a34-110">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="b7a34-111">O requisito de chave privada de exportável é para os fins do serviço de autenticação A/V, que deve usar a mesma chave privada em todos os servidores de borda do pool.</span><span class="sxs-lookup"><span data-stu-id="b7a34-111">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="b7a34-112">Se você quiser maximizar o tempo de atividade para seus serviços de áudio/vídeo, examine os requisitos de certificado para implementar um certificado de serviço de borda a/V separado (ou seja, um certificado de serviço de borda A/V separado das outras finalidades de certificado de borda externa).</span><span class="sxs-lookup"><span data-stu-id="b7a34-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="b7a34-113">Para obter detalhes, consulte [alterações no Lync server 2013 que afetam o planejamento do servidor de borda](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [planejar certificados do servidor de borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) e [preparar certificados AV e OAuth no Lync Server 2013 using-roll Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span><span class="sxs-lookup"><span data-stu-id="b7a34-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="b7a34-114">O nome do requerente do certificado é o nome de domínio totalmente qualificado do serviço de borda de acesso (FQDN) ou VIP do balanceador de carga de hardware (por exemplo, access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b7a34-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="b7a34-115">).</span><span class="sxs-lookup"><span data-stu-id="b7a34-115"></span></span> <span data-ttu-id="b7a34-116">O nome do requerente não pode ter um caractere curinga, ele deve ser um nome explícito.</span><span class="sxs-lookup"><span data-stu-id="b7a34-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7a34-117">Para o Lync Server 2013, isso não é mais necessário, mas ainda é recomendado para compatibilidade com o Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="b7a34-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="b7a34-118">A lista de nomes alternativos de entidades contém os FQDNs dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="b7a34-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="b7a34-119">A interface externa do serviço de borda do Access ou VIP do balanceador de carga de hardware (por exemplo, sip.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b7a34-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b7a34-120">Embora o nome do requerente do certificado seja igual ao FQDN do conector de acesso, o nome alternativo do assunto também deve conter o FQDN de borda de acesso porque a segurança da camada de transporte (TLS) ignora o nome do assunto e usa as entradas de nome alternativo do assunto para validação.</span><span class="sxs-lookup"><span data-stu-id="b7a34-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="b7a34-121">A interface de borda externa Web de Webconferência ou VIP de balanceador de carga de hardware (por exemplo, webcon.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b7a34-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="b7a34-122">Se você estiver usando a configuração automática do cliente ou a Federação, inclua também qualquer FQDN do domínio SIP usado dentro da sua empresa (por exemplo, sip.contoso.com, sip.fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="b7a34-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="b7a34-123">O serviço de borda A/V não usa as entradas de nome de assunto ou de nomes alternativos de assunto.</span><span class="sxs-lookup"><span data-stu-id="b7a34-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7a34-124">A ordem dos FQDNs na lista nomes alternativos de entidades não importa.</span><span class="sxs-lookup"><span data-stu-id="b7a34-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="b7a34-125">Se você estiver implantando vários servidores Edge com carga balanceada em um site, o certificado do serviço de autenticação A/V que é instalado em cada servidor de borda deve ser da mesma CA e deve usar a mesma chave privada.</span><span class="sxs-lookup"><span data-stu-id="b7a34-125">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="b7a34-126">Observe que a chave privada do certificado deve ser exportável, independentemente de ser usada em um servidor de borda ou muitos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="b7a34-126">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="b7a34-127">Ele também deve ser exportável se você solicitar o certificado de qualquer computador que não seja o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="b7a34-127">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="b7a34-128">Como o serviço de autenticação A/V não usa o nome da entidade ou o nome alternativo do assunto, você pode reutilizar o certificado de borda do Access desde que o nome da entidade e os requisitos de nome alternativo do assunto sejam atendidos para a borda do Access e para a borda de Webconferência e a chave privada do certificado é exportável.</span><span class="sxs-lookup"><span data-stu-id="b7a34-128">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="b7a34-129">Os requisitos para o certificado privado (ou público) usado para a interface interna de borda são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="b7a34-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="b7a34-130">O certificado pode ser emitido por uma autoridade de certificação interna ou uma CA de certificado público aprovada.</span><span class="sxs-lookup"><span data-stu-id="b7a34-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="b7a34-131">O nome do requerente do certificado geralmente é o FQDN ou o VIP da interface interna do hardware ou o VIP do balanceador de carga de hardware (por exemplo, lsedge.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b7a34-131">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="b7a34-132">No entanto, você pode usar um certificado curinga na borda interna.</span><span class="sxs-lookup"><span data-stu-id="b7a34-132">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="b7a34-133">Nenhuma lista de nomes alternativos de entidades é necessária.</span><span class="sxs-lookup"><span data-stu-id="b7a34-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="b7a34-134">O proxy reverso em seus serviços de implantação solicita:</span><span class="sxs-lookup"><span data-stu-id="b7a34-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="b7a34-135">Acesso do usuário externo ao conteúdo da reunião para reuniões</span><span class="sxs-lookup"><span data-stu-id="b7a34-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="b7a34-136">Acesso de usuário externo para expandir e exibir membros de grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="b7a34-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="b7a34-137">Acesso de usuário externo a arquivos que podem ser baixados do serviço de catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="b7a34-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="b7a34-138">Acesso de usuário externo ao cliente do Lync Web App</span><span class="sxs-lookup"><span data-stu-id="b7a34-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="b7a34-139">Acesso de usuário externo à página da Web configurações de conferência discada</span><span class="sxs-lookup"><span data-stu-id="b7a34-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="b7a34-140">Acesso de usuário externo ao serviço de informações de localização</span><span class="sxs-lookup"><span data-stu-id="b7a34-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="b7a34-141">Acesso do dispositivo externo ao serviço de atualização de dispositivo e obter atualizações</span><span class="sxs-lookup"><span data-stu-id="b7a34-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="b7a34-142">O proxy reverso publica as URLs dos Web Components do servidor interno.</span><span class="sxs-lookup"><span data-stu-id="b7a34-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="b7a34-143">As URLs dos Web Components são definidas no director, servidor front-end ou pool de front-end como **Serviços Web externos** no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="b7a34-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="b7a34-144">Há suporte para entradas curinga no campo nome alternativo do assunto do certificado atribuído ao proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="b7a34-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="b7a34-145">Para obter detalhes sobre como configurar a solicitação de certificado para o proxy reverso, consulte [solicitar e configurar um certificado para seu proxy http reverso no Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="b7a34-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b7a34-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="b7a34-146">See Also</span></span>


[<span data-ttu-id="b7a34-147">Suporte a certificado curinga no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7a34-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

