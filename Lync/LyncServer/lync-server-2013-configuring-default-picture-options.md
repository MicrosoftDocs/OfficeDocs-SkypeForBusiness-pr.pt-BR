---
title: 'Lync Server 2013: Configurando opções de imagem padrão'
description: 'Lync Server 2013: Configurando opções de imagem padrão.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6261aca82b4c71eb8e0573e8d2adbfc008e743fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557997"
---
# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="1084b-103">Configurando opções de imagem padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1084b-103">Configuring default picture options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1084b-104">_**Última modificação do tópico:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="1084b-104">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="1084b-105">Por padrão, as imagens dos usuários são exibidas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1084b-105">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="1084b-106">Se os usuários quiserem ocultar suas imagens, poderão selecionar a opção **ocultar minha imagem** no cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="1084b-106">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="1084b-107">No entanto, essa configuração é ignorada por alguns outros aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="1084b-107">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="1084b-108">Se a possibilidade de exibir imagens mesmo quando desativada pelo usuário é uma preocupação, você pode alterar as configurações de exibição de imagem do Lync globalmente ou para um site ou serviço para que as imagens dos usuários não sejam mostradas por padrão.</span><span class="sxs-lookup"><span data-stu-id="1084b-108">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="1084b-109">Use o seguinte cmdlet do Shell de gerenciamento do Lync Server para que as imagens do usuário não sejam mostradas, a menos que explicitamente selecione a opção **mostrar minha imagem** no cliente:</span><span class="sxs-lookup"><span data-stu-id="1084b-109">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="1084b-110">Para obter mais informações sobre esse cmdlet, consulte [set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1084b-110">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

