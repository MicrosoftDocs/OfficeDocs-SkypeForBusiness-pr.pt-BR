---
title: 'Lync Server 2013: modificar a política de caixa postal hospedada global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1746f622afb380f53a0109400a7d326b0b3c5de7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Modificar a política de caixa postal hospedada global no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-24_

A política de caixa postal hospedada *global* é instalada com o Lync Server 2013. É possível modificá-la para corresponder às suas necessidades, mas não é possível renomear ou exclui-la. Para modificar a política global, deve usar o cmdlet Set-CsHostedVoicemailPolicy para definir os parâmetros para os valores adequados da sua implantação específica.

Para obter detalhes sobre o cmdlet [set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , consulte a documentação do Shell de gerenciamento do Lync Server.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>Para modificar a política de caixa postal hospedada global

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o Set-CsHostedVoicemailPolicy para definir os parâmetros da política global do seu ambiente. Por exemplo, execute:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Como esse comando não especifica o parâmetro Identity da política, a interface de linha de comando do Windows PowerShell define os seguintes valores na política de caixa postal hospedada global:
    
      - **Destino** especifica o FQDN do serviço UM do Exchange hospedado. Este parâmetro é opcional, mas se você tentar habilitar um usuário para a caixa postal hospedada e a política atribuída do usuário não possui um valor de Destino, a habilitação falhará.
    
      - **Organization** especifica uma lista separada por vírgulas dos locatários do Exchange que hospedam os usuários do Lync Server. Cada inquilino deve ser especificado como o FQDN daquele inquilino no serviço UM do Exchange hospedado.
    
    <div>
    

    > [!NOTE]  
    > No cmdlet de exemplo anterior, o valor “corp1.litwareinc.com” substitui qualquer valor que pode já estar presente no parâmetro Organização. Por exemplo, se a política já contém uma lista separada por vírgulas da organização, a lista completa seria substituída. Se deseja adicionar uma organização à lista ao invés de substituir toda a lista, execute um comando similar ao seguinte.

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

