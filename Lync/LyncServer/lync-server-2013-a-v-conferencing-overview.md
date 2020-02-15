---
title: Lync Server 2013 visão geral de conferência A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd73e1356e42aca8dc4159143287371dd66f0688
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Visão geral da Conferência A/V no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-13_

A conferência A/V permite comunicações de áudio de vídeo em tempo real entre seus usuários. Ao implantar a conferência, você pode escolher habilitar e usar a Webconferência e a conferência A/V, ou apenas a Webconferência.

Para planejar a conferência A/V, você precisa saber a largura de banda de rede necessária para o tipo de mídia de conferência que sua organização requer. Isso pode incluir áudio, vídeo e vídeo panorâmico.

Antes de habilitar os usuários para conferência A/V, verifique se a rede pode lidar com a carga resultante. Sem largura de banda de rede suficiente, a experiência do usuário pode ser seriamente degradada. Você pode usar o CAC (controle de admissão de chamadas) para gerenciar a largura de banda da rede usada por conferência A/V. Isso é importante para redes restritas, como links limitados de largura de banda entre os sites central e de filial. Para obter detalhes, consulte [Overview of Call Admission Control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Para obter detalhes sobre os requisitos de largura de banda de mídia, consulte [requisitos de largura de banda de rede para tráfego de mídia no Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Se você implantar uma conferência de áudio na sua rede, os usuários precisarão de dispositivos de áudio, como fones de ouvido, para participar em uma conferência de áudio. Se você implantar conferência de vídeo, será necessário implantar dispositivos de vídeo, como webcams, para os usuários. Recomendamos que você use dispositivos UC (comunicações unificadas) certificados pela Microsoft para todos os tipos de dispositivos, para garantir uma experiência ideal para o usuário. Para obter detalhes sobre dispositivos certificados para UC, consulte "telefones e dispositivos para Lync" [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)em. Para dispositivos de áudio e vídeo, a implantação de vídeo e treinamento do usuário são etapas importantes a serem consideradas e planejadas.

As seções a seguir descrevem os recursos para conferência de áudio e vídeo, incluindo informações sobre gerenciamento de largura de banda e seleção de clientes apropriados.

<div>

## <a name="audio-conferencing-features"></a>Recursos de conferência de áudio

O Lync Server 2013 fornece vários recursos que você pode usar para configurar a experiência de conferência de áudio para o usuário, incluindo o seguinte:

  - **Tirar o áudio sem som**   o apresentador pode usar essa configuração para desativar todos os participantes de áudio na conferência e colocar a conferência em um estado em que os não-presenteres não podem desativar o mudo.

  - **Comunicados de entrada/saída de conferência**   se você habilitou a conferência discada, os apresentadores podem usar essa configuração para ativar ou desativar anúncios de entrada e saída para minimizar distrações enquanto uma conferência estiver em andamento.

  - **Adicionar um usuário discando**   os apresentadores e participantes que receberam permissão, pode adicionar números PSTN às conferências e fazer com que a conferência disque para esses números.

</div>

<div>

## <a name="video-conferencing-features"></a>Recursos de videoconferência

O Lync Server 2013 fornece vários recursos que você pode usar para configurar a experiência de conferência de vídeo do usuário, incluindo o seguinte:

  - **Modo de exibição**   de galeria em conferências de vídeo com mais de duas pessoas, os usuários veem automaticamente todos na conferência. Se a conferência tiver mais que cinco participantes, o vídeo dos participantes mais ativos serão exibidos na linha superior e apenas a foto dos outros participantes será exibida. O vídeo de vários participantes está ativado como padrão. Para obter detalhes sobre como configurar ou desativar o vídeo com vários participantes, confira [Configurando a largura de banda de vídeo no Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Vídeo panorâmico se**   um dispositivo de conferência de vídeo redonda estiver instalado na sala de conferência, este recurso fornece uma visão de 360 graus de tamanho completo da sala de conferência. A faixa de vídeo panorâmico está disponível apenas em dispositivos de mesa redonda.

  - **Apresentador somente modo**   de vídeo os apresentadores podem configurar a reunião para que apenas o vídeo do apresentador seja mostrado. Isso evita distrações em reuniões grandes, quando várias transmissões de vídeo estão disponíveis e travadas para diferentes fontes. Esse modo também é aplicado ao vídeo capturado e fornecido por dispositivos de mesa redonda.

  - ****   Os usuários de vídeo HD podem experimentar resoluções de até HD 1080p em chamadas de duas partes e conferências com vários participantes.

  - ****   Os apresentadores de Spotlight de vídeo podem configurar a reunião para que apenas o vídeo de um participante selecionado que é uma fonte de vídeo seja visto pelos outros participantes da conferência. Esse modo também se aplica ao vídeo capturado e fornecido pelos dispositivos de mesa redonda de vídeo panorâmico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

