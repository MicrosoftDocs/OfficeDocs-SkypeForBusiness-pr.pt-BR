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
ms.openlocfilehash: 48ef29fdf87dd25365a5aae69cb4c8115e410025
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522988"
---
# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Configurar um aplicativo SNMP no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

O Lync Server 2013 inclui uma interface de serviço Web padrão que você pode usar para conectar o serviço de informações de local aos aplicativos SNMP que correspondem a endereços MAC com informações de porta e switch.

Se um aplicativo SNMP estiver instalado e o serviço de informações de local não conseguir localizar uma correspondência no banco de dados de local, o serviço de informações de local consultará automaticamente o aplicativo usando o endereço MAC fornecido pelo cliente. O serviço de informações de local usa as informações de porta e switch retornadas pelo aplicativo SNMP para consultar o banco de dados de local novamente.

Para obter detalhes, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).

<div>


> [!NOTE]  
> Os endereços MAC não estão disponíveis em computadores que executam o Windows 8.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>Para configurar a URL do aplicativo SNMP

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o seguinte cmdlet para configurar a URL do aplicativo SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

