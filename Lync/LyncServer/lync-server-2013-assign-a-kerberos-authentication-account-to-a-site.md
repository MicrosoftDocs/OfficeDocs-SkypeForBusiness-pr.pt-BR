---
title: 'Lync Server 2013: atribuir uma conta de autenticação Kerberos a um site'
description: 'Lync Server 2013: atribuir uma conta de autenticação Kerberos a um site.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edcd80ef3ae15ae91dfab73ee8789054d897fe5c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559967"
---
# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Atribuir uma conta de autenticação Kerberos a um site no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2017-04-18_

Para concluir com sucesso este procedimento, você deve ter feito logon como usuário membro do grupo RTCUniversalServerAdmins.

Depois de criar a conta Kerberos, você deve atribuí-la a um site. Este é um site do Lync Server 2013, não um site do Active Directory. Você pode criar várias contas de autenticação Kerberos por implantação, mas pode atribuir apenas uma conta a um site. Use o procedimento a seguir para atribuir uma conta de autenticação Kerberos criada anteriormente a um site. Para obter detalhes sobre como criar a conta Kerberos, consulte [criar uma conta de autenticação Kerberos no Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>Para atribuir uma conta de autenticação Kerberos a um site

1.  Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que executa o Lync Server 2013 ou em um computador onde as ferramentas administrativas estão instaladas.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Na linha de comando, execute os dois comandos a seguir:
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    Por exemplo:
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Você deve especificar o parâmetro UserAccount usando o formato Domínio\Usuário. Não há suporte para o formato Usuário@Domínio.extensão para fazer referência a objetos de computador criados para fins de autenticação Kerberos.

    
    </div>

4.  **Opcional**: você pode ter configurado um FQDN de substituição (nome de domínio totalmente qualificado) para seus serviços [da Web, conforme altera a URL de serviços Web no Lync Server 2013](lync-server-2013-change-the-web-services-url.md). Se esse for o caso, você também precisará adicionar um SPN para esse FQDN. Por exemplo, se o FQDN era WebServices. contoso. local, você executaria:
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > Após fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar o <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

