---
title: Sincronizar uma senha de conta de autenticação Kerberos com o IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811134697ea04f1dab3637e648ff89455fca07d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Sincronizar uma senha de conta de autenticação Kerberos com o IIS no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2010-11-08_

Para concluir com sucesso este procedimento, você deve ter feito logon como usuário membro do grupo RTCUniversalServerAdmins.

Em um site, servidores front-end, servidores Standard Edition e diretores podem usar uma conta de autenticação Kerberos para fins de autenticação de solicitações para o serviço de serviços Web. Este procedimento localiza cada servidor que executa os serviços Web em um site que tenha sido atribuído a uma conta Kerberos e atualiza as definições de configuração do IIS (serviços de informações da Internet) para usar a conta Kerberos. Para obter detalhes, consulte [definir uma senha de conta de autenticação Kerberos em um servidor no Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Para definir e configurar uma senha de autenticação de conta Kerberos

1.  Conecte-se a um computador de origem (como um fe01.contoso.com) como membro do grupo RTCUniversalServerAdmins.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Na linha de comando do Shell de gerenciamento do Lync Server, execute os dois comandos a seguir:
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Por exemplo:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > O nome do computador de origem e do computador de desinto deve ser um nome de domínio Totalmente qualificado (FQDN) do servidor. Você não pode usar o FQDN do pool, a não ser que o nome do pool seja o mesmo do nome do computador sendo usado como computador de origem ou de destino.

    
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

