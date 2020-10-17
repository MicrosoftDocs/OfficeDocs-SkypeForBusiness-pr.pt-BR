---
title: 'Lync Server 2013: validar endereços'
description: 'Lync Server 2013: validar endereços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcbb8789912b3bcbcfb60dd79807f06c2957c1f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547267"
---
# <a name="validate-addresses-in-lync-server-2013"></a>Validar endereços no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-17_

Antes de publicar o banco de dados local, você deverá validar novas localizações em relação ao MSAG (Master Street Address Guide) mantido pelo seu tronco SIP ou pelo provedor de serviços de rede telefônica pública comutada (PSTN) E9-1-1.

Para obter detalhes sobre os provedores de serviço E9-1-1 do tronco SIP, consulte [escolhendo um provedor de serviço E9-1-1 para o Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Para obter detalhes sobre como validar endereços, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>Para validar endereços localizados no banco de dados de localização

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute os cmdlets a seguir para configurar a conexão com o provedor de serviços de emergência.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Execute o cmdlet a seguir para validar os endereços no banco de dados de localização.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    Você também pode usar o cmdlet **Test-CsLisCivicAddress** para validar endereços individuais.

</div>

</div>

<span> </span>

</div>

</div>

</div>

