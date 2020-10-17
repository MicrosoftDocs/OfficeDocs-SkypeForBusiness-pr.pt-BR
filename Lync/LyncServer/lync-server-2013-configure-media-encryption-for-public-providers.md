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
ms.openlocfilehash: 45a6a3dcccc766e9905017c0b35949ab4ff6894d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520598"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Configurar a criptografia de mídia para provedores públicos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-12-12_

Se você estiver implementando A Federação de áudio/vídeo (A/V) com o Windows Live Messenger, há dois parâmetros que precisam ser modificados: o nível de criptografia do Lync Server e a política EnablePublicCloudAccess. Como padrão, o nível de criptografia está definido como Obrigatório. Você deve mudar esse nível para Suportado. Se a política EnablePublicCloudAccess está definida como "false", ela precisa ser alterada para **True**. Você pode fazer isso no Shell de gerenciamento do Lync Server.

<div>

## <a name="configure-federation-for-windows-live"></a>Configurar a federação para Windows Live

1.  Inicie o Shell de gerenciamento do Lync Server no servidor front-end: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.

2.  No prompt de comando, digite os comandos a seguir:
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Esta etapa é obrigatória pois o Windows Live Messenger não suporta criptografia de áudio/vídeo. O comando define sua política global para suportar uma criptografia em vez de exigir criptografia de dados de áudio/vídeo. Os clientes que suportam criptografia ainda usarão criptografia, como o Lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

