---
title: 'Lync Server 2013: Editar ou configurar URLs simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b1439ddb0dafc63b0e70439ee5231477fdbb6be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="e8a99-102">Editar ou configurar URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8a99-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8a99-103">_**Tópico da última modificação:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="e8a99-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="e8a99-104">Esse procedimento não requer associação em um administrador local ou em um grupo de domínio privilegiado.</span><span class="sxs-lookup"><span data-stu-id="e8a99-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="e8a99-105">Você deve fazer logon em um computador como usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="e8a99-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="e8a99-106">O Lync Server 2013 usa URLs simples para direcionar chamadas internas e externas para serviços no servidor front-end ou no director, se um foi implantado.</span><span class="sxs-lookup"><span data-stu-id="e8a99-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="e8a99-107">Para obter mais informações sobre URLs simples, consulte [planejando URLs simples no Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="e8a99-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="e8a99-108">Você pode selecionar o formato de suas URLs simples a partir de várias opções.</span><span class="sxs-lookup"><span data-stu-id="e8a99-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="e8a99-109">Para obter detalhes sobre essas opções, consulte [requisitos de DNS para URLs simples no Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="e8a99-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="e8a99-110">Por padrão, as URLs simples serão configuradas na forma de (por exemplo, a URL simples de discagem) https://dialin.\<SIP : domínio\></span><span class="sxs-lookup"><span data-stu-id="e8a99-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="e8a99-111">Para configurar URLs simples</span><span class="sxs-lookup"><span data-stu-id="e8a99-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="e8a99-112">No construtor de topologias, clique com o botão direito do mouse no nó do **Lync Server** e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e8a99-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="e8a99-113">No painel **URLs Simples**, selecione **URLs de acesso telefônico:** (Discagem) ou **URLs de Reunião:** (Reunião) para editar. Em seguida, clique em **Editar URL**.</span><span class="sxs-lookup"><span data-stu-id="e8a99-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="e8a99-114">Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada.</span><span class="sxs-lookup"><span data-stu-id="e8a99-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="e8a99-115">O exemplo mostrado aqui modificou a URL de discagem para https://pool01.contoso.net/dialin.</span><span class="sxs-lookup"><span data-stu-id="e8a99-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="e8a99-116">Siga as mesmas etapas para editar a URL de Reunião, se necessário.</span><span class="sxs-lookup"><span data-stu-id="e8a99-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="e8a99-117">Para definir a URL simples Admin opcional</span><span class="sxs-lookup"><span data-stu-id="e8a99-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="e8a99-118">No construtor de topologias, clique com o botão direito do mouse no nó do **Lync Server** e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e8a99-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="e8a99-119">Na caixa **URL de acesso administrativo** , insira a URL simples que você deseja para ter acesso administrativo ao painel de controle do Lync Server 2013 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8a99-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e8a99-120">Nós recomendamos que você use a URL do administrador mais simples possível.</span><span class="sxs-lookup"><span data-stu-id="e8a99-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="e8a99-121">A opção mais simples é <STRONG> https://admin.</STRONG> &lt;domínio&gt;.</span><span class="sxs-lookup"><span data-stu-id="e8a99-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e8a99-122">Se alterar uma URL simples após a implantação inicial, você deve saber quais alterações afetam os registros de DNS e os certificados das URLs simples.</span><span class="sxs-lookup"><span data-stu-id="e8a99-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="e8a99-123">Se a alteração impactar a base de uma URL simples, você deve também alterar os registros DNS e certificados.</span><span class="sxs-lookup"><span data-stu-id="e8a99-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="e8a99-124">Por exemplo, mudar de https://lync.contoso.com/Meet para https://meet.contoso.com altera a URL base de Lync.contoso.com para Meet.contoso.com, portanto, você precisaria alterar os registros DNS e os certificados para se referirem ao Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e8a99-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="e8a99-125">Se você alterou a URL simples https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingspara, a URL base de Lync.contoso.com permanece a mesma, portanto, não é necessária nenhuma alteração de DNS ou certificado.</span><span class="sxs-lookup"><span data-stu-id="e8a99-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="e8a99-126">No entanto, sempre que você alterar um nome de URL simples, você deve executar o cmdlet <STRONG>Enable-CsComputer</STRONG> em cada director e servidor front-end para registrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="e8a99-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8a99-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="e8a99-127">See Also</span></span>


[<span data-ttu-id="e8a99-128">Planejamento de URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8a99-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

