---
title: 'Lync Server 2013: Relatar atribuições da conta Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02eb3cae7a7d2bbeb4cc3b9dce0a7daa8ee5c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Relatar atribuições da conta Kerberos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-01-16_

Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins.

Você pode usar o cmdlet **Get-CsKerberosAccountAssignment** para consultar informações sobre as atribuições de conta de autenticação Kerberos e informações de relatório sobre as atribuições atuais na sua implantação.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>Para consultar as atribuições de conta de autenticação Kerberos para um site

1.  Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que está executando o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Na linha de comando, execute um dos seguintes comandos:
    
      - Para consultar todas as atribuições de conta de autenticação Kerberos em sua organização e retornar informações de atribuição sobre cada uma delas, execute o cmdlet sem parâmetros:
        
            Get-CsKerberosAccountAssignment
    
      - Para consultar todas as atribuições de conta de autenticação Kerberos na implantação e retornar informações de atribuição de site sobre cada uma delas, execute o cmdlet com o parâmetro de identidade:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Por exemplo:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Para consultar todas as atribuições de conta de autenticação Kerberos em um único site e retornar informações de atribuição sobre cada uma delas, execute o cmdlet com o parâmetro de filtro:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Por exemplo:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Especificar * SiteName para o parâmetro Filter retorna informações sobre todos os sites que contêm o nome do site especificado em qualquer lugar no identificador de site (por exemplo, todos os sites que contêm a cadeia de caracteres Redmond no identificador do site).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

