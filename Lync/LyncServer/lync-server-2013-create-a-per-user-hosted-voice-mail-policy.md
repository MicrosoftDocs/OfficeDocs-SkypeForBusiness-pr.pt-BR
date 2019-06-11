---
title: 'Lync Server 2013: criar uma política de correio de voz hospedada por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d09638c28c1cbd2b068972aff169376508325885
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Criar uma política de correio de voz hospedada por usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-24_

Uma política *por usuário* pode impactar apenas usuários individuais, grupos e objetos de contato. Para implantar uma política por usuário, você deve explicitamente atribuir a política a um ou mais usuários, grupos ou objetos de contato. Para obter detalhes, consulte [atribuir uma política de correio de voz hospedada por usuário no Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Para obter detalhes sobre como trabalhar com políticas de correio de voz hospedadas por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>Para criar uma política de correio de voz hospedada por usuário

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet New-CsHostedVoicemailPolicy para criar a política. Por exemplo, execute:
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    O exemplo anterior cria uma política de caixa postal hospedada com o escopo por usuário e define os seguintes parâmetros:
    
      - **Identity** especifica um identificador exclusivo para a política, que inclui o escopo. Para uma política com escopo por usuário, esse valor de parâmetro é especificado como uma cadeia de caracteres simples, por exemplo, exrio.
    
      - **Destino** especifica o nome de domínio totalmente qualificado (FQDN) do serviço do Exchange um hospedado. Esse parâmetro é opcional, mas se você tentar habilitar um usuário para a caixa postal hospedada e a política atribuída do usuário não tiver um valor de destino, o habilitar falhará.
    
      - **Descrição** fornece informações descritivas opcionais sobre a política.
    
      - **Organização** especifica uma lista separada por vírgulas dos locatários do Exchange que os usuários do Lync Server 2013 em casa. Cada locatário deve ser especificado como FQDN do locatário no serviço do Exchange UM hospedado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Atribuir uma política de correio de voz hospedada por usuário no Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

