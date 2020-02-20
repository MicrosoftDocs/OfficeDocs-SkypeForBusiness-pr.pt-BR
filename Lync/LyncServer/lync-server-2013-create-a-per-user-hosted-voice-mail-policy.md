---
title: 'Lync Server 2013: criar uma política de caixa postal hospedada por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e13002fa83215c5c1aade627cb6e7ea86cf0a04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Criar uma política de caixa postal hospedada por usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-24_

Uma política *por usuário* pode afetar somente usuários individuais, grupos ou objetos de contato. Para implantar uma política por usuário, atribua explicitamente a política a um ou mais usuários, grupos ou objetos de contato. Para obter detalhes, consulte [atribuir uma política de caixa postal hospedada por usuário no Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Para obter detalhes sobre como trabalhar com políticas de caixa postal hospedada por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>Para criar uma política de correio de voz hospedada por usuário

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet New-CsHostedVoicemailPolicy para criar a política. Por exemplo, execute:
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    O exemplo anterior cria uma política de correio de voz hospedada com o escopo por usuário, e define os seguintes parâmetros:
    
      - **Identidade** especifica um identificador exclusivo para a política, que inclui o escopo. Para uma política com escopo por usuário, esse valor de parâmetro é especificado como uma cadeia de caracteres simples, por exemplo, ExRedmond.
    
      - **Destino** especifica o nome de domínio completamente qualificado (FQDN) do serviço Exchange UM hospedado. Esse parâmetro é opcional, mas se você tentar ativar um usuário para o correio de voz hospedado e a política atribuída ao usuário não possui um valor de Destino, a ativação irá falhar.
    
      - **Descrição** fornece informações descritivas opcionais sobre a política.
    
      - **Organization** especifica uma lista separada por vírgulas dos locatários do Exchange que hospedam os usuários do Lync Server 2013. Cada inquilino deve ser especificado como o FQDN daquele inquilino no serviço UM do Exchange hospedado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Atribuir uma política de caixa postal hospedada por usuário no Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

