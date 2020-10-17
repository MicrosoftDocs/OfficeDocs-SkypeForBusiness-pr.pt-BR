---
title: 'Lync Server 2013: modificar o filtro de transferência de arquivo padrão'
description: 'Lync Server 2013: modificar o filtro de transferência de arquivo padrão.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8091dfebea87b793c56b9a670cfeeeab15ce6c44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566927"
---
# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="d2058-103">Modificar o filtro de transferência de arquivo padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2058-103">Modify the default file transfer filter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2058-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d2058-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d2058-105">O Lync Server 2013 fornece um filtro de transferência de arquivo global que bloqueia tipos específicos de arquivos durante as seguintes atividades relacionadas a arquivos em sua implantação do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="d2058-105">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="d2058-106">Solicitações de transferência de arquivo durante conversas de mensagens instantâneas (IM)</span><span class="sxs-lookup"><span data-stu-id="d2058-106">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="d2058-107">Carregamentos de arquivo e downloads durante o uso do recurso do folheto do cliente do Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="d2058-107">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="d2058-108">Reprodução de multimídia durante conferências</span><span class="sxs-lookup"><span data-stu-id="d2058-108">Multimedia playback during conferences</span></span>

<span data-ttu-id="d2058-109">Dependendo dos tipos de arquivos que você deseja bloquear ou permitir, você pode usar o painel de controle do Lync Server para modificar o filtro global.</span><span class="sxs-lookup"><span data-stu-id="d2058-109">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="d2058-110">Para obter detalhes sobre a filtragem de transferência de arquivo, consulte [Configuring File Transfer and URL Filter for im (mensagens instantâneas) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="d2058-110">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="d2058-111">Para modificar o filtro de transferência de arquivo padrão</span><span class="sxs-lookup"><span data-stu-id="d2058-111">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="d2058-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d2058-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d2058-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2058-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d2058-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d2058-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d2058-115">Na barra de navegação esquerda, clique em **IM e Presença** e em **Filtro de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="d2058-115">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="d2058-116">Na página **Filtro de Arquivo**, clique duas vezes no filtro **Global**.</span><span class="sxs-lookup"><span data-stu-id="d2058-116">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="d2058-117">Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Habilitar filtro de arquivo**.</span><span class="sxs-lookup"><span data-stu-id="d2058-117">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="d2058-118">Na caixa de listagem suspensa **Transferência de arquivos**, clique em **Bloquear tudo** ou em **Bloquear tipos de arquivo específicos**.</span><span class="sxs-lookup"><span data-stu-id="d2058-118">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="d2058-119">Se você clicou em **Bloquear Tudo**, pule para a etapa 9.</span><span class="sxs-lookup"><span data-stu-id="d2058-119">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="d2058-120">Se você clicou em **Bloquear tipos de arquivos específicos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d2058-120">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="d2058-121">Clique em **Selecionar** para modificar a lista padrão de extensões do tipo de arquivo que você deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="d2058-121">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="d2058-122">Em **Selecionar Tipo de Arquivo**, selecione os tipos de arquivo que você deseja bloquear ou permitir adicionando ou removendo suas extensões das categorias em **Extensões do tipo de arquivo**.</span><span class="sxs-lookup"><span data-stu-id="d2058-122">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="d2058-123">Se você não ver a extensão para um tipo de arquivo que deseja bloquear, digite a extensão na caixa de texto em **Adicionar extensões do tipo de arquivo à lista** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d2058-123">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="d2058-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2058-124">Click **OK**.</span></span>

9.  <span data-ttu-id="d2058-125">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d2058-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2058-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="d2058-126">See Also</span></span>


[<span data-ttu-id="d2058-127">Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2058-127">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="d2058-128">Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico</span><span class="sxs-lookup"><span data-stu-id="d2058-128">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="d2058-129">Criar um novo filtro de URL no Lync Server 2013 para lidar com hiperlinks em conversas de IM</span><span class="sxs-lookup"><span data-stu-id="d2058-129">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="d2058-130">Modificar o filtro de URL padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2058-130">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

