---
title: 'Lync Server 2013: configurar armazenamento de arquivo DFS'
description: 'Lync Server 2013: configurar armazenamento de arquivo DFS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70ae93db188ec51d04dd33d6c3cb5659db5a2c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564377"
---
# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="2bd07-103">Configurar o armazenamento de arquivos do DFS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bd07-103">Configure DFS file storage for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bd07-104">_**Última modificação do tópico:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="2bd07-104">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="2bd07-105">O Lync Server 2013 suporta o uso de compartilhamentos de arquivos em um sistema de arquivos distribuído (DFS).</span><span class="sxs-lookup"><span data-stu-id="2bd07-105">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="2bd07-106">Para obter detalhes sobre o DFS para Windows Server 2008, consulte o guia passo a passo do DFS para o Windows Server 2008 em [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) . Para usar um DFS, o Lync Server 2013 requer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2bd07-106">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="2bd07-107">Namespaces sejam baseados em domínio</span><span class="sxs-lookup"><span data-stu-id="2bd07-107">Namespaces are domain based</span></span>

  - <span data-ttu-id="2bd07-108">Todos os servidores de namespace estejam executando um mínimo de Windows 2008</span><span class="sxs-lookup"><span data-stu-id="2bd07-108">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="2bd07-109">Lync Server 2013 a instalação requer que as permissões em uma pasta compartilhada permitam acesso total ao administrador.</span><span class="sxs-lookup"><span data-stu-id="2bd07-109">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="2bd07-110">O Lync Server 2013 usará as permissões de arquivo NTFS para ACL nas pastas.</span><span class="sxs-lookup"><span data-stu-id="2bd07-110">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="2bd07-111">Permissões de compartilhamento DFS herdadas não serão usadas para acesso restrito.</span><span class="sxs-lookup"><span data-stu-id="2bd07-111">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="2bd07-112">Para obter mais detalhes sobre os requisitos de compartilhamento de arquivos, consulte [File Storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="2bd07-112">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2bd07-113">Você pode estar procurando informações sobre como configurar um compartilhamento não DFS.</span><span class="sxs-lookup"><span data-stu-id="2bd07-113">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="2bd07-114">Em caso afirmativo, confira <A href="lync-server-2013-hardware-setup.md">configuração de hardware para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2bd07-114">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2bd07-115">O procedimento a seguir descreve como configurar corretamente permissões de pastas compartilhas usando o Assistente de Namespace DFS (como descrito no guia de instalação do DFS)</span><span class="sxs-lookup"><span data-stu-id="2bd07-115">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="2bd07-116">Para configurar permissões de pastas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="2bd07-116">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="2bd07-117">clique em **Iniciar**, aponte para **Todos os Programas**, aponte para **Ferramentas Administrativas** e clique em **Gerenciamento DFS**.</span><span class="sxs-lookup"><span data-stu-id="2bd07-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="2bd07-118">Na árvore de console do snap-in do Gerenciamento DFS, clique com o botão direito no servidor de namespace (por exemplo, filesrv1.contoso.com) e depois clique em **Editar Configurações**.</span><span class="sxs-lookup"><span data-stu-id="2bd07-118">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="2bd07-119">Selecione **Permissões de pastas compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="2bd07-119">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="2bd07-120">Selecione **Usar permissões personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="2bd07-120">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="2bd07-121">Para o grupo Administrador, selecione o seguinte sob **Permitir**:</span><span class="sxs-lookup"><span data-stu-id="2bd07-121">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="2bd07-122">**Controle total**</span><span class="sxs-lookup"><span data-stu-id="2bd07-122">**Full Control**</span></span>
    
      - <span data-ttu-id="2bd07-123">**Alteração**</span><span class="sxs-lookup"><span data-stu-id="2bd07-123">**Change**</span></span>
    
      - <span data-ttu-id="2bd07-124">**Leitura**</span><span class="sxs-lookup"><span data-stu-id="2bd07-124">**Read**</span></span>

6.  <span data-ttu-id="2bd07-125">Clique em **Aplicar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bd07-125">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

