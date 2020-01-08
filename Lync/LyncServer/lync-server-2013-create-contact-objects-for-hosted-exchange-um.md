---
title: 'Lync Server 2013: Criar objetos de contato para Exchange UM hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53d5bdfe3b341f534a3e8066fe85be5e93b0a7f7
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Criar objetos de contato para Exchange UM hospedado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-24_

O procedimento a seguir explica como criar objetos de contato do atendedor automático (AA) ou do Subscriber Access (SA) para a Unificação de mensagens (UM) hospedada pelo Exchange.

Para obter detalhes, consulte [Gerenciamento de objeto de contato do Exchange hospedado no Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) na documentação de planejamento.

Para obter detalhes sobre como configurar objetos de contato, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Os objetos de contato do Lync Server 2013 podem ser habilitados para o Exchange UM hospedado, uma política de caixa postal hospedada que se aplica a ele deve ser implantada. Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">políticas de caixa postal hospedadas no Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>Para criar objetos de contato AA ou SA para o Exchange UM hospedado

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet New-CsExUmContact para criar objetos de contato necessários para sua implantação. Por exemplo, execute o seguinte para criar um objeto de contato AA e a SA:
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    Estes exemplos definem os seguintes parâmetros:
    
      - **SipAddress** especifica o endereço SIP do objeto de contato. Isso deve ser um endereço que ainda não foi usado para configurar um objeto de usuário ou de contato nos serviços de domínio Active Directory. Esse valor deve estar no formato "SIP:\<*endereço*\>SIP", conforme mostrado nos exemplos anteriores.
    
      - **RegistrarPool** especifica o nome de domínio totalmente qualificado (FQDN) do pool no qual o serviço registrador está em execução.
        
        <div class=" ">
        

        > [!NOTE]  
        > Os objetos de contato de UM Exchange não podem ser movidos para pools que fazem parte de implantações do Lync Server 2013 anteriores ao Lync Server 2013.

        
        </div>
    
      - **Ou** especifica a unidade organizacional do Active Directory na qual esse objeto de contato será localizado.
    
      - **DisplayNumber** especifica o número de telefone do objeto de contato. O número de telefone de cada objeto de contato deve ser exclusivo.
    
      - **AutoAttendant** especifica se o objeto de contato é um atendedor automático. O atendedor automático oferece um conjunto de prompts de voz que permitem que os chamadores naveguem pelo sistema telefônico e atinjam a parte que desejam entrar em contato. Um valor de **false** (o padrão) para esse parâmetro indica um objeto de contato de acesso ao Assinante.

</div>

</div>

<span> </span>

</div>

</div>

</div>

