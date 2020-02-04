---
title: 'Lync Server 2013: validar endereços'
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
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a>Validar endereços no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-17_

Antes de publicar o banco de dados de localização, você deve validar novos locais em relação ao guia de endereço mestre (MSAG) que é mantido pelo seu tronco SIP ou provedor de serviços de rede telefônica pública comutada (PSTN) E9-1.

Para obter detalhes sobre os provedores de serviços do tronco SIP E9-1, consulte [escolhendo um provedor de serviços de E9-1-1 para o Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Para obter detalhes sobre como validar os endereços, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>Para validar endereços localizados no banco de dados de localização

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

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

