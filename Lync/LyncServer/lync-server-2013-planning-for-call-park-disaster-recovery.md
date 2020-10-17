---
title: 'Lync Server 2013: planejamento para recuperação de desastre de estacionamento de chamadas'
description: 'Lync Server 2013: planejamento para recuperação de desastre de estacionamento de chamada.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1d05503f1d8c30f4dd4446a995442d5e2500dbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554277"
---
# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Planejamento para recuperação de desastre de estacionamento de chamadas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-30_

Esta seção descreve algumas maneiras de preparar o aplicativo de estacionamento de chamada para recuperação de desastres e algumas considerações para o processo de recuperação de desastres.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>Preparando para recuperação de desastre de estacionamento de chamada

Considere o seguinte ao preparar e realizar os procedimentos de recuperação de desastres:

  - Planeje a recuperação de desastres ao realizar o planejamento de capacidade. Para a capacidade de recuperação de desastres, cada pool em um pool emparelhado deve ser capaz de lidar com as cargas de trabalho dos serviços de estacionamento de chamadas nos dois pools. Para obter detalhes sobre o planejamento de capacidade de estacionamento de chamada, consulte [Capacity Planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o serviço Estacionamento de Chamada executado no pool de backup. Portanto, o suporte para estacionamento de chamadas durante a recuperação de desastres exige que o aplicativo de estacionamento de chamada seja implantado e habilitado no pool primário e no pool de backup.

  - Cada pool deve ter um intervalo válido de números de órbita para ser utilizado pelos usuários hospedados no pool a fim de estacionar chamadas.

  - Mantenha sempre uma cópia de backup separada de qualquer música personalizada em espera que tenha sido carregada para estacionamento de chamada. Não é feito backup desses arquivos como parte do processo de recuperação de desastres do Lync Server 2013 e serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>Considerações de recuperação de desastre de estacionamento de chamada

Você pode definir apenas um conjunto de definições de configuração do aplicativo de estacionamento de chamada e um arquivo de áudio de música em espera personalizado por pool. Essas configurações incluem o tempo limite máximo, a música em espera, o número máximo de tentativas de recebimento de chamadas e o tempo limite de URI. Para exibir essas configurações, execute o cmdlet **Get-CsCpsConfiguration**. Para obter detalhes sobre o cmdlet **Get-CsCpsConfiguration** , consulte [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).

Durante a recuperação de desastre, o estacionamento de chamadas usa o aplicativo de estacionamento de chamada no pool de backup, de modo que não seja feito backup das configurações do pool principal. Se o pool primário não puder ser recuperado e você implantar um novo pool para substituir o pool principal, as configurações do pool primário serão perdidas e você precisará reconfigurar as configurações de estacionamento de chamada e qualquer arquivo de áudio de música em espera personalizado no novo pool.

Se você implantar um novo pool com um FQDN (nome de domínio totalmente qualificado) diferente para substituir o pool primário, precisará reatribuir todos os intervalos de órbita de estacionamento de chamada que foram associados ao pool primário ao FQDN do novo pool. Para reatribuir intervalos de órbita ao novo pool, você pode usar o painel de controle do Lync Server ou o cmdlet **set-CsCallParkOrbit** . Para obter detalhes sobre o cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

</div>

<span> </span>

</div>

</div>

</div>

