---
title: 'Lync Server 2013: criar uma política de correio de voz hospedada no nível do site'
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
ms.openlocfilehash: 6aeae2e533bd62cf1f3e24e7ceff69b870ebc7b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Criar uma política de caixa postal hospedada no nível do site no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-24_

Uma política de *site* pode afetar todos os usuários que estão hospedados no site para o qual a política está definida. Se um usuário estiver configurado para acesso do Exchange UM hospedado e não tiver sido atribuída uma política por usuário, a política do site será aplicada. Se você não implantou uma política de site, a política global se aplica.

Para obter detalhes sobre como configurar políticas de site, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>Para criar uma política de caixa postal hospedada no site

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet New-CsHostedVoicemailPolicy para criar a política. Por exemplo, execute:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Este exemplo cria uma política de caixa postal hospedada com escopo de site e define os seguintes parâmetros:
    
      - **Identity** especifica um identificador exclusivo para a política, que inclui o escopo. Para uma política com escopo de site, o valor do parâmetro Identity deve ser especificado no `site:` * \<nome\>* do formato, por `site:Redmond`exemplo,.
    
      - **Destino** especifica o nome de domínio totalmente qualificado (FQDN) do serviço do Exchange um hospedado. Esse parâmetro é opcional, mas se você tentar habilitar um usuário para a caixa postal hospedada e a política atribuída do usuário não tiver um valor de destino, o habilitar falhará.
    
      - **Descrição** fornece informações descritivas opcionais sobre a política.
    
      - **Organização** especifica uma lista separada por vírgulas dos locatários do Exchange que os usuários do Lync Server 2013 em casa. Cada locatário deve ser especificado como FQDN do locatário no serviço do Exchange UM hospedado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

