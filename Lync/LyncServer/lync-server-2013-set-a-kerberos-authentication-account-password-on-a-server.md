---
title: 'Lync Server 2013: Configurar uma senha da conta de autenticação Kerberos authentication em um servidor'
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
ms.openlocfilehash: 97130b93052c0e14e1e4b4863be8ceea6118db05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Configurar uma senha da conta de autenticação Kerberos authentication em um servidor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-01-16_

Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins.

Você deve configurar uma senha na conta Kerberos para cada site que tenha servidores front-end, servidores de edição padrão e directors. Você pode configurar a senha executando o cmdlet **set-CsKerberosAccountPassword** do Windows PowerShell em um servidor no site (por exemplo, um servidor front-end). Para cada site, você deve executar o cmdlet **set-CsKerberosAccountPassword** . O cmdlet configura o IIS (serviços de informações da Internet) para o serviço de serviços Web e define a senha na conta do computador nos serviços de domínio do Active Directory. Um método alternativo, com base em qual parâmetro é usado com o cmdlet, configura o IIS em um servidor enquanto usa outro servidor que tenha sido configurado como a origem da senha da conta Kerberos.

Quando você usa o cmdlet **set-CsKerberosAccountPassword** para definir uma senha, o Kerberos define a senha como uma cadeia de caracteres gerada aleatoriamente. Este cmdlet entra em contato com todas as instâncias do IIS em todos os sites centrais do Lync Server 2013 aos quais essa conta foi atribuída.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Para definir uma senha para uma conta de autenticação Kerberos

1.  Faça logon em qualquer computador do domínio com o Shell de gerenciamento do Lync Server instalado como membro do grupo RTCUniversalServerAdmins.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Na linha de comando, execute os dois comandos a seguir:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Por exemplo:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Você deve especificar o parâmetro USERACCOUNT usando o formato domínio \ usuário. Não há suporte para o formato de extensão User@Domain. para fazer referência aos objetos de computador criados para fins de autenticação Kerberos.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Depois de fazer qualquer alteração na autenticação Kerberos, como adicionar uma conta ou remover uma conta, você deve executar <STRONG>Enable-CsTopology</STRONG> no prompt de comando do Shell de gerenciamento do Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

