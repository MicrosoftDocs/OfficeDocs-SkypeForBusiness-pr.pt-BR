---
title: 'Lync Server 2013: editar ou configurar URLs simples'
description: 'Lync Server 2013: editar ou configurar URLs simples.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9152a65083f71510f4cdb1189b3982afdd68b4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551627"
---
# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="7a7fa-103">Editar ou configurar URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a7fa-103">Edit or configure simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a7fa-104">_**Última modificação do tópico:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="7a7fa-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="7a7fa-p101">Este procedimento não exige associação a um grupo de administradores locais ou de domínio privilegiado. Você deve fazer logon em um computador como usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="7a7fa-107">O Lync Server 2013 usa URLs simples para direcionar chamadas internas e externas para serviços no servidor de front-end ou no diretor, se um tiver sido implantado.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-107">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="7a7fa-108">Para obter mais informações sobre URLs simples, consulte [Planning for Simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-108">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="7a7fa-109">Você pode selecionar o formato para suas URLs simples a partir de várias opções.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-109">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="7a7fa-110">Para obter detalhes sobre essas opções, consulte [DNS Requirements for Simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-110">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="7a7fa-111">Por padrão, as URLs simples serão configuradas no formato (por exemplo, a URL simples de discagem): https://dialin .\<SIP Domain\></span><span class="sxs-lookup"><span data-stu-id="7a7fa-111">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="7a7fa-112">Para configurar URLs simples</span><span class="sxs-lookup"><span data-stu-id="7a7fa-112">To configure simple URLs</span></span>

1.  <span data-ttu-id="7a7fa-113">No construtor de topologias, clique com o botão direito do mouse no nó **Lync Server** e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-113">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="7a7fa-114">No painel **URLs simples** , selecione URLs de **acesso de telefone:** (discagem) ou **URLs de reunião:** (atender) para editar e clique em **Editar URL**.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-114">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="7a7fa-115">Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-115">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="7a7fa-116">O exemplo mostrado aqui modificou a URL de discagem para https://pool01.contoso.net/dialin .</span><span class="sxs-lookup"><span data-stu-id="7a7fa-116">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="7a7fa-117">Edite a URL de Reunião usando as mesmas etapas, se necessário.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-117">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="7a7fa-118">Para definir a URL simples Admin opcional</span><span class="sxs-lookup"><span data-stu-id="7a7fa-118">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="7a7fa-119">No construtor de topologias, clique com o botão direito do mouse no nó **Lync Server** e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-119">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="7a7fa-120">Na caixa **URL de acesso administrativo** , digite a URL simples que você deseja para acesso administrativo ao painel de controle do Lync Server 2013 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-120">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7a7fa-121">Recomendamos usar a URL mais simples possível para a URL Admin.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-121">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="7a7fa-122">A opção mais simples é <STRONG> https://admin .</STRONG> &lt; domínio &gt; .</span><span class="sxs-lookup"><span data-stu-id="7a7fa-122">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7a7fa-123">Se você alterar uma URL simples após a implantação inicial, esteja ciente das alterações que afetam seus registros de DNS (Sistema de Nome de Domínio) e certificados para URLs simples.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-123">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="7a7fa-124">Se a alteração impactar a base de uma URL simples, você deverá alterar os registros DNS e certificados também.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-124">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="7a7fa-125">Por exemplo, alterar de https://lync.contoso.com/Meet para https://meet.contoso.com altera a URL base de lync.contoso.com para Meet.contoso.com, portanto, você precisaria alterar os registros DNS e os certificados para fazer referência ao Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-125">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="7a7fa-126">Se você alterou a URL simples de https://lync.contoso.com/Meet para https://lync.contoso.com/Meetings , a URL base do Lync.contoso.com permanecerá a mesma, portanto, não serão necessárias alterações de DNS ou de certificado.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-126">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="7a7fa-127">No entanto, sempre que você alterar um nome de URL simples, deverá executar o cmdlet <STRONG>Enable-CsComputer</STRONG> em cada diretor e servidor front-end para registrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="7a7fa-127">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a7fa-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="7a7fa-128">See Also</span></span>


[<span data-ttu-id="7a7fa-129">Planejamento de URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a7fa-129">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

