---
title: 'Lync Server 2013: adicionando texto personalizado a mensagens instantâneas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e42c04c84d6df91b592bf4709daf36d6822aa49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="68b64-102">Adicionando texto personalizado a mensagens instantâneas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68b64-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68b64-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="68b64-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="68b64-104">Adicione um aviso de isenção de responsabilidade ao início de cada conversa de IM (mensagens instantâneas) do Lync 2013 usando os cmdlets **New-CSClientPolicy** ou **set-CSClientPolicy** do Shell de gerenciamento do Lync Server com o parâmetro imwarning.</span><span class="sxs-lookup"><span data-stu-id="68b64-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="68b64-105">O comando no exemplo a seguir adiciona um lembrete de segurança na parte superior da janela Conversa sempre que uma nova conversa de IM começa:</span><span class="sxs-lookup"><span data-stu-id="68b64-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="68b64-106">Use **Grant-CSClientPolicy** para atribuir essa nova política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="68b64-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="68b64-107">Para obter detalhes, consulte **New-CSClientPolicy** e **Grant-CSClientPolicy** na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68b64-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

