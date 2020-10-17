---
title: Criar um novo filtro de URL para lidar com hiperlinks em conversas de mensagens instantâneas
description: Criar um novo filtro de URL para lidar com hiperlinks em conversas de IM.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e583b3e8cbd04279ab7f54b4138a349fa0d1e85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554657"
---
# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="e02ad-103">Criar um novo filtro de URL no Lync Server 2013 para lidar com hiperlinks em conversas de IM</span><span class="sxs-lookup"><span data-stu-id="e02ad-103">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e02ad-104">_**Última modificação do tópico:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="e02ad-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="e02ad-105">Além de modificar o filtro de URL global, você pode configurar filtros de URL personalizados para sites individuais em sua implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e02ad-105">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="e02ad-106">Para obter detalhes sobre a filtragem de URL, consulte [Configurando a transferência de arquivos e filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="e02ad-106">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="e02ad-107">Para criar um novo filtro de URL</span><span class="sxs-lookup"><span data-stu-id="e02ad-107">To create a new URL filter</span></span>

1.  <span data-ttu-id="e02ad-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e02ad-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e02ad-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e02ad-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e02ad-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e02ad-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e02ad-111">Na barra de navegação esquerda, clique em **IM e Presença** e clique em **Filtro de URL**.</span><span class="sxs-lookup"><span data-stu-id="e02ad-111">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="e02ad-112">Na página **Filtro de URL**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e02ad-112">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="e02ad-113">Em **Selecionar um Site**, clique no site para o qual você deseja criar o filtro de URL e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e02ad-113">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="e02ad-114">Na caixa de diálogo **Novo Filtro de URL**, marque a caixa de seleção **Habilitar Filtro de URL** para habilitar a filtragem de URL para o site.</span><span class="sxs-lookup"><span data-stu-id="e02ad-114">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="e02ad-115">Para bloquear qualquer URL ativa que contenha um arquivo com uma extensão listada sob **Extensões de tipos de arquivos a serem bloqueadas** em **Editar Filtro de Arquivo**, marque a caixa de seleção **Bloquear URLs com extensão de arquivo**.</span><span class="sxs-lookup"><span data-stu-id="e02ad-115">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="e02ad-116">Na caixa de listagem suspensa **Prefixo de hiperlink**, clique na opção que corresponde à forma como você deseja lidar com URLs em conversas de mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="e02ad-116">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="e02ad-117">A caixa **Permitir mensagem** permite que uma mensagem de aviso seja enviada ao usuário ao enviar hiperlinks que têm permissão para serem enviados.</span><span class="sxs-lookup"><span data-stu-id="e02ad-117">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="e02ad-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e02ad-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e02ad-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="e02ad-119">See Also</span></span>


[<span data-ttu-id="e02ad-120">Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e02ad-120">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="e02ad-121">Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico</span><span class="sxs-lookup"><span data-stu-id="e02ad-121">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="e02ad-122">Modificar o filtro de transferência de arquivo padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e02ad-122">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="e02ad-123">Modificar o filtro de URL padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e02ad-123">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

