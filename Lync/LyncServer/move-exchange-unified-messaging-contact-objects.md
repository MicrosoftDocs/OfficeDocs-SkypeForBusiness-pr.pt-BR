---
title: Mover objetos de contato de Unificação de mensagens do Exchange
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42abb209eaf59be66c8516401616dcac4f1c94ad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500288"
---
# <a name="move-exchange-unified-messaging-contact-objects"></a>Mover objetos de contato de Unificação de mensagens do Exchange

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Para migrar objetos de contato do atendedor automático (AA) e de acesso do assinante (SA) para a nova implantação do Lync Server 2013, primeiro você move os objetos da implantação herdada do Office Communications Server 2007 R2 para a nova implantação do Lync Server 2013 usando os cmdlets **Get-CsExUmContact** e **move-CsExUmContact** . No servidor do Exchange, execute o script **ExchUCUtil** do Windows PowerShell para fazer o seguinte para o pool do Lync recém implantado:

  - Adicioná-lo aos gateways IP de unificação de mensagens

  - Adicioná-lo aos grupos de busca de unificação de mensagens

<div>


> [!NOTE]  
> Para usar os cmdlets <STRONG>Get-CsExUmContact</STRONG> e <STRONG>Move-CsExUmContact</STRONG>, é preciso ser membro do grupo RTCUniversalUserAdmins e ter permissão de OU (unidade organizacional) para a OU em que os objetos de contato estão armazenados. A permissão de OU pode ser concedida usando o cmdlet <STRONG>Grant-OUPermission</STRONG>.



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Para mover objetos de contato usando o Shell de Gerenciamento do Lync Server

1.  Abra o Shell de Gerenciamento do Lync Server.

2.  Para cada pool registrado com UM do Exchange (onde pool1.contoso.net é um pool da implantação do Office Communications Server 2007 R2 e pool2.contoso.net é o pool da implantação do Lync Server 2013) na linha de comando, digite o seguinte:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Para verificar se os objetos de contato foram movidos, execute o cmdlet **Get-CsExumContact** e confirme se **RegistrarPool** indica agora o novo pool.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Para executar o script ExchUCUtil Windows PowerShell

1.  Faça logon no servidor UM do Exchange como usuário com privilégios de administrador de organização do Exchange.

2.  Navegue até o script ExchUCUtil do Windows PowerShell.
    
    No Exchange 2007, o ExchUCUtil.ps1 está localizado em: **% arquivos de programas% \\ scripts do Microsoft \\ Exchange Server \\ \\ExchUCUtil.ps1**
    
    No Exchange 2010, o ExchUCUtil.ps1 está localizado em: **% arquivos de programas% \\ scripts do Microsoft \\ Exchange Server \\ v14 \\ \\ExchUCUtil.ps1**

3.  Se o Exchange estiver implantado em uma única floresta, digite:
    
        exchucutil.ps1
    
    Se o Exchange estiver implantado em várias florestas, digite:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    onde FQDN da floresta especifica a floresta na qual o Lync Server 2013 é implantado.
    
    <div>
    

    > [!IMPORTANT]  
    > Certifique-se de reiniciar o serviço de <STRONG>Front-End do Lync Server</STRONG> (rtcsrv.exe) <EM>depois</EM> de executar exchucutil.ps1. Caso contrário, o Lync Server 2013 não detectará a Unificação de mensagens na topologia.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

