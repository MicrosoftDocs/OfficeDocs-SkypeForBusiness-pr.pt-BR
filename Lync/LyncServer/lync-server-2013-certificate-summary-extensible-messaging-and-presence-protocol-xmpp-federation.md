---
title: 'Lync Server 2013: Resumo de certificado-Federação de protocolo de presença e mensagens extensível (XMPP)'
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
ms.openlocfilehash: 7af2c226397c5225fc26f6dbdf40d12a4bdb1ca0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="de2bf-102">Resumo de certificados – Federação de protocolo de presença e mensagens extensíveis (XMPP) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de2bf-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de2bf-103">_**Tópico da última modificação:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="de2bf-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="de2bf-104">Os requisitos de certificado para habilitar e estabelecer comunicações com parceiros de protocolo de presença e mensagens extensível (XMPP) exigem o registro adicional de seus domínios do XMPP.</span><span class="sxs-lookup"><span data-stu-id="de2bf-104">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains.</span></span> <span data-ttu-id="de2bf-105">O registro incluído no certificado como um nome alternativo de assunto (SAN) será o domínio que pode participar de comunicações XMPP.</span><span class="sxs-lookup"><span data-stu-id="de2bf-105">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="de2bf-106">O domínio pode ser o domínio de nível raiz (por exemplo, contoso.com) se você quiser habilitar o XMPP para o seu domínio inteiro ou pode ser selecionado domínios filho (por exemplo, corp.contoso.com, finance.contoso.com) se você estiver habilitando XMPP para um subconjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="de2bf-106">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="de2bf-107">Resumo do certificado de mensagens extensíveis e protocolo de presença</span><span class="sxs-lookup"><span data-stu-id="de2bf-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de2bf-108">Componente</span><span class="sxs-lookup"><span data-stu-id="de2bf-108">Component</span></span></th>
<th><span data-ttu-id="de2bf-109">Nome do assunto</span><span class="sxs-lookup"><span data-stu-id="de2bf-109">Subject name</span></span></th>
<th><span data-ttu-id="de2bf-110">Nomes alternativos de assunto (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="de2bf-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="de2bf-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="de2bf-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de2bf-112">Atribuir ao serviço Edge para acessar o servidor de borda ou o pool de bordas</span><span class="sxs-lookup"><span data-stu-id="de2bf-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="de2bf-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2bf-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="de2bf-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2bf-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="de2bf-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2bf-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="de2bf-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="de2bf-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="de2bf-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="de2bf-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="de2bf-118">As três primeiras entradas de SAN são as entradas de SAN normais para um servidor de perímetro completo.</span><span class="sxs-lookup"><span data-stu-id="de2bf-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="de2bf-119">O contoso.com é a entrada necessária para federação com o parceiro XMPP no nível do domínio raiz.</span><span class="sxs-lookup"><span data-stu-id="de2bf-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="de2bf-120">Essa entrada permitirá que o XMPP para todos os domínios com o contoso.com sufixo seja re.</span><span class="sxs-lookup"><span data-stu-id="de2bf-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="de2bf-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="de2bf-121">See Also</span></span>


[<span data-ttu-id="de2bf-122">Exemplo de configuração de XMPP no Lync Server 2013 – federação XMPP com Google Talk</span><span class="sxs-lookup"><span data-stu-id="de2bf-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="de2bf-123">Planejar certificados do Servidor de Borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de2bf-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="de2bf-124">Configurar certificados de Borda para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de2bf-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="de2bf-125">Solicitação-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="de2bf-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="de2bf-126">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="de2bf-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

