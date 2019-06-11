---
title: Mover objetos de contato da Unificação de mensagens do Exchange
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Mover objetos de contato da Unificação de mensagens do Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Para migrar os objetos de contato do atendedor automático (AA) e do usuário (SA) para a nova implantação do Lync Server 2013, primeiro mova os objetos da implantação herdada do Office Communications Server 2007 R2 para a nova implantação do Lync Server 2013 usando o ** Cmdlets Get-CsExUmContact** e **move-CsExUmContact** . No servidor Exchange, você executa o script **ExchUCUtil** do Windows PowerShell para fazer o seguinte para o pool do Lync recém implantado:

  - Adicione-o aos gateways IP de Unificação de mensagens.

  - Adicione-o aos grupos coletivos de Unificação de mensagens.

<div>


> [!NOTE]  
> Para usar os cmdlets <STRONG>Get-CsExUmContact</STRONG> e <STRONG>move-CsExUmContact</STRONG> , você deve ser membro do grupo RTCUniversalUserAdmins e ter permissão de unidade organizacional (OU) para a UO em que os objetos de contatos estão armazenados. É possível conceder permissão de OU ao usar o cmdlet <STRONG>Grant-OUPermission</STRONG> .



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Para mover objetos de contato usando o Shell de gerenciamento do Lync Server

1.  Abra o Shell de gerenciamento do Lync Server.

2.  Para cada pool registrado no Exchange UM (onde pool1.contoso.net é um pool da implantação do Office Communications Server 2007 R2 e pool2.contoso.net é o pool da implantação do Lync Server 2013) na linha de comando, digite o seguinte:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Para verificar se os objetos de contato foram movidos, execute o cmdlet **Get-CsExumContact** e confirme se **RegistrarPool** agora está apontando para o novo pool.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Para executar o script do Windows PowerShell ExchUCUtil

1.  Faça logon no servidor Exchange UM como usuário com privilégios de administrador da organização do Exchange.

2.  Navegue até o script ExchUCUtil do Windows PowerShell.
    
    No Exchange 2007, ExchUCUtil. ps1 está localizado em: **% arquivos de programas\\%\\Microsoft Exchange\\Server\\scripts ExchUCUtil. ps1**
    
    No Exchange 2010, ExchUCUtil. ps1 está localizado em: **% arquivos de programas\\%\\Microsoft Exchange\\Server\\v14\\scripts ExchUCUtil. ps1**

3.  Se o Exchange estiver implantado em uma única floresta, digite:
    
        exchucutil.ps1
    
    Ou, se o Exchange estiver implantado em várias florestas, digite:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    em que floresta FQDN especifica a floresta na qual o Lync Server 2013 é implantado.
    
    <div>
    

    > [!IMPORTANT]  
    > Certifique-se de reiniciar o serviço de <STRONG>front-end do Lync Server</STRONG> (RtcSrv. exe) <EM>depois</EM> de executar ExchUCUtil. ps1. Caso contrário, o Lync Server 2013 não irá detectar a Unificação de mensagens na topologia.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

