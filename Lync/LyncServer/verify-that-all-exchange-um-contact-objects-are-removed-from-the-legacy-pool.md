---
title: Verificar se todos os objetos de contato do UM do Exchange foram removidos do pool herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7815f78dfa5f2b4aab3f09102a9948498c20cf10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="aa93d-102">Verificar se todos os objetos de contato do UM do Exchange foram removidos do pool herdado</span><span class="sxs-lookup"><span data-stu-id="aa93d-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa93d-103">_**Última modificação do tópico:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="aa93d-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="aa93d-104">Use a ferramenta **OCSUmUtil** ou o cmdlet **Get-CsExumContact** para verificar se os objetos de contato do um do Exchange foram removidos do pool herdado do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aa93d-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="aa93d-105">**OCSUmUtil** está localizado na seguinte pasta:</span><span class="sxs-lookup"><span data-stu-id="aa93d-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="aa93d-106">% Arquivos de programa\\% arquivos\\comuns do Lync\\Server\\2013 suportam ocsumutil. exe</span><span class="sxs-lookup"><span data-stu-id="aa93d-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="aa93d-107">**OCSUmUtil** precisa ser executado a partir de uma conta de usuário que tenha:</span><span class="sxs-lookup"><span data-stu-id="aa93d-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="aa93d-108">Associação ao grupo RTCUniversalServerAdmins e RTCUniversalUserAdmins (que inclui direitos para ler as configurações da Unificação de Mensagens do Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="aa93d-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="aa93d-109">Direitos no domínio para criar objetos de contato no contêiner de unidade organizacional (UO) especificado</span><span class="sxs-lookup"><span data-stu-id="aa93d-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="aa93d-110">Para obter detalhes sobre como usar o cmdlet **Get-CsExumContact** , consulte [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aa93d-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

