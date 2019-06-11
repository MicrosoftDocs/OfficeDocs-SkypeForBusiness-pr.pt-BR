---
title: 'Lync Server 2013: Planejamento para recuperação de desastre de Estacionamento de Chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7da940f55574e1c6d50aeb06c0c80710bdbaad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Planejamento para recuperação de desastre de Estacionamento de Chamada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-30_

Esta seção descreve algumas maneiras de preparar o aplicativo parque de chamadas para a recuperação de desastres e algumas considerações para o processo de recuperação de desastres.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>Preparando-se para a recuperação de desastre do parque da chamada

Lembre-se do seguinte ao se preparar e executar procedimentos de recuperação de desastres.

  - Planeje a recuperação de desastres quando você fizer o planejamento da capacidade. Para a capacidade de recuperação de desastres, cada pool em um pool emparelhado deve ser capaz de manipular as cargas de trabalho dos serviços de estacionamento de chamadas em ambos os pools. Para obter detalhes sobre o planejamento da capacidade do parque de chamadas, consulte [planejamento de capacidade para estacionamento de chamadas no Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o serviço de estacionamento de chamadas executado no pool de backup. Portanto, o suporte para o parque da chamada durante a recuperação de desastres exige que o aplicativo parque de chamadas seja implantado e habilitado no pool primário e no pool de backup.

  - Cada pool deve ter um intervalo válido de números órbitas para usuários que são hospedados nesse pool para usar para chamadas de estacionamento.

  - Mantenha sempre uma cópia de backup separada de qualquer música personalizada em espera que tenha sido carregada para o parque de chamadas. Esses arquivos não são submetidos a backup como parte do processo de recuperação de desastres do Lync Server 2013 e serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>Considerações sobre a recuperação de desastre do parque

Você pode definir apenas um conjunto de configurações de aplicativo de estacionamento de chamada e um arquivo de áudio de música em espera personalizado por pool. Essas configurações incluem o limite de tempo limite, música em espera, tentativas máximas de recebimento de chamada e URI de tempo limite. Para exibir essas definições de configuração, execute o cmdlet **Get-CsCpsConfiguration** . Para obter detalhes sobre o cmdlet **Get-CsCpsConfiguration** , consulte [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).

Durante a recuperação de desastres, o parque de chamadas usa o aplicativo parque de chamadas no pool de backup, portanto, as configurações do pool primário não são incluídas no backup. Se o pool primário não puder ser recuperado e você implantar um novo pool para substituir o pool primário, as configurações do pool primário serão perdidas, e você precisará reconfigurar as configurações do estacionamento de chamadas e todos os arquivos de áudio de música em espera personalizados no novo pool.

Se você implantar um novo pool com um nome de domínio totalmente qualificado (FQDN) diferente para substituir o pool primário, será necessário reatribuir todos os intervalos órbitas do parque de chamadas que foram associados ao pool primário ao FQDN do novo pool. Para reatribuir intervalos de órbita ao novo pool, você pode usar o painel de controle do Lync Server ou o cmdlet **set-CsCallParkOrbit** . Para obter detalhes sobre o cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

</div>

<span> </span>

</div>

</div>

</div>

