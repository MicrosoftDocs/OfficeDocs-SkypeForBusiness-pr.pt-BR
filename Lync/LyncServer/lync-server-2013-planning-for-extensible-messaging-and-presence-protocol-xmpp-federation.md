---
title: Planejando a Federação do protocolo de mensagens extensíveis e presença (XMPP)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4e1d8f9b7f164dd9e83f556dcc57809619278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="7db85-102">Como planejar a Federação do protocolo de presença e de mensagens extensíveis (XMPP) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7db85-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7db85-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7db85-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7db85-104">As versões anteriores do Lync Server e do Office Communications Server forneciam um gateway de protocolo de presença e mensagens (XMPP) extensível que poderia ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP.</span><span class="sxs-lookup"><span data-stu-id="7db85-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="7db85-105">No Microsoft Lync Server 2013, a funcionalidade XMPP pode ser implantada como um recurso.</span><span class="sxs-lookup"><span data-stu-id="7db85-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="7db85-106">A funcionalidade XMPP é instalada em duas partes: um proxy do XMPP que é executado no servidor de borda e o gateway de XMPP que é executado nos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7db85-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="7db85-107">A implantação e a configuração do XMPP são abordadas na [implantação de acesso ao usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) você planeja oferecer suporte a XMPP em sua organização definindo regras de porta e protocolo em seu firewall, configuração de certificados e adicionar DNS registos.</span><span class="sxs-lookup"><span data-stu-id="7db85-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="7db85-108">Os tópicos a seguir nesta seção resumem as informações que você precisará para planejar com êxito a Federação do XMPP para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="7db85-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="7db85-p103">O recurso XMPP do Lync Server 2013 é testado pela Microsoft e ela oferece suporte para federação de mensagens instantâneas com o Google Talk. Para quaisquer outros sistemas XMPP, entre em contato com o fornecedor do mesmo para verificar se eles suportam federação com o Lync Server 2013, e para quaisquer recomendações de implantação ou solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="7db85-p103">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7db85-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7db85-111">In This Section</span></span>

  - [<span data-ttu-id="7db85-112">Resumo de certificados – Federação de protocolo de presença e mensagens extensíveis (XMPP) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7db85-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="7db85-113">Resumo de portas – Federação de protocolo de presença e mensagens extensíveis (XMPP) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7db85-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="7db85-114">Resumo de DNS-Federação de protocolo de presença e mensagens extensíveis (XMPP) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7db85-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7db85-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="7db85-115">See Also</span></span>


[<span data-ttu-id="7db85-116">Configurando federação de XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7db85-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="7db85-117">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7db85-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="7db85-118">Gerenciar parceiros XMPP federados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7db85-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="7db85-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7db85-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="7db85-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7db85-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="7db85-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7db85-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

