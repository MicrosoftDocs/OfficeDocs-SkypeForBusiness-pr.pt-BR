---
title: 'Lync Server 2013: configurar um aplicativo SNMP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e11d79278318c99e1c6a1db3c4609e19553ba4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Configurar um aplicativo SNMP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

O Lync Server 2013 inclui uma interface de serviço Web padrão que você pode usar para conectar o serviço de informações de localização a aplicativos de protocolo de gerenciamento de rede simples (SNMP) que correspondem a endereços MAC com informações de porta e switch.

Se um aplicativo SNMP estiver instalado e o serviço de informações de localização não conseguir encontrar uma correspondência no banco de dados de localização, o serviço de informações de localização consultará automaticamente o aplicativo usando o endereço MAC fornecido pelo cliente. Em seguida, o serviço de informações de localização usa a porta e as informações de troca retornadas pelo aplicativo SNMP para consultar o banco de dados de localização novamente.

Para obter detalhes, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).

<div>


> [!NOTE]  
> Os endereços MAC não estão disponíveis em computadores que executam o Windows 8.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>Para configurar a URL do aplicativo SNMP

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o seguinte cmdlet para configurar a URL do aplicativo SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

