---
title: 'Lync Server 2013: definir uma senha de conta de autenticação Kerberos em um servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20229f7bbc600b6a54bf28b13b9d5c14e8cbeb28
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510038"
---
# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Definir uma senha de conta de autenticação Kerberos em um servidor no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-01-16_

Para concluir com sucesso este procedimento, você deve ter feito logon como usuário membro do grupo RTCUniversalServerAdmins.

Você deve configurar uma senha na conta Kerberos para cada site que possua Servidores front end, servidores Standard Edition e Diretores. Você pode configurar a senha executando o cmdlet **set-CsKerberosAccountPassword**do   Windows PowerShell em um servidor no site (por exemplo, um servidor front-end). Para cada site, você deve executar o cmdlet **set-CsKerberosAccountPassword**   . O cmdlet configura o IIS (serviços de informações da Internet) para o serviço de serviços Web e, em seguida, define a senha na conta do computador nos serviços de domínio do Active Directory. Um método alternativo, com base no parâmetro usado com o cmdlet, configura o IIS em um servidor enquanto usa outro servidor que tenha sido configurado como origem da senha da conta Kerberos.

Ao usar o cmdlet **Set-CsKerberosAccountPassword** para definir uma senha, o Kerberos define a senha para uma cadeia de caracteres gerada de forma aleatória. Este cmdlet contata todas as instâncias do IIS em todos os sites centrais do Lync Server 2013 aos quais essa conta é atribuída.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Para definir uma senha para uma conta de autenticação Kerberos

1.  Faça logon em qualquer computador do domínio com o Shell de gerenciamento do Lync Server instalado como um membro do grupo RTCUniversalServerAdmins.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Na linha de comando, execute os dois comandos a seguir:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Por exemplo:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Você deve especificar o parâmetro UserAccount usando o formato Domínio\Usuário. O formato Usuário@Domínio.extensão não é compatível para referenciar os objetos computador criados para fins de autenticação Kerberos.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Após fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar o <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

