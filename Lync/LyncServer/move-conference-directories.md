---
title: Mover diretórios de conferências
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ae7633d638571410c93cfefe87d9e333731a4bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="7226a-102">Mover diretórios de conferências</span><span class="sxs-lookup"><span data-stu-id="7226a-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7226a-103">_**Tópico da última modificação:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="7226a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="7226a-104">Antes de encerrar um pool, você precisa executar o procedimento a seguir para cada diretório de conferência no pool do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7226a-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="7226a-105">Para mover um diretório de conferências para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7226a-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="7226a-106">Abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7226a-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="7226a-107">Para obter a identidade dos diretórios de conferências em sua organização, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="7226a-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="7226a-108">Como esse cmdlet retorna todos os diretórios de conferência em sua organização, talvez você queira limitar os resultados apenas ao pool que deseja encerrar.</span><span class="sxs-lookup"><span data-stu-id="7226a-108">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span></span> <span data-ttu-id="7226a-109">Por exemplo, se você quiser encerrar um pool com o nome de domínio totalmente qualificado (FQDN) pool01.contoso.net:</span><span class="sxs-lookup"><span data-stu-id="7226a-109">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="7226a-110">Esse cmdlet retorna todos os diretórios de conferência em que a ID de serviço contém a pool01.contoso.net FQDN.</span><span class="sxs-lookup"><span data-stu-id="7226a-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="7226a-111">Para mover diretórios de conferência, execute o seguinte procedimento para cada diretório de conferências no pool:</span><span class="sxs-lookup"><span data-stu-id="7226a-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="7226a-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7226a-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="7226a-113">Você pode observar um erro, mostrado abaixo, que é causado pelo shell de gerenciamento do Lync Server que exige um conjunto atualizado de permissões do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7226a-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="7226a-114">Para resolver o erro, feche a janela atual e abra um novo Shell de gerenciamento do Lync Server e execute o comando novamente.</span><span class="sxs-lookup"><span data-stu-id="7226a-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="7226a-115">![Saída de erro move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Saída de erro move-CsConferenceDirectory")</span><span class="sxs-lookup"><span data-stu-id="7226a-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

