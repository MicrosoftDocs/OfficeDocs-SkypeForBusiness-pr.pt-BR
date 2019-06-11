---
title: 'Lync Server 2013: modificar o filtro padrão de transferência de arquivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="35bf2-102">Modificar o filtro de transferência de arquivo padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35bf2-102">Modify the default file transfer filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35bf2-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="35bf2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="35bf2-104">O Lync Server 2013 fornece um filtro de transferência de arquivo global que bloqueia tipos específicos de arquivos durante as seguintes atividades relacionadas a arquivos em sua implantação do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="35bf2-104">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="35bf2-105">Solicitações de transferência de arquivos durante as conversas de mensagens instantâneas (IM)</span><span class="sxs-lookup"><span data-stu-id="35bf2-105">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="35bf2-106">Uploads e downloads de arquivos durante o uso do recurso folheto no cliente do Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="35bf2-106">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="35bf2-107">Reprodução de multimídia durante conferências</span><span class="sxs-lookup"><span data-stu-id="35bf2-107">Multimedia playback during conferences</span></span>

<span data-ttu-id="35bf2-108">Dependendo dos tipos de arquivos que você deseja bloquear ou permitir, você pode usar o painel de controle do Lync Server para modificar o filtro global.</span><span class="sxs-lookup"><span data-stu-id="35bf2-108">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="35bf2-109">Para obter detalhes sobre a filtragem de transferência de arquivo, consulte Configurando [a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="35bf2-109">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="35bf2-110">Para modificar o filtro de transferência de arquivo padrão</span><span class="sxs-lookup"><span data-stu-id="35bf2-110">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="35bf2-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="35bf2-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="35bf2-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35bf2-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="35bf2-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="35bf2-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="35bf2-114">Na barra de navegação à esquerda, clique em **mensagens instantâneas e presença** e, em seguida, clique em **filtro de arquivo**.</span><span class="sxs-lookup"><span data-stu-id="35bf2-114">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="35bf2-115">Na página **filtro de arquivo** , clique duas vezes no filtro **global** .</span><span class="sxs-lookup"><span data-stu-id="35bf2-115">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="35bf2-116">Em **Editar Filtro de arquivo**, marque a caixa de seleção **habilitar filtro de arquivo** .</span><span class="sxs-lookup"><span data-stu-id="35bf2-116">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="35bf2-117">Na caixa de listagem suspensa **transferência de arquivo** , clique em **bloquear todos** ou **bloquear tipos de arquivo específicos**.</span><span class="sxs-lookup"><span data-stu-id="35bf2-117">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="35bf2-118">Se você clicou em **bloquear tudo**, pule para a etapa 9.</span><span class="sxs-lookup"><span data-stu-id="35bf2-118">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="35bf2-119">Se você clicou em **bloquear tipos de arquivo específicos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="35bf2-119">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="35bf2-120">Clique em **selecionar** para modificar a lista padrão de extensões de tipo de arquivo que você deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="35bf2-120">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="35bf2-121">Em **Selecionar tipo de arquivo**, selecione os tipos de arquivo que você deseja bloquear ou permitir, adicionando ou removendo suas extensões das categorias em **extensões de tipo de arquivo**.</span><span class="sxs-lookup"><span data-stu-id="35bf2-121">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="35bf2-122">Se você não vir a extensão para um tipo de arquivo que deseja bloquear, digite a extensão na caixa de texto em **adicionar extensões de tipo de arquivo à lista**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="35bf2-122">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="35bf2-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="35bf2-123">Click **OK**.</span></span>

9.  <span data-ttu-id="35bf2-124">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="35bf2-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35bf2-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="35bf2-125">See Also</span></span>


[<span data-ttu-id="35bf2-126">Configurar a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35bf2-126">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="35bf2-127">Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico</span><span class="sxs-lookup"><span data-stu-id="35bf2-127">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="35bf2-128">Criar um novo filtro de URL no Lync Server 2013 para manipular hiperlinks em conversas de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="35bf2-128">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="35bf2-129">Modificar o filtro de URL padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35bf2-129">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

