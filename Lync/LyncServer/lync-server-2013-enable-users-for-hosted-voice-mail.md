---
title: 'Lync Server 2013: Habilitar usuários para correio de voz hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45872df26989d8d264ce77406bfbce86f321ccf8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Habilitar usuários para correio de voz hospedado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-24_

Siga o procedimento para habilitar os usuários do Lync Server 2013 para a caixa postal em um serviço do Exchange Unified Messaging (UM) hospedado.

Para obter detalhes, consulte [Gerenciamento de usuários hospedados do Exchange no Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) na documentação de planejamento.

Para obter detalhes sobre o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , consulte a documentação do Shell de gerenciamento do Lync Server.

<div>


> [!IMPORTANT]  
> Para que um usuário do Lync Server 2013 possa ser habilitado para a caixa postal hospedada, uma política de caixa postal hospedada que se aplica à conta de usuário deve ser implantada. Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">políticas de caixa postal hospedadas no Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>Para habilitar usuários para a caixa postal hospedada

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet Set-CsUser para configurar a conta de usuário para a caixa postal hospedada. Por exemplo, execute:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    O exemplo anterior define os seguintes parâmetros:
    
      - O **HostedVoiceMail** permite que as chamadas de correio de voz de um usuário sejam roteadas para UM Exchange um hospedado. Ele também sinaliza o Microsoft Lync 2013 para iluminar o indicador "Call voice mail".
    
      - **Identidade** especifica a conta de usuário a ser modificada. O valor IDENTITY pode ser especificado usando qualquer um dos seguintes formatos:
        
          - O endereço SIP do usuário
        
          - O nome de usuário do Active Directory do usuário do Active Directory
        
          - O nome de logon\\do domínio do usuário (por exemplo\\, contoso kenmyer)
        
          - O nome de exibição dos serviços de domínio Active Directory do usuário (por exemplo, Ken Myer). Se estiver usando o nome de exibição como o valor de identidade, você poderá usar o\*caractere curinga asterisco (). Por exemplo, a identidade "\* Smith" retorna todos os usuários que têm um nome de exibição que termina com o valor de cadeia de caracteres "Smith".
        
        <div>
        

        > [!NOTE]  
        > O nome de conta SAM do Active Directory do usuário não pode ser usado como o valor de identidade porque o SAM-Account-Name não é necessariamente exclusivo na floresta.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

