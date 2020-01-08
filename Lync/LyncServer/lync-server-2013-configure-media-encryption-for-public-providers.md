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
ms.openlocfilehash: 270035730b8268c56b1730d8c212e90c8a9f1a30
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Configurar criptografia de mídia para fornecedores públicos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-12-12_

Se você estiver implementando a Federação de áudio/vídeo (A/V) com o Windows Live Messenger, há dois parâmetros que você precisa modificar: o nível de criptografia do Lync Server e a política EnablePublicCloudAccess. Por padrão, o nível de criptografia é definido como obrigatório. Você deve alterar essa configuração para com suporte. Se a política EnablePublicCloudAccess estiver definida como false, isso precisará ser definido como **true**. Você pode fazer isso a partir do Shell de gerenciamento do Lync Server.

<div>

## <a name="configure-federation-for-windows-live"></a>Configurar a Federação para o Windows Live

1.  Inicie o Shell de gerenciamento do Lync Server no servidor front-end: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  No prompt de comando, digite os seguintes comandos:
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Esta etapa é obrigatória porque o Windows Live Messenger não dá suporte à criptografia de áudio/vídeo. O comando define sua política global como uma configuração de criptografia de suporte em vez de exigir criptografia dos dados de áudio/vídeo. Os clientes que dão suporte à criptografia ainda usarão a criptografia, como o Lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

