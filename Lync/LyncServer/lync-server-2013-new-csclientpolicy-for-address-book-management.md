---
title: 'Lync Server 2013: New-CsClientPolicy para gerenciamento de catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f68f6cfa2fde4d1e5a2bc58a36478a60060dd5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="d41e1-102">New-CsClientPolicy para o gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d41e1-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d41e1-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d41e1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d41e1-104">Quem pode executar este cmdlet: por padrão, os membros dos grupos a seguir estão autorizados a executar o cmdlet New-CsClientPolicy: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d41e1-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="d41e1-105">Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d41e1-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="d41e1-106">O cmdlet New-CsClientPolicy define um grande número de configurações para configurar clientes para os recursos que estão disponíveis no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d41e1-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="d41e1-107">Para o serviço de catálogo de endereços, o parâmetro AddressBookAvailability é de interesse.</span><span class="sxs-lookup"><span data-stu-id="d41e1-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="d41e1-108">Esse parâmetro, que afeta diretamente as opções disponíveis para os clientes, tem três opções possíveis:</span><span class="sxs-lookup"><span data-stu-id="d41e1-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="d41e1-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="d41e1-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="d41e1-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="d41e1-110">WebSearchOnly</span></span>

  - <span data-ttu-id="d41e1-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="d41e1-111">FileDownloadOnly</span></span>

<span data-ttu-id="d41e1-112">Quando definido, ele determina como o catálogo de endereços é acessado por clientes.</span><span class="sxs-lookup"><span data-stu-id="d41e1-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="d41e1-113">Se você definir esse parâmetro, deverá definir uma das opções.</span><span class="sxs-lookup"><span data-stu-id="d41e1-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="d41e1-114">Se você não modificar essa configuração, o WebSearchAndFileDownload padrão permanecerá em vigor.</span><span class="sxs-lookup"><span data-stu-id="d41e1-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="d41e1-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d41e1-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="d41e1-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="d41e1-116">See Also</span></span>


[<span data-ttu-id="d41e1-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="d41e1-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

