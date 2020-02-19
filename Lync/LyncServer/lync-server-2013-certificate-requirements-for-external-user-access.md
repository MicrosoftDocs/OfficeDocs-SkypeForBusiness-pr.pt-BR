---
title: 'Lync Server 2013: requisitos de certificado para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0561c2d6b36090a9499abf360373cf0468cdbda8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="a7b90-102">Requisitos de certificado para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7b90-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7b90-103">_**Última modificação do tópico:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="a7b90-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="a7b90-104">O software de comunicações do Microsoft Lync Server 2013 suporta o uso de um único certificado público para interfaces externas de borda de acesso e webconferência, além do serviço de autenticação A/V.</span><span class="sxs-lookup"><span data-stu-id="a7b90-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="a7b90-105">A interface interna de Borda normalmente usa um certificado privado emitido por uma autoridade de certificação (CA) interna, mas também pode usar um certificado público, contanto que seja de uma CA pública confiável.</span><span class="sxs-lookup"><span data-stu-id="a7b90-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="a7b90-106">O proxy reverso em sua implantação usa um certificado público e criptografa a comunicação do proxy reverso para os clientes e do proxy reverso para os servidores internos usando HTTP (ou seja, Segurança da camada de transporte sobre HTTP).</span><span class="sxs-lookup"><span data-stu-id="a7b90-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="a7b90-107">Veja a seguir os requisitos para o certificado público usado para interfaces externas de Borda de acesso e de webconferência e para o serviço de autenticação A/V:</span><span class="sxs-lookup"><span data-stu-id="a7b90-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="a7b90-108">O certificado precisa ser emitido por uma CA pública aprovada que suporta nomes de entidade alternativos.</span><span class="sxs-lookup"><span data-stu-id="a7b90-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="a7b90-109">Para obter detalhes, consulte o artigo 929395 da base de dados de conhecimento da Microsoft, "parceiros de certificado de comunicações unificadas para o Exchange Server e o Communications Server" em [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span><span class="sxs-lookup"><span data-stu-id="a7b90-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="a7b90-p103">Se o certificado for usado em um pool de Borda, ele deverá ser criado como exportável, com o mesmo certificado usado em cada Servidor de Borda no pool de Borda. O requisito de chave privada exportável serve para o serviço de Autenticação A/V, que precisa usar a mesma chave privada em todos os Servidores de Borda no pool.</span><span class="sxs-lookup"><span data-stu-id="a7b90-p103">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool. The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="a7b90-112">Se você quiser maximizar o tempo de atividade para seus serviços de áudio/vídeo, revise os requisitos de certificado para implementar um certificado de serviço de borda A/V separado (ou seja, um certificado de serviço de borda A/V separado de outros fins de certificado de borda externa).</span><span class="sxs-lookup"><span data-stu-id="a7b90-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="a7b90-113">Para obter detalhes, consulte [Changes in Lync server 2013 que afetam o planejamento do servidor de borda](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [planejar certificados do servidor de borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) e [preparar certificados AV e OAuth no Lync Server 2013 usando-Reset-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span><span class="sxs-lookup"><span data-stu-id="a7b90-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="a7b90-114">O nome da entidade do certificado é o nome de domínio totalmente qualificado (FQDN) do serviço de borda de acesso ou VIP do balanceador de carga de hardware (por exemplo, access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a7b90-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="a7b90-115">).</span><span class="sxs-lookup"><span data-stu-id="a7b90-115">).</span></span> <span data-ttu-id="a7b90-116">O nome da entidade não pode ter um caractere curinga, deve ser um nome explícito.</span><span class="sxs-lookup"><span data-stu-id="a7b90-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7b90-117">Para o Lync Server 2013, isso não é mais um requisito, mas ainda é recomendado para compatibilidade com o Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="a7b90-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="a7b90-118">A lista de nomes de entidade alternativos contém os FQDNs do seguinte:</span><span class="sxs-lookup"><span data-stu-id="a7b90-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="a7b90-119">A interface externa do serviço de borda de acesso ou VIP do balanceador de carga de hardware (por exemplo, sip.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a7b90-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a7b90-120">Embora o nome de entidade do certificado seja igual ao FQDN da Borda de acesso, o nome de entidade alternativo também precisa conter o FQDN da Borda de acesso, pois a TLS ignora o nome de entidade e usa as entradas de nome de entidade alternativo para validação.</span><span class="sxs-lookup"><span data-stu-id="a7b90-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="a7b90-121">Da interface externa da Borda de webconferência ou VIP do balanceador de carga de hardware (por exemplo, webcon.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a7b90-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="a7b90-122">Se você estiver usando a configuração ou federação automática de cliente, inclua também quaisquer FQDNs de domínio de SIP usados em sua empresa (por exemplo, sip.contoso.com, sip.fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="a7b90-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="a7b90-123">O serviço de borda A/V não usa as entradas de nome de entidade ou de nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="a7b90-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7b90-124">A ordem dos FQDNs na lista de nomes de entidade alternativos não importa.</span><span class="sxs-lookup"><span data-stu-id="a7b90-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="a7b90-p106">Se você estiver implantando múltiplos Servidores de Borda com carga balanceada em um site, o certificado do serviço de autenticação A/V instalado em cada Servidor de Borda deverá ser da mesma CA e deverá usar a mesma chave privada. Observe que a chave privada do certificado precisa ser exportável, independentemente se for usada em um Servidor de Borda ou em muitos Servidores de Borda. Também deve ser exportável se você solicitar o certificado de qualquer computador além do Servidor de Borda. Como o serviço de autenticação A/V não usa o nome de entidade ou o nome alternativo de entidade, é possível reutilizar o certificado de Borda de acesso contanto que os requisitos de nome de entidade e de nome de entidade alternativo sejam atendidos para a Borda de acesso e para a Borda de webconferência e a chave privada do certificado seja exportável.</span><span class="sxs-lookup"><span data-stu-id="a7b90-p106">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key. Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers. It must also be exportable if you request the certificate from any computer other than the Edge Server. Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="a7b90-129">Os requisitos para o certificado privado (ou público) usado na interface interna de Borda são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="a7b90-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="a7b90-130">O certificado pode ser emitido por uma CA interna ou uma CA de certificado público aprovada.</span><span class="sxs-lookup"><span data-stu-id="a7b90-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="a7b90-p107">O nome de entidade do certificado é normalmente o FQDN da interface interna da Borda ou o VIP do balanceador de carga de hardware (por exemplo, lsedge.contoso.com). No entanto, é possível usar um certificado curinga na Borda interna.</span><span class="sxs-lookup"><span data-stu-id="a7b90-p107">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com). However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="a7b90-133">Nenhuma lista de nomes de entidade alternativos é necessária.</span><span class="sxs-lookup"><span data-stu-id="a7b90-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="a7b90-134">O proxy reverso em seus serviços de implantação solicitam:</span><span class="sxs-lookup"><span data-stu-id="a7b90-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="a7b90-135">Acesso de usuário externo para atender ao conteúdo das reuniões</span><span class="sxs-lookup"><span data-stu-id="a7b90-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="a7b90-136">Acesso de usuário externo para expandir e exibir membros dos grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="a7b90-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="a7b90-137">Acesso de usuário externo para arquivos baixáveis do Serviço de Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="a7b90-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="a7b90-138">Acesso de usuário externo ao cliente do Lync Web App</span><span class="sxs-lookup"><span data-stu-id="a7b90-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="a7b90-139">Acesso de usuário externo à página da web Configurações de Conferência Discada</span><span class="sxs-lookup"><span data-stu-id="a7b90-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="a7b90-140">Acesso de usuário externo ao Serviço de Informações de Local</span><span class="sxs-lookup"><span data-stu-id="a7b90-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="a7b90-141">Acesso de dispositivo externo ao Serviço de Atualização de Dispositivo e obtenção de atualizações</span><span class="sxs-lookup"><span data-stu-id="a7b90-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="a7b90-142">O proxy reverso publica as URLs de Componentes da web do servidor interno.</span><span class="sxs-lookup"><span data-stu-id="a7b90-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="a7b90-143">As URLs dos componentes Web são definidas no diretor, servidor front-end ou pool de front-ends como **Serviços Web externos** no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="a7b90-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="a7b90-144">Entradas curinga são suportadas no campo de nome de entidade alternativo do certificado atribuído ao proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="a7b90-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="a7b90-145">Para obter detalhes sobre como configurar a solicitação de certificado para o proxy reverso, consulte [solicitar e configurar um certificado para seu proxy http reverso no Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="a7b90-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a7b90-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="a7b90-146">See Also</span></span>


[<span data-ttu-id="a7b90-147">Suporte a certificados curinga no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7b90-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

