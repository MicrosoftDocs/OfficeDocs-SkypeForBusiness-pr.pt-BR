---
title: 'Lync Server 2013: Configurar criptografia de mídia para fornecedores públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1496bda01456593066efd212241e3d930f1e2cc6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="1837f-102">Configurar criptografia de mídia para fornecedores públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1837f-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1837f-103">_**Tópico da última modificação:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="1837f-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="1837f-104">Se você estiver implementando a Federação de áudio/vídeo (A/V) com o Windows Live Messenger, há dois parâmetros que você precisa modificar: o nível de criptografia do Lync Server e a política EnablePublicCloudAccess.</span><span class="sxs-lookup"><span data-stu-id="1837f-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="1837f-105">Por padrão, o nível de criptografia é definido como obrigatório.</span><span class="sxs-lookup"><span data-stu-id="1837f-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="1837f-106">Você deve alterar essa configuração para com suporte.</span><span class="sxs-lookup"><span data-stu-id="1837f-106">You must change this setting to Supported.</span></span> <span data-ttu-id="1837f-107">Se a política EnablePublicCloudAccess estiver definida como false, isso precisará ser definido como **true**.</span><span class="sxs-lookup"><span data-stu-id="1837f-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="1837f-108">Você pode fazer isso a partir do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1837f-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="1837f-109">Configurar a Federação para o Windows Live</span><span class="sxs-lookup"><span data-stu-id="1837f-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="1837f-110">Inicie o Shell de gerenciamento do Lync Server no servidor front-end: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1837f-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1837f-111">No prompt de comando, digite os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="1837f-111">From the command prompt, type the following commands:</span></span>
    
       ```
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="1837f-112">Esta etapa é obrigatória porque o Windows Live Messenger não dá suporte à criptografia de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="1837f-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="1837f-113">O comando define sua política global como uma configuração de criptografia de suporte em vez de exigir criptografia dos dados de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="1837f-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="1837f-114">Os clientes que dão suporte à criptografia ainda usarão a criptografia, como o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1837f-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

