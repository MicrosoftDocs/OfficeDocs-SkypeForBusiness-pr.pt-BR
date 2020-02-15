---
title: Configurando políticas de voz, registros de uso de PSTN e rotas de voz
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fc69514b425c6a619a0edcd349a8b8733eca369
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a>Configurando políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-10_

Políticas de voz, registros de uso PSTN e rotas de voz estão totalmente relacionados. Configure as políticas de voz selecionando um conjunto de recursos de chamada e, em seguida, atribuindo à política um conjunto de registros de uso da PSTN, que especificam quais direitos serão autorizados para os usuários ou grupos aos quais foi atribuída a política de voz. As rotas de voz também recebem registros de uso da PSTN, que servem para corresponder as rotas aos usuários que têm autorização para usá-las. Isto é, os usuários podem somente fazer chamadas que utilizem as rotas para as quais exista um registro de uso da PSTN correspondente.

O fluxo de trabalho recomendado para uma nova implantação Enterprise Voice é de começar configurando uma política de voz que inclua os registros de uso PSTN adequados e, então, associar as rotas apropriadas à cada registro de uso PSTN.

<div>


> [!NOTE]
> Você também pode criar políticas de voz com escopo de <EM>usuário</EM> e atribuí-las a grupos ou usuários individuais.



</div>

Para as etapas detalhas para realizar cada uma destas tarefas, consulte os procedimentos nesta seção.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando políticas de voz e registros de uso de PSTN para autorizar recursos e privilégios de chamada no Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [Exibir registros de uso de PSTN no Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)

  - [Configurando rotas de voz para chamadas de saída no Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [Exportando e importando a configuração de roteamento de voz no Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

