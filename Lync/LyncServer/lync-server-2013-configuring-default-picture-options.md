---
title: 'Lync Server 2013: Configurando opções de imagem padrão'
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
ms.openlocfilehash: fc6bb0368b97e41402f2e0abf0834cf23f078c08
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514808"
---
# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="c9c3e-102">Configurando opções de imagem padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9c3e-102">Configuring default picture options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9c3e-103">_**Última modificação do tópico:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="c9c3e-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="c9c3e-104">Por padrão, as imagens dos usuários são exibidas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c9c3e-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="c9c3e-105">Se os usuários quiserem ocultar suas imagens, poderão selecionar a opção **ocultar minha imagem** no cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="c9c3e-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="c9c3e-106">No entanto, essa configuração é ignorada por alguns outros aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="c9c3e-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="c9c3e-107">Se a possibilidade de exibir imagens mesmo quando desativada pelo usuário é uma preocupação, você pode alterar as configurações de exibição de imagem do Lync globalmente ou para um site ou serviço para que as imagens dos usuários não sejam mostradas por padrão.</span><span class="sxs-lookup"><span data-stu-id="c9c3e-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="c9c3e-108">Use o seguinte cmdlet do Shell de gerenciamento do Lync Server para que as imagens do usuário não sejam mostradas, a menos que explicitamente selecione a opção **mostrar minha imagem** no cliente:</span><span class="sxs-lookup"><span data-stu-id="c9c3e-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="c9c3e-109">Para obter mais informações sobre esse cmdlet, consulte [set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9c3e-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

