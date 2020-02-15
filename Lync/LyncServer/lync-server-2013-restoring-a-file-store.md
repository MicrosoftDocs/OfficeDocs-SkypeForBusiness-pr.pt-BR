---
title: 'Lync Server 2013: restaurar um repositório de arquivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60c4a3e1563890d64394f3a99141523cb95add38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="38787-102">Restaurando um repositório de arquivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38787-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38787-103">_**Última modificação do tópico:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="38787-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="38787-104">Os repositórios de arquivos do Standard Edition geralmente estão localizados no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="38787-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="38787-105">Os Repositórios de Arquivo para o Enterprise Edition estão normalmente localizados em um cluster ou servidor de arquivos.</span><span class="sxs-lookup"><span data-stu-id="38787-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="38787-106">O procedimento a seguir descreve como restaurar um repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="38787-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="38787-107">Para restaurar um Re positório de arquivo</span><span class="sxs-lookup"><span data-stu-id="38787-107">To restore a File Store</span></span>

1.  <span data-ttu-id="38787-108">Se um repositório de arquivos falhar, copie o repositório de arquivos apropriado\\ de $backup para o local do repositório de arquivos no servidor de arquivos ou no servidor Standard Edition e, em seguida, compartilhe a pasta.</span><span class="sxs-lookup"><span data-stu-id="38787-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38787-109">O caminho e o nome de arquivo do repositório de arquivos restaurados devem ser exatamente os mesmos do repositório de arquivos de backup, para que os componentes que usam os arquivos possam acessá-los.</span><span class="sxs-lookup"><span data-stu-id="38787-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="38787-110">Se necessário, defina as listas de controle de acesso (ACLs) para o repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="38787-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="38787-111">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="38787-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38787-112">Você só precisará executar esta etapa se não tiver executado o construtor de topologias durante o processo de restauração.</span><span class="sxs-lookup"><span data-stu-id="38787-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

