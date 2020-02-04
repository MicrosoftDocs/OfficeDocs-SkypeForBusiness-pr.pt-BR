---
title: 'Lync Server 2013: modificar a política de caixa de correio de voz hospedada global'
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
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Modificar a política de caixa de correio de voz hospedada global no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-24_

A política de caixa de correio de voz hospedada *global* é instalada com o Lync Server 2013. Você pode modificá-la para atender às suas necessidades, mas não pode renomeá-la ou excluí-la. Para modificar a política global, use o cmdlet Set-CsHostedVoicemailPolicy para definir os parâmetros para os valores apropriados para a implantação específica.

Para obter detalhes sobre o cmdlet [set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , consulte a documentação do Shell de gerenciamento do Lync Server.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>Para modificar a política de caixa de correio de voz hospedada global

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet Set-CsHostedVoicemailPolicy para definir os parâmetros de política global do seu ambiente. Por exemplo, execute:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Como esse comando não especifica o parâmetro Identity da política, a interface de linha de comando do Windows PowerShell define os seguintes valores na política de caixa postal hospedada global:
    
      - **Destino** especifica o nome de domínio totalmente qualificado (FQDN) do serviço do Exchange um hospedado. Esse parâmetro é opcional, mas se você tentar habilitar um usuário para a caixa postal hospedada e a política atribuída do usuário não tiver um valor de destino, o habilitar falhará.
    
      - **Organização** especifica uma lista separada por vírgulas dos locatários do Exchange que hospedam os usuários do Lync Server. Cada locatário deve ser especificado como FQDN do locatário no serviço do Exchange UM hospedado.
    
    <div>
    

    > [!NOTE]  
    > No cmdlet do exemplo anterior, o valor "corp1.litwareinc.com" substitui qualquer valor que já esteja presente no parâmetro da organização. Por exemplo, se a política já contiver uma lista separada por vírgulas de organizações, a lista completa será substituída. Se você quiser adicionar uma organização à lista em vez de substituir a lista inteira, execute um comando semelhante ao seguinte.

    
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

