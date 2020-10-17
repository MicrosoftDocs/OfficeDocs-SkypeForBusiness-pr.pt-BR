---
title: 'Lync Server 2013: Resumo de certificado-Federação de protocolo de presença e Unificação de mensagens (XMPP)'
description: 'Lync Server 2013: Resumo de certificado-Federação de protocolo de presença e Unificação de mensagens (XMPP).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e2bb593d909c2eec6032dc89c07cc5f5b1a72db
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572337"
---
# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="1eafe-103">Resumo de certificado-Federação de XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eafe-103">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eafe-104">_**Última modificação do tópico:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="1eafe-104">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="1eafe-p101">Os requisitos de certificado para ativar e estabelecer comunicações com mensagens extensíveis e parceiros de protocolo de presença (XMPP) requerem o registro adicional dos seus domínios XMPP. O registro incluído no certificado como um nome alternativo da entidade (SAN) será o domínio que pode participar das comunicações XMPP. O domínio pode ser o domínio no nível raiz (por exemplo, contoso.com) se você deseja habilitar XMPP para o domínio inteiro ou pode ser determinados domínios filho (por exemplo, corp.contoso.com, finance.contoso.com) se estiver habilitando XMPP para um subconjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="1eafe-p101">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains. The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications. The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="1eafe-108">Resumo do certificado para o protocolo Extensible Messaging and Presence</span><span class="sxs-lookup"><span data-stu-id="1eafe-108">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eafe-109">Componente</span><span class="sxs-lookup"><span data-stu-id="1eafe-109">Component</span></span></th>
<th><span data-ttu-id="1eafe-110">Nome da entidade</span><span class="sxs-lookup"><span data-stu-id="1eafe-110">Subject name</span></span></th>
<th><span data-ttu-id="1eafe-111">Nomes alternativos de entidade (SAN)/Ordem</span><span class="sxs-lookup"><span data-stu-id="1eafe-111">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="1eafe-112">Comments</span><span class="sxs-lookup"><span data-stu-id="1eafe-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eafe-113">Atribuir ao serviço de borda de acesso do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="1eafe-113">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="1eafe-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1eafe-114">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1eafe-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1eafe-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="1eafe-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1eafe-116">sip.contoso.com</span></span></p>
<p><span data-ttu-id="1eafe-117">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1eafe-117">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="1eafe-118">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1eafe-118">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1eafe-119">As três primeiras entradas de SAN são as entradas de SAN normais para um servidor de borda completo.</span><span class="sxs-lookup"><span data-stu-id="1eafe-119">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="1eafe-120">A contoso.com é a entrada exigida para federação com o parceiro XMPP no nível de domínio raiz.</span><span class="sxs-lookup"><span data-stu-id="1eafe-120">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="1eafe-121">Essa entrada permitirá que o XMPP todos os domínios com o sufixo contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1eafe-121">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1eafe-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="1eafe-122">See Also</span></span>


[<span data-ttu-id="1eafe-123">Exemplo de configuração de XMPP no Lync Server 2013 – Federação do XMPP com Google Talk</span><span class="sxs-lookup"><span data-stu-id="1eafe-123">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="1eafe-124">Planejar certificados de servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eafe-124">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="1eafe-125">Configurar certificados de borda para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eafe-125">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="1eafe-126">Request-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="1eafe-126">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="1eafe-127">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="1eafe-127">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

