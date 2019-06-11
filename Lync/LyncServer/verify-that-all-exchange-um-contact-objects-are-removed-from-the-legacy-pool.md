---
title: Verificar se todos os objetos de contato do Exchange UM são removidos do pool herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0db8f4c55d863221c9a66d33a21bbe073bbc225a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="a6432-102">Verificar se todos os objetos de contato do Exchange UM são removidos do pool herdado</span><span class="sxs-lookup"><span data-stu-id="a6432-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6432-103">_**Tópico da última modificação:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="a6432-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="a6432-104">Use a ferramenta **OCSUmUtil** ou o cmdlet **Get-CsExumContact** para verificar se objetos de contato do Exchange um foram removidos do pool herdado do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a6432-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="a6432-105">O **OCSUmUtil** está localizado na seguinte pasta:</span><span class="sxs-lookup"><span data-stu-id="a6432-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="a6432-106">% Arquivos de programas\\% arquivos\\comuns o Lync\\Server\\2013 suporta ocsumutil. exe</span><span class="sxs-lookup"><span data-stu-id="a6432-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="a6432-107">O **OCSUmUtil** deve ser executado a partir de uma conta de usuário que tenha:</span><span class="sxs-lookup"><span data-stu-id="a6432-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="a6432-108">Associação no grupo RTCUniversalServerAdmins e RTCUniversalUserAdmins (que inclui direitos para ler as configurações de mensagens unificadas do Exchange Server)</span><span class="sxs-lookup"><span data-stu-id="a6432-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="a6432-109">Direitos de domínio para criar objetos de contato no contêiner de unidade organizacional (UO) especificado</span><span class="sxs-lookup"><span data-stu-id="a6432-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="a6432-110">Para obter detalhes sobre como usar o cmdlet **Get-CsExumContact** , consulte [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6432-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

