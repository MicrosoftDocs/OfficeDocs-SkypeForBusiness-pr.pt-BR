---
title: Mover diretórios de conferência
description: Mover diretórios de conferência.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a91c30c0bedc84c684a096f5ea482fa911dc798
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549727"
---
# <a name="move-conference-directories"></a><span data-ttu-id="55bd6-103">Mover diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="55bd6-103">Move conference directories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55bd6-104">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="55bd6-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="55bd6-105">Antes de encerrar um pool, você precisa executar o procedimento a seguir para cada diretório de conferência no pool do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="55bd6-105">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="55bd6-106">Para mover um diretório de conferência para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55bd6-106">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="55bd6-107">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55bd6-107">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="55bd6-108">Para obter a identidade dos diretórios de conferência de sua organização, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="55bd6-108">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="55bd6-p101">Como este cmdlet retorna todos os diretórios de conferência da organização, convém limitar os resultados apenas ao pool que deseja encerrar. Por exemplo, caso deseje encerrar um pool com o FQDN (nome de domínio totalmente qualificado) pool01.contoso.net:</span><span class="sxs-lookup"><span data-stu-id="55bd6-p101">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission. For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="55bd6-111">Este cmdlet retorna todos os diretórios de conferência cujos IDs de serviço contêm o FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="55bd6-111">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="55bd6-112">Para mover diretórios de conferência, execute o seguinte comando para cada diretório de conferência no pool:</span><span class="sxs-lookup"><span data-stu-id="55bd6-112">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="55bd6-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="55bd6-113">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="55bd6-114">Você pode encontrar um erro, mostrado abaixo, que é causado pelo shell de gerenciamento do Lync Server que requer um conjunto atualizado de permissões do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55bd6-114">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="55bd6-115">Para resolver o erro, feche a janela atual e abra um novo Shell de gerenciamento do Lync Server e execute o comando novamente.</span><span class="sxs-lookup"><span data-stu-id="55bd6-115">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="55bd6-116">![Saída de erro move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory saída de erro")</span><span class="sxs-lookup"><span data-stu-id="55bd6-116">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

