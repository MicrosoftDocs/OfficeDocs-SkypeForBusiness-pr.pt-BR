---
title: 'Lync Server 2013: configurar a criptografia de mídia para provedores públicos'
description: 'Lync Server 2013: Configure Media Encryption for Public Providers.'
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
ms.openlocfilehash: 177c19f151b67d741c7e26506f7ebc98b3ce831a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577617"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="cb528-103">Configurar a criptografia de mídia para provedores públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb528-103">Configure media encryption for public providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb528-104">_**Última modificação do tópico:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="cb528-104">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="cb528-105">Se você estiver implementando A Federação de áudio/vídeo (A/V) com o Windows Live Messenger, há dois parâmetros que precisam ser modificados: o nível de criptografia do Lync Server e a política EnablePublicCloudAccess.</span><span class="sxs-lookup"><span data-stu-id="cb528-105">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="cb528-106">Como padrão, o nível de criptografia está definido como Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="cb528-106">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="cb528-107">Você deve mudar esse nível para Suportado.</span><span class="sxs-lookup"><span data-stu-id="cb528-107">You must change this setting to Supported.</span></span> <span data-ttu-id="cb528-108">Se a política EnablePublicCloudAccess está definida como "false", ela precisa ser alterada para **True**.</span><span class="sxs-lookup"><span data-stu-id="cb528-108">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="cb528-109">Você pode fazer isso no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cb528-109">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="cb528-110">Configurar a federação para Windows Live</span><span class="sxs-lookup"><span data-stu-id="cb528-110">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="cb528-111">Inicie o Shell de gerenciamento do Lync Server no servidor front-end: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cb528-111">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cb528-112">No prompt de comando, digite os comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="cb528-112">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="cb528-113">Esta etapa é obrigatória pois o Windows Live Messenger não suporta criptografia de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="cb528-113">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="cb528-114">O comando define sua política global para suportar uma criptografia em vez de exigir criptografia de dados de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="cb528-114">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="cb528-115">Os clientes que suportam criptografia ainda usarão criptografia, como o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cb528-115">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

