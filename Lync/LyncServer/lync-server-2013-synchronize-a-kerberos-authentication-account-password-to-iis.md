---
title: Sincronizar uma senha de conta de autenticação Kerberos com o IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc56da26961caaad236857c88d601676e12cefc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Sincronizar uma senha de conta de autenticação Kerberos com o IIS no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2010-11-08_

Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins.

Em um site, os servidores de front-end, os servidores de edição padrão e os directors podem usar uma conta de autenticação Kerberos para fins de autenticação de solicitações para o serviço de serviços Web. Esse procedimento localiza cada servidor que executa serviços Web em um site que tenha sido atribuído a uma conta Kerberos e atualiza as configurações de configuração dos serviços de informações da Internet (IIS) para usar a conta Kerberos. Para obter detalhes, consulte [definir uma senha da conta de autenticação Kerberos em um servidor no Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Para definir e configurar uma senha da conta de autenticação Kerberos

1.  Faça logon em um computador de origem (por exemplo, fe01.contoso.com) como membro do grupo RTCUniversalServerAdmins.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Na linha de comando do Shell de gerenciamento do Lync Server, execute os dois comandos a seguir:
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Por exemplo:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > O nome do computador de origem e do computador de destino deve ser um nome de domínio totalmente qualificado (FQDN) do servidor. Você não pode usar o FQDN do pool, a menos que o nome do pool seja igual ao nome do computador que você está usando como computador de origem ou de destino.

    
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

