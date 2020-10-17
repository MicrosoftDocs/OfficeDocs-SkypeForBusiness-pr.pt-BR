---
title: 'Lync Server 2013: habilitar usuários para caixa postal hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c0975f6be3d78ec7634859b26e7ed35e7efee5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501028"
---
# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Habilitar usuários para caixa postal hospedada no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-24_

Siga o procedimento para habilitar os usuários do Lync Server 2013 para caixa postal em um serviço de UM (Unificação de mensagens) do Exchange hospedado.

Para obter detalhes, consulte [Hosted Exchange User Management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) na documentação de planejamento.

Para obter detalhes sobre o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , consulte a documentação do Shell de gerenciamento do Lync Server.

<div>


> [!IMPORTANT]  
> Antes que um usuário do Lync Server 2013 possa ser habilitado para caixa postal hospedada, uma política de caixa postal hospedada que se aplica à sua conta de usuário deve ser implantada. Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail Policies in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>Para habilitar usuários para caixa postal hospedada

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet Set-CsUser para configurar a conta de usuário para a caixa postal hospedada. Por exemplo, execute:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    O exemplo anterior define os seguintes parâmetros:
    
      - **HostedVoiceMail ** permite que as chamadas de caixa postal do usuário sejam roteadas para o UM do Exchange hospedado. Ele também sinaliza o Microsoft Lync 2013 para acelerar o indicador "Call de caixa postal".
    
      - **Identidade** especifica a conta de usuário a ser modificada. O valor de Identidade pode ser especificado usando qualquer um dos seguintes formatos:
        
          - O endereço SIP do usuário
        
          - O nome UPN do Active Directory do usuário
        
          - O nome de logon do domínio do usuário \\ (por exemplo, Contoso \\ kenmyer)
        
          - O Nome de exibição de serviços de domínio do Active Directory do usuário (por exemplo, Ken Myer). Se estiver usando o Display-Name como o valor de identidade, você poderá usar o \* caractere curinga asterisco (). Por exemplo, a identidade " \* Smith" retorna todos os usuários que têm um Display-Name que termina com o valor de cadeia de caracteres "Smith".
        
        <div>
        

        > [!NOTE]  
        > O Nome de conta SAM do Active Directory do usuário não pode ser usado como o valor de Identidade, pois o Nome de conta SAM não é necessariamente exclusivo na floresta.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

