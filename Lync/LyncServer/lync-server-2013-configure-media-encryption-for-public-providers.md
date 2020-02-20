---
title: 'Lync Server 2013: configurar a criptografia de mídia para provedores públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 571aa8309ee310353adebecfc7b8fe737076b384
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="b97b6-102">Configurar a criptografia de mídia para provedores públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b97b6-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b97b6-103">_**Última modificação do tópico:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="b97b6-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="b97b6-104">Se você estiver implementando A Federação de áudio/vídeo (A/V) com o Windows Live Messenger, há dois parâmetros que precisam ser modificados: o nível de criptografia do Lync Server e a política EnablePublicCloudAccess.</span><span class="sxs-lookup"><span data-stu-id="b97b6-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="b97b6-105">Como padrão, o nível de criptografia está definido como Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="b97b6-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="b97b6-106">Você deve mudar esse nível para Suportado.</span><span class="sxs-lookup"><span data-stu-id="b97b6-106">You must change this setting to Supported.</span></span> <span data-ttu-id="b97b6-107">Se a política EnablePublicCloudAccess está definida como "false", ela precisa ser alterada para **True**.</span><span class="sxs-lookup"><span data-stu-id="b97b6-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="b97b6-108">Você pode fazer isso no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b97b6-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="b97b6-109">Configurar a federação para Windows Live</span><span class="sxs-lookup"><span data-stu-id="b97b6-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="b97b6-110">Inicie o Shell de gerenciamento do Lync Server no servidor front-end: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b97b6-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b97b6-111">No prompt de comando, digite os comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="b97b6-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="b97b6-112">Esta etapa é obrigatória pois o Windows Live Messenger não suporta criptografia de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="b97b6-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="b97b6-113">O comando define sua política global para suportar uma criptografia em vez de exigir criptografia de dados de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="b97b6-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="b97b6-114">Os clientes que suportam criptografia ainda usarão criptografia, como o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b97b6-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

