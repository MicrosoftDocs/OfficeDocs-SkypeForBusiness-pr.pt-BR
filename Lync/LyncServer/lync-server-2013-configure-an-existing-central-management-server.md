---
title: 'Lync Server 2013: Configurar um Servidor de Gerenciamento Central existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec9193d8c40a26179c5dfe1f142740abdda8bc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="bb4ba-102">Configurar um Servidor de Gerenciamento Central existente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb4ba-102">Configure an existing Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb4ba-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bb4ba-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bb4ba-104">Se você reutilizar um servidor central de gerenciamento de uma implantação existente do Lync Server 2013, será necessário executar o procedimento descrito abaixo para garantir que o painel de controle do Lync Server e o Windows PowerShell funcionem corretamente.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-104">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="bb4ba-105">Para configurar um servidor de gerenciamento central existente</span><span class="sxs-lookup"><span data-stu-id="bb4ba-105">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="bb4ba-106">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bb4ba-107">Use o cmdlet **Update-CsAdminRole** para atualizar as funções de controle de acesso baseado em função (RBAC) armazenadas no servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-107">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bb4ba-108">Nenhuma saída é esperada, a menos que haja um erro.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-108">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

