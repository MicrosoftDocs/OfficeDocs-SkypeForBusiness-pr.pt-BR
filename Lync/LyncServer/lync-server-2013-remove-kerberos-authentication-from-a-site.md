---
title: 'Lync Server 2013: Remover autenticação Kerberos de um site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f030083bc49822f1d41e297388f6ca7dbf66d397
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>No Lync Server 2013, remover autenticação Kerberos de um site

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-01-16_

Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins.

Se precisar remover a autenticação Kerberos de um site ou de remover um site, você deve remover a atribuição de conta de autenticação Kerberos do site usando o cmdlet **Remove-CsKerberosAccountAssignment** . Use o procedimento a seguir para remover a atribuição de conta de autenticação Kerberos, que remove a atribuição de todos os computadores do site.

<div class=" ">


> [!WARNING]  
> Se você estiver desativando permanentemente a conta habilitada para Kerberos, use os usuários e computadores do Active Directory para excluí-la dos serviços de domínio Active Directory depois de ter removido a tarefa. Se você planeja usar o objeto no futuro, talvez queira manter o objeto do Active Directory.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>Para remover a autenticação Kerberos de um site

1.  Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que está executando o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Na linha de comando, execute os dois comandos a seguir:
    
       ```
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    Por exemplo:
    
       ```
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Depois de fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

