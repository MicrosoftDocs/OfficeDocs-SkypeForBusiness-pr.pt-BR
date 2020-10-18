---
title: 'Lync Server 2013: relatar atribuições de conta Kerberos'
description: 'Lync Server 2013: relatar atribuições de conta Kerberos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23e40dddfc4538db70e2101b1bfcbbce2fe3fa8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576117"
---
# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Relatar as atribuições de conta Kerberos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-01-16_

Para concluir com sucesso este procedimento, você deve ter feito logon como usuário membro do grupo RTCUniversalServerAdmins.

Você pode usar o cmdlet **Get-CsKerberosAccountAssignment** para consultar informações sobre as atribuições de conta de autenticação Kerberos e relatar as informações sobre as atribuições atuais em sua implantação.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>Para consultar as atribuições da conta de autenticação Kerberos de um site

1.  Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que executa o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Na linha de comando, execute um dos seguintes comandos:
    
      - Para consultar todas as atribuições de conta de autenticação Kerberos em sua organização e retornar as informações de atribuição sobre cada um deles, execute o cmdlet sem parâmetros:
        
            Get-CsKerberosAccountAssignment
    
      - Para consultar todas as atribuições de conta de autenticação Kerberos em sua implantação e retornar as informações de atribuição sobre cada um deles, execute o cmdlet com o parâmetro Identity:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Por exemplo:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Para consultar todas as atribuições de conta de autenticação Kerberos em um único site e retornar as informações de atribuição sobre cada um deles, execute o cmdlet com o parâmetro Filter:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Por exemplo:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Especificar * SiteName para o parâmetro Filter retorna as informações sobre todos os sites que contêm o nome do site especificado em qualquer lugar no identificador de site (por exemplo, todos os sites que contêm a cadeia de caracteres Redmond no identificador de site).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

