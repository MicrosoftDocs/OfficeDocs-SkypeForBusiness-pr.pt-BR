---
title: 'Lync Server 2013: configurar Federação para um provedor de conferência de áudio'
description: 'Lync Server 2013: configurar Federação para um provedor de conferência de áudio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c74654224c42618768d881a95031d58be4d55df5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553317"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="22a5b-103">Configurar Federação para um provedor de conferência de áudio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22a5b-103">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22a5b-104">_**Última modificação do tópico:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="22a5b-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="22a5b-105">Se você quiser usar um provedor de serviços de audioconferência (ACP) em sua implantação híbrida (Lync Server local com Lync Online), você precisará configurar a Federação entre sua implantação do Lync local e o parceiro ACP como um servidor parceiro permitido.</span><span class="sxs-lookup"><span data-stu-id="22a5b-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="22a5b-106">Você pode configurar a Federação adicionando o domínio de parceiro ACP e o servidor de borda (isso também pode ser chamado de proxy de acesso) à lista de domínios federados para sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="22a5b-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="22a5b-107">O parceiro ACP precisará adicionar o FQDN do pool de servidores de borda local à lista de domínios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="22a5b-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="22a5b-108">Entre em contato com seu provedor de ACP para obter o parceiro detailsYour ACP adicional, é necessário adicionar o FQDN do pool de servidores de borda local à lista de domínios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="22a5b-108">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="22a5b-109">**Adicionar o domínio ACP e o servidor de borda como um domínio federado permitido**</span><span class="sxs-lookup"><span data-stu-id="22a5b-109">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="22a5b-110">Para adicionar o domínio ACP como um servidor parceiro permitido (domínio federado permitido), siga as etapas em [Configurar suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="22a5b-110">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="22a5b-111">Para o servidor de borda, adicione o FQDN do servidor de borda do parceiro ACP.</span><span class="sxs-lookup"><span data-stu-id="22a5b-111">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="22a5b-112">Talvez seja necessário entrar em contato com seu parceiro ACP para obter o FQDN do servidor de borda, que também pode ser mencionado pelo ACP como proxy de acesso.</span><span class="sxs-lookup"><span data-stu-id="22a5b-112">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="22a5b-113">**Forneça o FQDN do seu pool do servidor de borda ao parceiro ACP**</span><span class="sxs-lookup"><span data-stu-id="22a5b-113">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="22a5b-114">O parceiro ACP precisa configurar a Federação para adicionar seu domínio local como um servidor parceiro permitido adicionando o FQDN do seu pool de servidor de borda como um domínio federado permitido.</span><span class="sxs-lookup"><span data-stu-id="22a5b-114">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

