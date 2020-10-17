---
title: 'Lync Server 2013: Habilitando o monitoramento'
description: 'Lync Server 2013: Habilitando o monitoramento.'
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
ms.openlocfilehash: d8995042bdc9b121dc5253940104bb167567ddcc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558477"
---
# <a name="enabling-monitoring-in-lync-server-2013"></a>Habilitando o monitoramento no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-17_

Embora os agentes de coleta de dados unificados sejam instalados e ativados automaticamente em cada servidor de front-end, isso não significa que você começará automaticamente a coletar dados de monitoramento no momento em que concluir a instalação do Microsoft Lync Server 2013. Ao invés disso, você deve fazer duas coisas: associar seus pools de servidores de Front-End/servidores de Front-end com um banco de dados de monitoramento e deve habilitar o registro de detalhes da chamada (CDR) e/ou monitoramento da Qualidade de Experiência (QoE) no escopo global e/ou local.

Para obter instruções passo a passo sobre como associar servidores front-end ou pools de front-ends a um banco de dados de monitoramento, consulte o tópico [associando um repositório de monitoramento a um pool de front-ends no Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) no guia de implantação. Após estas associações serem realizadas e após sua nova topologia do Lync Server ter sido publicada, você ainda não poderá coletar dados de monitoramento. Isso ocorre porque, por padrão, a coleta de dados de CDR e QoE é desabilitada quando você instala o Lync Server 2013.

Para poder começar a coletar dados necessários habilite o CDR e/ou monitoramento QoE. (Observe que você não precisa habilitar o monitoramento de CDR e QoE; se preferir, é possível habilitar um tipo de monitoramento enquanto deixa o outro tipo desabilitado.) Para habilitar o monitoramento de CDR no escopo global, execute o seguinte comando no Shell de gerenciamento do Lync Server:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Como alternativa, você pode habilitar o monitoramento de CDR no painel de controle do Lync Server 2013. No painel de controle do Lync Server, conclua o procedimento a seguir:

1.  Clique em **Monitoramento**.

2.  Na guia **Registro de Detalhes da Chamada**, clique duas vezes na configuração **Global**.

3.  No painel **Editar configuração do registro de detalhe da chamada (CDR)**, selecione **Habilitar monitoramento de CDRs** e clique em **Confirmar**.

Para habilitar o monitoramento de QoE no escopo global, execute este comando no Shell de gerenciamento do Lync Server:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Se preferir, você também pode habilitar o monitoramento de QoE no painel de controle do Lync Server. No Painel de Controle, conclua o seguinte procedimento:

1.  Clique em **Monitoramento**.

2.  Na guia **Dados da Qualidade da Experiência**, clique duas vezes na configuração **Global**.

3.  No painel **Editar configuração da Qualidade da Experiência (QoE)**, selecione **Habilitar monitoramento de dados QoE** e clique em **Confirmar**.

Como observado, os exemplos anteriores habilitam o monitoramento no escopo global; isto é, eles habilitam o monitoramento CDR e QoE através da sua organização. Em alternativa, é possível criar definições de configurações CDR e QoE separadas no escopo local e habilitar ou desabilitar seletivamente o monitoramento de cada local. Por exemplo, é possível habilitar o monitoramento CDR para seu local Redmond, desabilitar o monitoramento CDR para Dublin. Para obter mais informações sobre como gerenciar suas definições de configuração de monitoramento, consulte o tópico Deployment Guide [Configuring Call Detail Recording and Quality of Experience Settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

</div>

<span> </span>

</div>

</div>

</div>

