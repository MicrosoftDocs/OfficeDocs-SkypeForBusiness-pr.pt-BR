---
title: Criar um novo filtro de URL para manipular hiperlinks em conversas de mensagens instantâneas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8f9a06dd80f87f2758269ddd2d468aeae2014d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="e8ad6-102">Criar um novo filtro de URL no Lync Server 2013 para manipular hiperlinks em conversas de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="e8ad6-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8ad6-103">_**Tópico da última modificação:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="e8ad6-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="e8ad6-104">Além de modificar o filtro de URL global, você pode configurar filtros de URL personalizados para sites individuais na implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8ad6-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="e8ad6-105">Para obter detalhes sobre a filtragem de URL, consulte Configurando [a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="e8ad6-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="e8ad6-106">Para criar um novo filtro de URL</span><span class="sxs-lookup"><span data-stu-id="e8ad6-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="e8ad6-107">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e8ad6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e8ad6-108">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8ad6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e8ad6-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e8ad6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e8ad6-110">Na barra de navegação à esquerda, clique em **mensagens instantâneas e presença**e, em seguida, clique em **filtro de URL**.</span><span class="sxs-lookup"><span data-stu-id="e8ad6-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="e8ad6-111">Na página **filtro de URL** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="e8ad6-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="e8ad6-112">Em **selecionar um site**, clique no site para o qual você deseja criar o filtro de URL e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8ad6-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="e8ad6-113">Na caixa de diálogo **novo filtro de URL** , marque a caixa de seleção **habilitar filtro de URL** para habilitar a filtragem de URL do site.</span><span class="sxs-lookup"><span data-stu-id="e8ad6-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="e8ad6-114">Para bloquear qualquer URL ativa que contenha um arquivo com uma extensão listada em **extensões de tipo de arquivo para bloquear** no **filtro de arquivo de edição**, marque a caixa de seleção **Bloquear URLs com extensão de arquivo** .</span><span class="sxs-lookup"><span data-stu-id="e8ad6-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="e8ad6-115">Na caixa de listagem suspensa **prefixo do hiperlink** , clique na opção que corresponde à maneira como você deseja manipular URLs nas conversas de mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="e8ad6-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="e8ad6-116">A caixa de **mensagem permitir** permite que uma mensagem de aviso seja enviada ao usuário ao enviar hiperlinks que podem ser enviados.</span><span class="sxs-lookup"><span data-stu-id="e8ad6-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="e8ad6-117">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e8ad6-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8ad6-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="e8ad6-118">See Also</span></span>


[<span data-ttu-id="e8ad6-119">Configurar a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8ad6-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="e8ad6-120">Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico</span><span class="sxs-lookup"><span data-stu-id="e8ad6-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="e8ad6-121">Modificar o filtro de transferência de arquivo padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8ad6-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="e8ad6-122">Modificar o filtro de URL padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8ad6-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

