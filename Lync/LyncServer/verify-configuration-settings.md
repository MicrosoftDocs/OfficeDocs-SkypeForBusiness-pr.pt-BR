---
title: Verifique as configurações
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bfc01e5b14738592647c379a1e2f9e62f808bf3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="537bc-102">Verifique as configurações</span><span class="sxs-lookup"><span data-stu-id="537bc-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="537bc-103">_**Última modificação do tópico:** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="537bc-103">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="537bc-104">Você pode validar a replicação de informações de configuração para o servidor de borda executando o cmdlet do Lync Server 2013 **Get-CsManagementStoreReplicationStatus** no computador interno no qual o repositório de gerenciamento central está localizado, ou em qualquer computador ingressado no domínio no qual o Lync Server 2013 Core Components (OcsCore. msi) está instalado.</span><span class="sxs-lookup"><span data-stu-id="537bc-104">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="537bc-105">Os resultados iniciais podem indicar o status como "Falso" e não "Verdadeiro" para replicação.</span><span class="sxs-lookup"><span data-stu-id="537bc-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="537bc-106">Se isso acontecer, execute o cmdlet **Invoke-CsManagementStoreReplication** e dê tempo para a replicação ser concluída antes de executar o **Get-CsManagementStoreReplicationStatus** novamente.</span><span class="sxs-lookup"><span data-stu-id="537bc-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

