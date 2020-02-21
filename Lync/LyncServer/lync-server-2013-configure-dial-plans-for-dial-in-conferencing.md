---
title: 'Lync Server 2013: configurar planos de discagem para conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a86bf3061c714089ee326a729d0dd43ef267b8e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Configurar planos de discagem para conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-25_

Quando você implanta a conferência discada, precisa criar ou modificar um ou mais planos de discagem para o roteamento de números de telefone de acesso de discagem. Verifique se pelo menos uma regra de normalização em cada plano de discagem converte ramais telefônicos em números de telefone completos no formato E.164. Os usuários da conferência discada ingressam em conferências como usuários corporativos autenticados, digitando seu PIN (número de identificação pessoal) e seu número de telefone. Você precisa de uma regra de normalização para converter ramais em números de telefone completos, de forma que os usuários possam ser autenticados ao inserir somente um ramal telefônico.

Para configurar planos de discagem para conferência discada, execute o seguinte procedimento:

  - Quer você implante ou não o Enterprise Voice, modifique o plano de discagem global para adicionar uma região de conferência discada e para garantir que uma regra de normalização converta precisamente seus números de acesso de discagem. Para obter instruções detalhadas, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Se você não implantou o Enterprise Voice, crie planos de discagem para seus números de acesso de conferência discada. Certifique-se de incluir uma região de conferência discada. Para obter instruções detalhadas, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Se você implantou o Enterprise Voice, modifique os planos de discagem do Enterprise Voice conforme necessário para incluir regiões e usar regras de normalização apropriadas para números de acesso de discagem. Para obter instruções detalhadas, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). Você também pode criar planos de discagem dedicados, usados somente para números de acesso de discagem. Para obter instruções detalhadas, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Para obter detalhes sobre as regiões de planejamento, confira [requisitos de conferência discada no Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) na documentação de planejamento.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Exibir informações do plano de discagem no Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

