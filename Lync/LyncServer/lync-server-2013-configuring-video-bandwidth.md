---
title: 'Lync Server 2013: Configurando a largura de banda do vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cca8df1ea3c4c2458851da24ab8b39dbbab2d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Configurando a largura de banda do vídeo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

O Lync Server 2013 inclui várias configurações para o gerenciamento de vídeo para chamadas de dois participantes e conferências de vários participantes. Ao implantar o Lync Server 2013, você deve avaliar se as configurações padrão são adequadas para sua organização e modificá-las conforme necessário.

Os parâmetros descritos nesta seção se aplicam às duas chamadas de terceiros e à conferência de vários participantes. Exiba ou modifique essas configurações usando um dos seguintes cmdlets:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Verifique as seguintes configurações na política de conferência:

  - **VideoBitRateKb**   essa configuração especifica a taxa máxima de bits de vídeo em kilobits por segundo (Kbps) usada para vídeo enviado por um usuário. O valor padrão é 50000 kbps. Os valores válidos são de 0 a 50000.
    
    Essa configuração aplica-se separadamente ao vídeo principal e ao vídeo panorâmico.
    
    Exemplo: se você especificar 2000 Kbps, o Lync Server poderá enviar 2000 kbps para o fluxo de vídeo principal e 2000 kbps para o fluxo de vídeo panorâmico.
    
    <div>
    

    > [!NOTE]  
    > O máximo de largura de banda de rede de vídeo de um ponto de extremidade do Lync 2013 é de 8000 kbps para o vídeo principal e 2500 kbps para o vídeo panorâmico. Esses valores máximos serão atingidos somente se vários vídeos forem recebidos ou enviados. Para obter detalhes, consulte a seção "uso da rede de tráfego de mídia" em <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisitos de largura de banda de rede para o tráfego de mídia no Lync Server 2013</A>. Esta seção lista a largura de banda máxima e típica de fluxo de vídeo para todas as resoluções compatíveis.

    
    </div>

  - **TotalReceiveVideoBitRateKb**   essa configuração, que é nova no Lync Server 2013, especifica a taxa de bits máxima permitida (em quilobits por segundo) para todos os fluxos de vídeo recebidos por um cliente. Ou seja, ele especifica o total combinado para todos os fluxos de vídeo, exceto fluxos de vídeo panorâmicos, que um cliente pode receber. Por exemplo, se você especificar 1500 Kbps, um cliente pode receber até 1500 kbps de vídeo, que pode consistir em vários fluxos de vídeo ou um único fluxo de vídeo. Essa configuração se aplica somente aos clientes do Lync Server 2013.
    
    O valor padrão para **TotalReceiveVideoBitRateKb** é de 50000 kbps. Se a configuração **EnableMultiviewJoin** para o modo de exibição de galeria estiver definida como true, **TotalReceiveVideoBitRateKb** não deverá ser definido abaixo de 420 kbps. Se a configuração **EnableMultiviewJoin** para o modo de exibição de galeria estiver definida como false, **TotalReceiveVideoBitRateKb** não deverá ser definido abaixo de 100 kbps. Se **EnableMultiviewJoin** for definido como true e você definir o valor abaixo de 420 Kbps, os valores serão padrão para o valor limite. Esse limite ajuda a evitar problemas de configuração acidentais que podem resultar em má experiência do usuário.
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre a configuração <STRONG>EnableMultiviewJoin</STRONG> , consulte <A href="lync-server-2013-configuring-gallery-view.md">Configurando o modo de exibição de galeria no Lync Server 2013</A>.

    
    </div>

  - **MaxVideoConferencingResolution**   este parâmetro não está mais sendo usado para clientes do Lync Server 2013 no Lync Server 2013 conferências. Conferências do Lync Server 2013 use os controles de taxa de bits descritos anteriormente nesta seção. Essa configuração ainda é usada para clientes herdados que participam de uma conferência do Lync Server 2013. Esse parâmetro determina a resolução máxima permitida para clientes herdados em conferências organizadas por usuários que são hospedados no Lync Server 2013. Ou seja, os clientes herdados são tratados da mesma forma que estavam nas versões anteriores do Lync Server ou Office Communications Server.

Além das configurações de política de conferência que se aplicam aos usuários, avalie as configurações de configuração de mídia. Exiba ou modifique essas configurações usando um dos seguintes cmdlets:

  - **Get-CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **New-CsMediaConfiguration**

Verifique a seguinte configuração:

  - **MaxVideoRateAllowed**   a configuração por pool especifica a taxa máxima em que os sinais de vídeo serão transferidos nos pontos de extremidade do cliente. Aplica-se apenas às versões anteriores dos clientes do Lync Server.
    
    <div>
    

    > [!NOTE]  
    > Os clientes do Lync Server 2013 ignoram essa configuração e usam a configuração TotalReceiveVideoBitRateKb na política de conferência em vez disso.

    
    </div>
    
    O valor padrão é HD720P. Os valores válidos são HD720p15M, VGA600K e CIF250K.
    
    Exemplo: se você especificar 1500 Kbps, todos os clientes herdados do pool poderão receber até 1500 kbps de vídeo em conferências de dois participantes ou de vários participantes.

Os procedimentos a seguir são exemplos de como usar o Shell de gerenciamento do Lync Server para modificar as configurações descritas nesta seção.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>Para modificar a política de conferência para configurações de vídeo

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Na linha de comando, execute o seguinte cmdlet para editar a política de conferência:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>Para modificar a configuração de mídia para clientes herdados

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Na linha de comando, execute o cmdlet a seguir para editar a configuração de mídia:
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

