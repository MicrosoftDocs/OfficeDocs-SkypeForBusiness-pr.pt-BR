---
title: Visão geral da Conferência A/V do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d477a8423e7e5ee57e54d0bde584edeb02db4608
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Visão geral da Conferência A/V no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-13_

A conferência A/V permite comunicações de áudio e vídeo em tempo real entre seus usuários. Ao implantar uma conferência, você pode optar por habilitar e usar conferências via Web e conferência A/V ou apenas conferências na Web.

Para planejar a conferência A/V, você precisa saber a largura de banda de rede necessária para o tipo de mídia de conferência que sua organização requer. Isso pode incluir áudio, vídeo e vídeo panorâmico.

Antes de habilitar usuários para conferência A/V, verifique se sua rede pode manipular a carga resultante. Sem largura de banda suficiente, a experiência do usuário pode ser gravemente prejudicada. Você pode usar o controle de admissão de chamadas (CAC) para gerenciar a largura de banda de rede usada por uma conferência A/V. Isso é importante para redes restritas, como links limitados de largura de banda entre sites centrais e filiais. Para obter detalhes, consulte [visão geral do controle de admissão de chamadas no Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Para obter detalhes sobre requisitos de largura de banda de mídia, consulte [requisitos de largura de banda de rede para tráfego de mídia no Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Se você implantar uma conferência de áudio na sua rede, os usuários precisarão de dispositivos de áudio, como fones de ouvido, para participar de uma conferência. Se você implantar conferência de vídeo, precisará implantar dispositivos de vídeo, como webcams para usuários. Recomendamos que você use dispositivos de comunicação unificada (UC) certificados pela Microsoft para todos os tipos de dispositivos, para garantir uma experiência de usuário ideal. Para obter detalhes sobre dispositivos certificados pela UC, consulte "telefones e dispositivos para Lync" [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)em. Para dispositivos de áudio ou de vídeo, a implantação de dispositivos e o treinamento do usuário são etapas importantes para você considerar e planejar.

As seções a seguir descrevem os recursos de videoconferência e videoconferência, incluindo informações sobre o gerenciamento de largura de banda e a seleção dos clientes adequados.

<div>

## <a name="audio-conferencing-features"></a>Recursos de conferência de áudio

O Lync Server 2013 fornece vários recursos que você pode usar para configurar a experiência de audioconferência para o usuário, incluindo o seguinte:

  - **Desativar mudo**   o apresentador pode usar essa configuração para ativar o mudo de todos os participantes de áudio na conferência e colocar a conferência em um estado em que os não-apresentadores não podem desativar o mudo.

  - **Comunicados de entrada/saída de conferência**   se você tiver habilitado a conferência discada, os apresentadores poderão usar essa configuração para ativar ou desativar anúncios de entrada e saída para minimizar distrações enquanto uma conferência estiver em andamento.

  - **Adicionar um usuário discando**   os apresentadores e os participantes que receberam permissão, pode adicionar números PSTN às conferências e fazer com que a conferência disque para esses números.

</div>

<div>

## <a name="video-conferencing-features"></a>Recursos de videoconferência

O Lync Server 2013 fornece vários recursos que você pode usar para configurar a experiência de videoconferência para o usuário, incluindo o seguinte:

  - **Modo de exibição**   de galeria em videoconferências com mais de duas pessoas, os usuários visualizam automaticamente todas as pessoas na conferência. Se a conferência tiver mais de cinco participantes, o vídeo dos participantes mais ativos serão exibidos na linha superior e apenas a foto dos outros participantes será exibida. O vídeo de vários participantes está ativado como padrão. Para obter detalhes sobre como configurar ou desativar o vídeo de vários participantes, consulte Configurando a [largura de banda do vídeo no Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Vídeo panorâmico se**   um dispositivo de videoconferência da mesa redonda estiver instalado na sala de conferência, esse recurso fornecerá uma exibição de nível 360 completa da sala de conferência. A faixa de vídeo panorâmico está disponível apenas com dispositivos RoundTable.

  - **Apresentador somente**   os apresentadores do modo de vídeo podem configurar a reunião para que somente o vídeo do apresentador seja mostrado. Isso evita distrações em reuniões grandes, quando várias transmissões de vídeo estão disponíveis e bloqueadas para diferentes fontes. Esse modo também se aplica ao vídeo capturado e fornecido por dispositivos RoundTable.

  - ****   Os usuários de vídeo HD podem ter resoluções de até HD 1080p em chamadas de dois participantes e em conferências de vários participantes.

  - ****   Apresentadores de destaque de vídeo podem configurar a reunião para que somente o vídeo de um participante selecionado que é uma fonte de vídeo seja visto pelos outros participantes da conferência. Esse modo também se aplica ao vídeo capturado e fornecido pelos dispositivos RoundTable para vídeo panorâmico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

