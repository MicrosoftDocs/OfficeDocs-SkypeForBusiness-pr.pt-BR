---
title: 'Lync Server 2013: Configurando largura de banda de vídeo'
description: 'Lync Server 2013: Configurando largura de banda de vídeo.'
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
ms.openlocfilehash: 85fedbe2fb856696236e79c3bbcece34d5af4a34
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550667"
---
# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Configurando largura de banda de vídeo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

O Lync Server 2013 inclui várias configurações para o gerenciamento de vídeo para chamadas de duas partes e conferências com vários participantes. Ao implantar o Lync Server 2013, você deve avaliar se as configurações padrão são apropriadas para sua organização e modificá-las conforme necessário.

Os parâmetros descritos nesta seção se aplicam tanto a conferências de dois grupos quanto de vários grupos. Visualize ou modifique tais configurações utilizando um dos cmdlets a seguir:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Verifique as configurações a seguir na sua política de conferência:

  - **VideoBitRateKb**     Essa configuração especifica a taxa máxima de bits de vídeo em kilobits por segundo (Kbps) usada para o vídeo enviado por um usuário. O valor padrão é 50000 kbps. Valores válidos vão de 0 a 50000.
    
    Essa configuração aplica-se separadamente a um vídeo principal e vídeo panorâmico.
    
    Exemplo: se você especificar 2000 Kbps, o Lync Server pode enviar 2000 kbps para o fluxo de vídeo principal e 2000 kbps para o fluxo de vídeo panorâmico.
    
    <div>
    

    > [!NOTE]  
    > A largura de banda de rede de vídeo máxima para um ponto de extremidade do Lync 2013 é de 8000 kbps para o vídeo principal e 2500 kbps para o vídeo panorâmico. Esses valores máximos são alcançados apenas se vários vídeos são recebidos ou enviados. Para obter detalhes, consulte a seção "uso da rede de tráfego de mídia" em <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisitos de largura de banda de rede para tráfego de mídia no Lync Server 2013</A>. Essa seção lista a largura de banda máxima e típica para fluxo de vídeo para todas as resoluções suportadas.

    
    </div>

  - **TotalReceiveVideoBitRateKb**     Essa configuração, que é nova no Lync Server 2013, especifica a taxa de bits máxima permitida (em kilobits por segundo) para todos os fluxos de vídeo recebidos por um cliente. Isto é, especifica o total combinado para todos os fluxos de vídeo, exceto fluxos de vídeo panorâmico, que o cliente pode receber. Por exemplo, se você especificar 1500 kbps, então um cliente poderá receber até 1500 kbps de vídeo, o que pode consistir de vários fluxos de vídeo ou um único fluxo. Essa configuração se aplica somente aos clientes do Lync Server 2013.
    
    O valor padrão para **TotalReceiveVideoBitRateKb** é 50000 kbps. Se a configuração **EnableMultiviewJoin** para o Modo de exibiçãod e Galeria estiver definido como Verdadeiro, **TotalReceiveVideoBitRateKb** não deverá ser definido em menos de 420 kbps. Se a configuração **EnableMultiviewJoin** para o Modo de exibição de Galeria for definido como Falso, **TotalReceiveVideoBitRateKb** não deverá ser definido para menos de 100 kbps. Se **EnableMultiviewJoin** estiver definido como Verdadeiro e você define o valor para abaixo de 420 kbps, os valores se tornarão padrão para o valor limite. Esse limiar ajuda a evitar uma desconfiguração acidental que pode resultar de uma experiência de usuário pobre.
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre a configuração do <STRONG>EnableMultiviewJoin</STRONG> , consulte <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.

    
    </div>

  - **MaxVideoConferencingResolution**     Este parâmetro não é mais usado para clientes do Lync Server 2013 no Lync Server 2013 conferências. As conferências do Lync Server 2013 usam os controles de taxa de bits descritos anteriormente nesta seção. Essa configuração ainda é usada para clientes herdados que participam de uma conferência do Lync Server 2013. Esse parâmetro determina a resolução máxima permitida para clientes herdados em conferências organizadas por usuários hospedados no Lync Server 2013. Ou seja, os clientes herdados são tratados da mesma forma que estavam em versões anteriores do Lync Server ou do Office Communications Server.

In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:

  - **Get-CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **New-CsMediaConfiguration**

Verify the following setting:

  - **MaxVideoRateAllowed**     Essa configuração por pool especifica a taxa máxima em que os sinais de vídeo serão transferidos nos pontos de extremidade do cliente. Aplica-se apenas às versões anteriores dos clientes do Lync Server.
    
    <div>
    

    > [!NOTE]  
    > Os clientes do Lync Server 2013 ignoram essa configuração e usam a configuração TotalReceiveVideoBitRateKb na política de conferência.

    
    </div>
    
    The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.
    
    Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.

Os procedimentos a seguir são exemplos de como usar o Shell de gerenciamento do Lync Server para modificar as configurações descritas nesta seção.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>To modify conferencing policy for video settings

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  At the command line, run the following cmdlet to edit conferencing policy:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>To modify media configuration for legacy clients

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  At the command line, run the following cmdlet to edit the media configuration:
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

