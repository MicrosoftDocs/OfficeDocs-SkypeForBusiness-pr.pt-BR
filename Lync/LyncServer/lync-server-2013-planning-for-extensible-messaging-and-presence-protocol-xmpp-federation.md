---
title: Planejando a Federação do protocolo XMPP (Extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f95a8e53de2c11473d8424eb2bc794e41aa7d1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="d215e-102">Planejando a Federação do protocolo XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d215e-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d215e-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d215e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d215e-104">Versões anteriores do Lync Server e Office Communications Server forneciam um Gateway XMPP (Extensible Messaging and Presence Protocol) que pode ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP.</span><span class="sxs-lookup"><span data-stu-id="d215e-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="d215e-105">No Microsoft Lync Server 2013, a funcionalidade do XMPP pode ser implantada como um recurso.</span><span class="sxs-lookup"><span data-stu-id="d215e-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="d215e-106">A funcionalidade do XMPP está instalada em duas partes: um proxy do XMPP que é executado no servidor de borda e o gateway do XMPP que é executado nos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d215e-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="d215e-107">A implantação e a configuração do XMPP são abordadas na [implantação de acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) você planeja oferecer suporte a XMPP em sua organização definindo regras de porta e protocolo no firewall, configuração de certificados e adição de registros DNS.</span><span class="sxs-lookup"><span data-stu-id="d215e-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="d215e-108">Os seguintes tópicos nesta seção resumem as informações que você precisará para planejar com êxito a Federação do XMPP para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d215e-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d215e-109">O recurso XMPP do Lync Server 2013 é testado e suportado pela Microsoft para Federação de mensagens instantâneas com o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="d215e-109">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="d215e-110">Para qualquer outro sistema XMPP, entre em contato com o fornecedor terceirizado para verificar se eles suportam a Federação com o Lync Server 2013 e para qualquer recomendação de implantação ou solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="d215e-110">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d215e-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d215e-111">In This Section</span></span>

  - [<span data-ttu-id="d215e-112">Resumo de certificado-Federação de XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d215e-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="d215e-113">Resumo de porta-Federação XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d215e-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="d215e-114">Resumo de DNS-Federação do protocolo XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d215e-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d215e-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="d215e-115">See Also</span></span>


[<span data-ttu-id="d215e-116">Configurando a Federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d215e-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="d215e-117">Configurar políticas para controlar o acesso de usuário federado do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d215e-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="d215e-118">Gerenciar parceiros federados do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d215e-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="d215e-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d215e-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="d215e-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d215e-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="d215e-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d215e-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

