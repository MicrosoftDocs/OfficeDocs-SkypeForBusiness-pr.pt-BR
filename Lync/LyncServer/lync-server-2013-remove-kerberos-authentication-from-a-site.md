---
title: 'Lync Server 2013: remover a autenticação Kerberos de um site'
description: 'Lync Server 2013: remover a autenticação Kerberos de um site.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3d9100d07d37e98800cfce106bc75fcfaeaa59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553527"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>No Lync Server 2013 remover a autenticação Kerberos de um site

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-01-16_

Para concluir com sucesso este procedimento, você deve ter feito logon como usuário membro do grupo RTCUniversalServerAdmins.

Se for necessário remover a autenticação Kerberos de um site ou desativar um site, você deve remover a atribuição da conta da autenticação Kerberos do site usando o cmdlet **Remove-CsKerberosAccountAssignment**. Use o procedimento a seguir para remover a atribuição da conta da autenticação Kerberos, o que remove a atribuição de todos os computadores no site.

<div class=" ">


> [!WARNING]  
> Se você estiver desativando permanentemente a conta habilitada para Kerberos, deverá usar usuários e computadores do Active Directory para excluí-la dos serviços de domínio do Active Directory após a remoção da atribuição. Se você planeja usar o objeto no futuro, pode ser desejável manter o objeto do Active Directory.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>Para remover a autenticação Kerberos de um site

1.  Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que executa o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Na linha de comando, execute os dois comandos a seguir:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    Por exemplo:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Após fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar o <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

