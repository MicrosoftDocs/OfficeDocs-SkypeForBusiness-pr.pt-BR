---
title: Gerenciando as definições de configuração do serviço de registro em log centralizado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c6e156fbae7147b650c7360394cbd0d277b937b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Gerenciando as definições de configuração do serviço de registro em log centralizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O serviço de registro em log centralizado é controlado e configurado por configurações e parâmetros que são criados e usados pelo CLSController (controlador de serviço de registro em log centralizado) para enviar comandos ao agente de serviço de registro em log centralizado do computador individual (CLSAgent). O agente processa os comandos enviados a ele e (no caso de um comando Iniciar) usa a configuração dos cenários, provedores, tamanho de log, duração de rastreamento e sinalizadores para começar a coletar logs de rastreamento de acordo com as informações de configuração fornecidas.

<div>


> [!IMPORTANT]
> Nem todos os cmdlets do Windows PowerShell listados para o serviço de registro em log centralizado devem ser usados com as implantações locais do Lync Server 2013. Embora eles possam parecer funcionar, os cmdlets a seguir não foram projetados para funcionar com as implantações locais do Lync Server 2013: 
> <UL>
> <LI>
> <P><STRONG>Cmdlets CsClsRegion:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A> e <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</P>
> <LI>
> <P><STRONG>Cmdlets CsClsSearchTerm:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> e <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</P>
> <LI>
> <P><STRONG>Cmdlets CsClsSecurityGroup:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A> e <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</P></LI></UL>As configurações definidas nesses cmdlets não afetarão nem causarão qualquer comportamento adverso, mas serão projetadas para uso com o Microsoft 365 e não produzirão os resultados esperados em implantações locais. Isso não quer dizer que não há uso para esses cmdlets em implantações locais, mas sua utilização é um tópico mais avançado que não é abordado nesta documentação.


</div>

<div>

## <a name="in-this-section"></a>Nesta seção

Os tópicos nesta seção definem as opções de configuração, parâmetros e configurações para o serviço de registro em log centralizado. Informações sobre como configurar o serviço de registro em log centralizado, como recuperar as definições de configuração, a criação de cenários, o gerenciamento de grupos de segurança para o serviço de registro em log centralizado, a pesquisa e mais estão contidos nos tópicos a seguir.

  - [Gerenciando o computador, o site e o serviço de registro em log global centralizado no Lync Server 2013](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Configurando provedores para o serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Configurando cenários para o serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Visão geral do serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Cmdlets de registro centralizado no Lync Server 2013](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

