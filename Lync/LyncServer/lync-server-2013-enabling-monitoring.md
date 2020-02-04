---
title: 'Lync Server 2013: Habilitando o monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f11aab3c58a43ac0746cb1f297bf4f3f85d28c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a>Habilitando o monitoramento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-17_

Embora os agentes de coleta de dados unificados sejam automaticamente instalados e ativados em cada servidor front-end, isso não significa que você começará a coletar dados de monitoramento automaticamente no momento em que você terminar de instalar o Microsoft Lync Server 2013. Em vez disso, você deve fazer duas coisas: você deve associar seus servidores de front-end/pools front-end a um banco de dados de monitoramento e deve habilitar a monitoração de detalhes de chamadas (CDR) e/ou Quality of Experience (QoE) no escopo global e/ou no escopo do site.

Para obter instruções passo a passo sobre como associar servidores de front-end ou pools de front-end a um banco de dados de monitoramento, consulte o tópico [associando um repositório de monitoramento a um pool de front-end no Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) no guia de implantação. Depois que essas associações tiverem sido feitas e após a publicação da nova topologia do Lync Server, você ainda não poderá coletar os dados de monitoramento. Isso ocorre porque, por padrão, a coleta de dados CDR e QoE é desativada quando você instala o Lync Server 2013.

Para começar a coleta de dados, você precisará habilitar o CDR e/ou o monitoramento QoE. (Observe que você não precisa habilitar o monitoramento de CDR e QoE; se preferir, você pode habilitar um tipo de monitoramento enquanto deixa o outro tipo desabilitado.) Para habilitar o monitoramento de CDR no escopo global, execute o seguinte comando no Shell de gerenciamento do Lync Server:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Você também pode habilitar o monitoramento de CDR no painel de controle do Lync Server 2013. No painel de controle do Lync Server, conclua o seguinte procedimento:

1.  Clique em **Monitoramento**.

2.  Na guia **Registro de Detalhes das Chamadas**, clique duas vezes na configuração **Global**.

3.  No painel **Editar configuração do registro de detalhes das chamadas (CDR)**, selecione **Habilitar monitoramento de CDRs** e clique em **Confirmar**.

Para habilitar o monitoramento de QoE no escopo global, execute este comando dentro do Shell de gerenciamento do Lync Server:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Se preferir, você também pode habilitar o monitoramento de QoE no painel de controle do Lync Server. No Painel de Controle, execute o seguinte procedimento:

1.  Clique em **Monitoramento**.

2.  Na guia **Dados da Qualidade da Experiência**, clique duas vezes na configuração **Global**.

3.  No painel **Editar configuração da Qualidade da Experiência (QoE)**, selecione **Habilitar monitoramento de dados QoE** e clique em **Confirmar**.

Como observado, os exemplos precedentes habilitam o monitoramento no escopo global; isto é, eles habilitam o monitoramento CDR e QoE em toda a sua organização. Como alternativa, é possível criar definições de configurações CDR e QoE separadas no escopo local e habilitar ou desabilitar seletivamente o monitoramento de cada local. Por exemplo, é possível habilitar o monitoramento CDR para seu local Redmond e desabilitar o monitoramento CDR para Dublin. Para obter mais informações sobre como gerenciar suas configurações de monitoramento de configuração, consulte o tópico do guia de implantação [Configurando a gravação de detalhes da chamada e as configurações de qualidade de experiência no Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

</div>

<span> </span>

</div>

</div>

</div>

