---
title: 'Lync Server 2013: requisitos do aplicativo Lync da Windows Store'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806fb7a71232492be7ef01474136817b7808111e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="0320a-102">Requisitos do aplicativo Lync da Windows Store para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0320a-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0320a-103">_**Tópico da última modificação:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="0320a-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="0320a-104">As organizações com uma implantação local do Lync Server devem atender aos seguintes requisitos para dar suporte ao aplicativo Lync da Windows Store.</span><span class="sxs-lookup"><span data-stu-id="0320a-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0320a-105">Para o Lync Server 2010, execute a atualização cumulativa para o Lync Server 2010: fevereiro de 2012 (disponível em <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>) ou posterior em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="0320a-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="0320a-106">Para permitir que os usuários ingressem em reuniões, execute a atualização cumulativa do Lync Server 2010: outubro de 2012 (disponível em <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>) nos servidores.</span><span class="sxs-lookup"><span data-stu-id="0320a-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="0320a-107">Habilite a descoberta automática, o Lync Web App e os serviços de tíquete da Web no servidor.</span><span class="sxs-lookup"><span data-stu-id="0320a-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="0320a-108">Habilite a autenticação de certificado no servidor front-end ou no pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="0320a-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="0320a-109">(O processo de registro do usuário no servidor front-end ou no pool de front-ends é geralmente chamado de registrador.) Para obter detalhes, consulte [criar configurações de registrador de configuração no Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0320a-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="0320a-110">Publicar os registros de recursos de alias de DNS (CNAME) do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="0320a-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="0320a-111">Não é mais necessário ter certeza de que o ponto de distribuição da lista de certificados revogados (CRL) dos certificados emitidos para o Lync Server aponta para um recurso HTTP em vez de um recurso LDAP.</span><span class="sxs-lookup"><span data-stu-id="0320a-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="0320a-112">No entanto, certifique-se de que os computadores cliente tenham as atualizações mais recentes do Windows instaladas.</span><span class="sxs-lookup"><span data-stu-id="0320a-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="0320a-113">Configurar proxies HTTP na empresa para permitir o tráfego HTTP relacionado ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0320a-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="0320a-114">Adicione exceções para a descoberta automática, Lync Web App e serviços webticket, se necessário.</span><span class="sxs-lookup"><span data-stu-id="0320a-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="0320a-115">Em clientes, instale o Windows 8,1 e a versão mais recente do aplicativo Lync da Windows Store para corrigir um problema de entrada que geralmente ocorre ao usar vários domínios (por exemplo, quando o URI SIP é **UserA@domainZ.com** , mas o servidor de borda é **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="0320a-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="0320a-116">Se a sua organização assinar o Lync Online ou o Office 365 e você estiver usando seu próprio nome de domínio, você deve realizar algumas etapas adicionais para configurar a rede para descoberta automática dos servidores do Lync.</span><span class="sxs-lookup"><span data-stu-id="0320a-116">If your organization subscribes to Lync Online or Office 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="0320a-117">Os requisitos de configuração de rede são iguais para o aplicativo Lync da Windows Store e Lync em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="0320a-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span> <span data-ttu-id="0320a-118">Siga as instruções "configurar sua rede" no artigo do wiki do Office 365 "configurar dispositivos móveis do Lync", disponível em [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span><span class="sxs-lookup"><span data-stu-id="0320a-118">Follow the instructions “Set up your network” in the Office 365 wiki article “Set up Lync mobile devices,” available at [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0320a-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="0320a-119">See Also</span></span>


[<span data-ttu-id="0320a-120">Implantando o aplicativo Lync da Windows Store no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0320a-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

