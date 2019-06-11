---
title: 'Lync Server 2013: Configurando o convite para a reunião'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 014a42597e3df416d9e502eaaa90e2f1e71e35ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="5021b-102">Configurando o convite da reunião no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5021b-102">Configuring the meeting invitation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5021b-103">_**Tópico da última modificação:** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="5021b-103">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="5021b-104">Você pode personalizar convites de reunião enviados pelo suplemento de reunião online para o Lync 2013, incluindo os seguintes itens opcionais no corpo do convite da reunião:</span><span class="sxs-lookup"><span data-stu-id="5021b-104">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="5021b-105">**O logotipo da sua organização** Adicione o logotipo da sua organização aos convites para reunião usando a opção de URL do logotipo.</span><span class="sxs-lookup"><span data-stu-id="5021b-105">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="5021b-106">Se os convites para reuniões forem enviados para pessoas de fora da sua organização, a imagem deverá estar localizada em uma URL disponível publicamente.</span><span class="sxs-lookup"><span data-stu-id="5021b-106">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="5021b-107">Os formatos de imagem com suporte são GIF e JPG.</span><span class="sxs-lookup"><span data-stu-id="5021b-107">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="5021b-108">Embora o Lync Server 2013 armazene a URL sem restrições de tamanho na imagem, para obter os melhores resultados, o tamanho máximo da imagem deve ter 30 pixels de altura por 188 pixels de largura.</span><span class="sxs-lookup"><span data-stu-id="5021b-108">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="5021b-109">**Um link de ajuda ou suporte personalizado** Adicione uma URL para o site de ajuda ou de equipe de suporte da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5021b-109">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="5021b-110">Se os convites para reuniões forem enviados para pessoas de fora da sua organização, a URL deverá estar disponível publicamente.</span><span class="sxs-lookup"><span data-stu-id="5021b-110">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="5021b-111">O tamanho máximo da URL é 1 KB.</span><span class="sxs-lookup"><span data-stu-id="5021b-111">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="5021b-112">**Texto de isenção de responsabilidade legal** Adicione uma URL para o texto legal ou um aviso de isenção de responsabilidade que será exibido em todos os convites da reunião.</span><span class="sxs-lookup"><span data-stu-id="5021b-112">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="5021b-113">Se os convites para reuniões forem enviados para pessoas de fora da sua organização, a URL deverá estar disponível publicamente.</span><span class="sxs-lookup"><span data-stu-id="5021b-113">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="5021b-114">O tamanho máximo da URL é 1 KB.</span><span class="sxs-lookup"><span data-stu-id="5021b-114">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="5021b-115">**Texto do rodapé personalizado** Adicione o texto que será renderizado como um rodapé personalizado no convite.</span><span class="sxs-lookup"><span data-stu-id="5021b-115">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="5021b-116">O comprimento máximo do texto que pode ser adicionado é 2 KB.</span><span class="sxs-lookup"><span data-stu-id="5021b-116">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="5021b-117">Você pode configurar essas opções usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5021b-117">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="5021b-118">**Para personalizar o convite da reunião usando o painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="5021b-118">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="5021b-119">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5021b-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5021b-120">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5021b-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5021b-121">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5021b-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5021b-122">Na barra de navegação à esquerda, clique em **conferência** e em **configuração de reunião**.</span><span class="sxs-lookup"><span data-stu-id="5021b-122">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="5021b-123">Na página **Configuração de reunião**, clique em **Novo** e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5021b-123">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="5021b-p106">Para criar uma política a nível local, clique em **Configuração local**. No campo de pesquisa **Selecionar um local**, digite todo ou parte do nome do local para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de locais, clique no local desejado e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5021b-p106">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="5021b-p107">Para criar uma política a nível de pool, clique em **Configuração do pool**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço do pool para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de serviços, clique no pool desejado e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5021b-p107">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="5021b-130">Execute qualquer uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="5021b-130">Do any of the following:</span></span>
    
      - <span data-ttu-id="5021b-131">No campo **URL do logotipo** , digite a URL da imagem de logotipo da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5021b-131">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="5021b-132">No campo **URL da ajuda** , digite a URL do site de ajuda ou suporte da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5021b-132">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="5021b-133">No campo **texto legal** , digite a URL do texto legal ou da isenção de responsabilidade que você deseja incluir em convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="5021b-133">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="5021b-134">No campo **texto do rodapé personalizado** , digite o texto do rodapé, até 2 KB.</span><span class="sxs-lookup"><span data-stu-id="5021b-134">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="5021b-135">**Para personalizar o convite da reunião usando o Shell de gerenciamento do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="5021b-135">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="5021b-136">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5021b-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5021b-137">Execute o cmdlet **New-CsMeetingConfiguration** ou **set-CsMeetingConfiguration** para criar ou configurar as opções de convite da reunião.</span><span class="sxs-lookup"><span data-stu-id="5021b-137">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="5021b-138">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="5021b-138">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

