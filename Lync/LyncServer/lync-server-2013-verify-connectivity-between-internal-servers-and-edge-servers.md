---
title: Verificar a conectividade entre servidores internos e servidores de borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8165781f9604b84f5b846ebda8679f9110262b88
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="c09d8-102">Verificar a conectividade entre servidores internos e servidores de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c09d8-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c09d8-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c09d8-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c09d8-104">No Lync Server 2013, um assistente de validação separado estava disponível para ajudar a validar a conectividade entre servidores de borda e servidores internos.</span><span class="sxs-lookup"><span data-stu-id="c09d8-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="c09d8-105">No Lync Server 2013 a validação da conectividade é feita automaticamente quando você instala seus servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="c09d8-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="c09d8-106">Você pode validar a replicação de informações de configuração para a borda executando o cmdlet **Get-CsManagementStoreReplicationStatus** do Windows PowerShell no computador interno no qual o repositório de gerenciamento central está localizado (ou qualquer computador ingressado no domínio em que o Lync Server 2013 Core Components (OcsCore. msi) está instalado.</span><span class="sxs-lookup"><span data-stu-id="c09d8-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="c09d8-107">Os resultados iniciais podem indicar o status como "Falso" e não "Verdadeiro" para replicação.</span><span class="sxs-lookup"><span data-stu-id="c09d8-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="c09d8-108">Se assim, execute o cmdlet **Invoke-CsManagementStoreReplication** e permita que o tempo necessário para a replicação seja concluído antes de executar o **Get-CsManagementStoreReplicationStatus** novamente.</span><span class="sxs-lookup"><span data-stu-id="c09d8-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="c09d8-109">É possível verificar a conectividade de usuário externo separadamente, inclusive o uso do Analisador de Conectividade Remota do Office Communications Server para verificar a conectividade de usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="c09d8-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="c09d8-110">Para obter detalhes, consulte [Verify Connectivity for External Users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span><span class="sxs-lookup"><span data-stu-id="c09d8-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

