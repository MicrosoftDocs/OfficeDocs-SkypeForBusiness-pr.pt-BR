---
title: 'Lync Server 2013: Roteamento do Exchange UM hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cc1112effd0eac0a25614ee50d7008ee1c5e37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Roteamento do Exchange UM hospedado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

O aplicativo de roteamento de UM do Exchange é executado no servidor front-end para direcionar chamadas, seja para uma implantação do Microsoft Exchange Server Unified Messaging (UM) local ou para o serviço UM do Exchange UM hospedado.

<div>

## <a name="the-exum-routing-application"></a>O aplicativo de roteamento ExUM

O aplicativo de roteamento do Exchange UM do Lync Server 2013 usa as informações das configurações da conta do usuário e dos parâmetros da política de caixa postal hospedadas para determinar como direcionar chamadas para mensagens de voz hospedadas, conforme mostrado no diagrama a seguir.

**Exemplo de implantação mista de roteamento UM do Exchange**

![Implantação do Exchange um do Lync Server local] (images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Implantação do Exchange um do Lync Server local")

O roteamento do Exchange UM pode ser configurado para direcionar chamadas para usuários que estão habilitados para o Exchange um local, para usuários que estão habilitados para um Exchange UM hospedado ou para uma combinação dos dois.

Por exemplo, suponha que a caixa de correio de Roy e o serviço do Exchange UM sejam hospedados em uma implantação local do Exchange.

  - As informações de endereço proxy da conta de usuário Roy fornecem as informações que o aplicativo de roteamento ExUM usa para direcionar as chamadas para um servidor do Exchange UM local.

A caixa de correio de Alice e o serviço do Exchange UM estão localizados em um data center do provedor de serviços do Exchange hospedado. O roteamento para suas chamadas de UM do Exchange é configurado da seguinte maneira:

  - Os valores definidos no atributo msExchUCVoiceMailSettings da conta de usuário de Alice dizem para o aplicativo de roteamento ExUM verificar se há detalhes de roteamento em uma política de caixa postal hospedada.
    
    <div>
    

    > [!NOTE]  
    > O valor do atributo msExchUCVoiceMailSettings pode ser definido por um provedor de serviços do Exchange ou pelo administrador do Lync Server 2013. No exemplo mostrado no diagrama anterior, o valor (CsHostedVoiceMail = 1) foi definido pelo administrador do Lync Server 2013 para habilitar a caixa postal hospedada para Alice. Para obter detalhes sobre esse atributo, consulte <A href="lync-server-2013-hosted-exchange-user-management.md">Gerenciamento de usuários hospedados do Exchange no Lync Server 2013</A>.

    
    </div>

  - A política de caixa postal hospedada que é atribuída à conta de usuário de Alice fornece detalhes de roteamento:
    
      - Destino é o provedor de serviços de UM do Exchange UM (ls) hospedado. ExUm. \<hostedExchangeServer\>. com neste exemplo).
    
      - As organizações são identificadas pelas IDs de locatários, que são os FQDNs de roteamento para as mensagens SIP para locatários do Exchange Server localizados em ls. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com e Corp.litwareinc.com neste exemplo).
        
        <div>
        

        > [!NOTE]  
        > O FQDN para Exchange Online é exap.um.outlook.com.

        
        </div>
        
        Para obter detalhes, consulte [políticas de caixa postal hospedadas no Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

<div>


> [!NOTE]  
> Se o atributo msExchUCVoiceMailSettings e as configurações de endereço de proxy de UM estiverem presentes em uma conta de usuário, o atributo msExchUCVoiceMailSettings terá precedência.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

