---
title: Verificar informações de topologia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7657bb80d7acb6d48a4027c665fae70e469bb236
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>Verificar informações de topologia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-26_

A primeira etapa na verificação da mesclagem concluída com êxito é exibir as informações de topologia do Office Communications Server 2007 R2 que você mesclou com o Lync Server 2013. No construtor de topologias, o nó **BackCompatSite** exibe o nome de domínio totalmente qualificado (FQDN) de cada pool e servidor do Office Communications Server 2007 R2 que você mesclou.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>Para ver BackCompatSite no construtor de topologias

1.  No ambiente do Office Communications Server 2007 R2, abra a ferramenta administrativa do Office Communications Server 2007 R2 e anote os FQDNs dos pools e servidores herdados.

2.  No ambiente do Lync Server 2013, abra o construtor de topologias e, em seguida, expanda o nó **BackCompatSite** .

3.  Verifique se os FQDNs dos pools e servidores que você mesclaram são exibidos.
    
    <div>
    

    > [!NOTE]  
    > Você não vê nenhuma informação no <STRONG>BackCompatSite</STRONG> para funções de servidor que estão posicionadas em um servidor front-end ou servidor Standard Edition. Somente as funções de servidor que são necessárias para interoperabilidade entre o Office Communications Server 2007 R2 e o Lync Server 2013 são mostradas.

    
    </div>

![Caixa de diálogo BackCompatSite do construtor de topologia] (images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Caixa de diálogo BackCompatSite do construtor de topologia")

Você também pode usar o painel de controle do Lync Server 2013 para exibir a topologia mesclada. No painel de controle do Lync Server 2013, você pode ver cada FQDN do servidor, FQDN do pool e nome do site para a sua topologia mesclada. Os servidores mesclados têm um nome de **site** de **BackCompatSite**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Para exibir a topologia mesclada no painel de controle do Lync Server 2013

1.  Abra o painel de controle do Lync Server 2013.

2.  Clique em **topologia**.

3.  Na guia **status** , verifique se servidores e pools que você mesclou são exibidos procurando **BackCompatSite** na coluna do **site** .

![Painel de controle do Lync Server mostrando topologia mesclada] (images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Painel de controle do Lync Server mostrando topologia mesclada")

Para ver mais detalhes sobre um pool mesclado, use o cmdlet **Get-CsPool** . Além das informações que estão disponíveis no painel de controle Topology Builder e Lync Server 2013, esse cmdlet exibe os serviços executados no pool do Lync Server 2013.

<div>


> [!NOTE]  
> Quando você publica a topologia depois de executar o assistente de mesclagem no construtor de topologias, os diretórios de conferências são mesclados ao Lync Server 2013. Os diretórios de conferência podem ser verificados executando o cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> .



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>Para exibir serviços em um pool mesclado

1.  Abra o Shell de gerenciamento do Lync Server 2013.

2.  Na linha de comando, digite o seguinte:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Por exemplo:
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>Para verificar se as pastas de conferência foram mescladas

1.  Abra o Shell de gerenciamento do Lync Server 2013.

2.  Na linha de comando, digite o seguinte:
    
        Get-CsConferenceDirectory

3.  Verifique se todos os diretórios de conferência do pool ou do servidor que você está mesclando estão agora no Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

