---
title: 'Lync Server 2013: roteamento do Exchange UM hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 815ddf2922c13bfc0889d6567479458aecd7d707
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Roteamento do Exchange UM hospedado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

O aplicativo de roteamento de UM do Exchange é executado no servidor front-end para encaminhar chamadas para uma implantação local da UM (Unificação de mensagens) do Microsoft Exchange Server ou para o serviço UM do Exchange hospedado.

<div>

## <a name="the-exum-routing-application"></a>O aplicativo ExUM Routing

O aplicativo de roteamento de UM do Lync Server 2013 do Exchange usa informações de configurações de conta de usuário e de parâmetros de política de caixa postal hospedada para determinar como rotear chamadas para mensagens de voz hospedadas, conforme mostrado no diagrama a seguir.

**Exemplo de implantação mista de encaminhamento do UM do Exchange**

![Implantação de UM do Exchange do Lync Server local](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Implantação de UM do Exchange do Lync Server local")

O roteamento da UM do Exchange pode ser configurado para rotear chamadas para usuários habilitados para um do Exchange local, para usuários habilitados para um do Exchange hospedado ou para uma combinação dos dois.

Por exemplo, suponha que a caixa de correio da Roy e o serviço UM do Exchange estejam hospedados em uma implantação local do Exchange.

  - As informações de endereço de proxy da conta de usuário Roy fornecem as informações que o aplicativo de roteamento ExUM usa para rotear chamadas para um servidor de UM do Exchange local.

A caixa de correio de Alice e o serviço UM do Exchange estão localizados em um data center do provedor de serviço do Exchange hospedado. O roteamento de suas chamadas de UM do Exchange é configurado da seguinte maneira:

  - Os valores definidos no atributo msExchUCVoiceMailSettings de conta de usuário de Alice solicitam que o aplicativo ExUM Routing verifique os detalhes de encaminhamento em uma política de caixa postal hospedada.
    
    <div>
    

    > [!NOTE]  
    > O valor do atributo msExchUCVoiceMailSettings pode ser definido pelo provedor de serviços do Exchange ou pelo administrador do Lync Server 2013. No exemplo mostrado no diagrama anterior, o valor (CsHostedVoiceMail = 1) foi definido pelo administrador do Lync Server 2013 para habilitar a caixa postal hospedada para Ana Maria. Para obter detalhes sobre esse atributo, consulte <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange User Management in Lync Server 2013</A>.

    
    </div>

  - A política de caixa postal hospedada atribuída à conta de usuário de Alice fornece os detalhes de encaminhamento:
    
      - O destino é o provedor de serviços UM UM do Exchange hospedado (ls. ExUm. \<hostedExchangeServer\>. com neste exemplo).
    
      - As organizações são identificadas pelas IDs de locatário, que são os FQDNs de roteamento para mensagens SIP para locatários do Exchange Server que estão localizados na ls. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com e Corp.litwareinc.com neste exemplo).
        
        <div>
        

        > [!NOTE]  
        > O FQDN para Exchange Online é exap.um.outlook.com.

        
        </div>
        
        Para obter detalhes, consulte [Hosted voice mail Policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

<div>


> [!NOTE]  
> Se o atributo msExchUCVoiceMailSettings e as configurações de endereço proxy do UM estiverem presentes em uma conta de usuário, o atributo msExchUCVoiceMailSettings prevalecerá.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

