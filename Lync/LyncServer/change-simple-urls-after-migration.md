---
title: Alterar URLs simples após a migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df0d6666f4ea824d59a97eb1f63b66016c75d547
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42003416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="ed468-102">Alterar URLs simples após a migração</span><span class="sxs-lookup"><span data-stu-id="ed468-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed468-103">_**Última modificação do tópico:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="ed468-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="ed468-104">O Lync Server oferece suporte a três URLs simples:</span><span class="sxs-lookup"><span data-stu-id="ed468-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="ed468-105">**Reunir** é usado como URL base para todas as conferências no site ou na organização.</span><span class="sxs-lookup"><span data-stu-id="ed468-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="ed468-106">Com o URL Reunir simples, os links para ingressar em reuniões são fáceis de compreender, de comunicar e distribuir.</span><span class="sxs-lookup"><span data-stu-id="ed468-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="ed468-107">**Discar** possibilita o acesso à página da web Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="ed468-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="ed468-108">O URL Discar é incluído em todos os convites de reuniões para que o usuário que desejar discar para ingressar na reunião possa obter acesso ao número de telefone necessário, bem como as informações do PIN.</span><span class="sxs-lookup"><span data-stu-id="ed468-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="ed468-109">O **administrador** permite acesso rápido ao painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed468-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="ed468-110">A URL simples de Admin é interna à organização.</span><span class="sxs-lookup"><span data-stu-id="ed468-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="ed468-111">Após a migração para o Lync Server 2013, você deve estar ciente de como a alteração impacta seus registros DNS e certificados para URLs simples.</span><span class="sxs-lookup"><span data-stu-id="ed468-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="ed468-112">Se o diretor herdado do Lync Server 2010 permanecer em uso na topologia, não será necessário fazer alterações nas suas URLs simples.</span><span class="sxs-lookup"><span data-stu-id="ed468-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="ed468-113">Se o diretor do Lync Server 2010 for removido da topologia após a migração, os registros DNS de URL simples devem ser atualizados para apontar para um dos pools do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed468-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="ed468-114">Contudo, sempre que você alterar o nome de um URL simples, você deve executar o Enable-CsComputer em cada servidor Diretor e Front End para registrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="ed468-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="ed468-115">Alterando URLs simples após a migração</span><span class="sxs-lookup"><span data-stu-id="ed468-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="ed468-116">**Para atualizar a URL simples de reunião**</span><span class="sxs-lookup"><span data-stu-id="ed468-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="ed468-117">No construtor de topologias, clique com o botão direito do mouse no nó superior **Lync Server**e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ed468-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="ed468-118">Selecione **URLs simples** no painel esquerdo e, abaixo das **URLs da reunião:** selecione a URL de reunião e clique em **Editar URL**.</span><span class="sxs-lookup"><span data-stu-id="ed468-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="ed468-119">Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada.</span><span class="sxs-lookup"><span data-stu-id="ed468-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="ed468-120">**Para atualizar a URL simples de administrador**</span><span class="sxs-lookup"><span data-stu-id="ed468-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="ed468-121">No construtor de topologias, clique com o botão direito do mouse no nó superior **Lync Server**e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ed468-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="ed468-122">Selecione **URLs simples** no painel esquerdo e, em seguida, abaixo da caixa **URL de acesso administrativo** , digite a URL simples que você deseja para acesso administrativo ao Lync Server 2013 painel de controle e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed468-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ed468-123">Recomendamos usar a URL mais simples possível para a URL Admin.</span><span class="sxs-lookup"><span data-stu-id="ed468-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="ed468-124">A opção mais simples é <STRONG> https://admin.</STRONG> &lt;domínio&gt;.</span><span class="sxs-lookup"><span data-stu-id="ed468-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed468-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="ed468-125">See Also</span></span>


[<span data-ttu-id="ed468-126">Planejamento de URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed468-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

