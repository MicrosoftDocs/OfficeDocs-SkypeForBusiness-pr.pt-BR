---
title: 'Lync Server 2013: criar uma política de caixa postal hospedada no nível do site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9518b605ed6c79418e58fd0d3f9aab0e4d493957
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Criar uma política de caixa postal hospedada no nível do site no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-24_

Uma política de *local* pode afetar todos os usuários hospedados no local em que a política foi definida. Se um usuário for configurado para acesso hospedado ao serviço de UM do Exchange e não tiver recebido uma política Por usuário, a política de local será aplicada. Caso não tenha implantado uma política de local, será aplicada a política global.

Para obter detalhes sobre como configurar políticas de site, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>Para criar uma política de caixa postal hospedada em um site

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet New-CsHostedVoicemailPolicy para criar a política. Por exemplo, execute:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Esse exemplo cria uma política de caixa postal com escopo do site e define os parâmetros a seguir:
    
      - A **Identidade** especifica um identificador único para a política, o que inclui o escopo. Para uma política com escopo de site, o valor do parâmetro Identity deve ser especificado no `site:` * \<nome\>* do formato, por `site:Redmond`exemplo,.
    
      - **Destino** especifica o nome de domínio completamente qualificado (FQDN) do serviço Exchange UM hospedado. Esse parâmetro é opcional, mas se você tentar ativar um usuário para o correio de voz hospedado e a política atribuída ao usuário não possui um valor de Destino, a ativação irá falhar.
    
      - **Descrição** fornece informações descritivas opcionais sobre a política.
    
      - **Organization** especifica uma lista separada por vírgulas dos locatários do Exchange que hospedam os usuários do Lync Server 2013. Cada inquilino deve ser especificado como FQDN daquele inquilino no serviço hospedado de UM do Exchange.

</div>

</div>

<span> </span>

</div>

</div>

</div>

