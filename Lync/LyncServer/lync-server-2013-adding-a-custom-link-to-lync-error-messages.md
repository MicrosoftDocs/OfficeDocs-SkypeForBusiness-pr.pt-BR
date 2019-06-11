---
title: 'Lync Server 2013: Adicionando um link personalizado às mensagens de erro do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f62dd7841f77a519653a658131423a89f77ed012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="a88f1-102">Adicionando um link personalizado às mensagens de erro do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a88f1-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a88f1-103">_**Tópico da última modificação:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a88f1-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a88f1-104">Personalize mensagens de erro do Lync 2013 adicionando um link para suas próprias informações de solução de problemas ou suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="a88f1-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="a88f1-105">Para fazer isso, use os cmdlets shell do Shell de gerenciamento do Lync Server **New-CSClientPolicy** ou **set-CSClientPolicy** com o parâmetro CustomLinkInErrorMessages.</span><span class="sxs-lookup"><span data-stu-id="a88f1-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="a88f1-106">O texto do link personalizado é "clique aqui para obter tópicos de suporte do administrador" e não pode ser personalizado.</span><span class="sxs-lookup"><span data-stu-id="a88f1-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="a88f1-107">Por exemplo, o comando a seguir faz com que o link personalizado apareça na área de notas de rodapé de cada mensagem de erro do Lync 2013 e define o destino do link comohttp://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="a88f1-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="a88f1-108">Use **Grant-CSClientPolicy** para atribuir esta nova política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="a88f1-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="a88f1-109">Para obter detalhes, consulte **New-CSClientPolicy** and **Grant-CSClientPolicy** na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a88f1-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

