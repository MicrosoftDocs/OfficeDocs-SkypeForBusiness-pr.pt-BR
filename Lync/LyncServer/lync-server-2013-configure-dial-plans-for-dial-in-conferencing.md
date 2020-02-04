---
title: 'Lync Server 2013: Configurar planos de discagem para conferência discada'
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
ms.openlocfilehash: 544c431257dea20db729e80dd1d9acc565da8201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Configurar planos de discagem para conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-25_

Ao implantar a conferência discada, você precisa criar ou modificar um ou mais planos de discagem para o roteamento de números de telefone de acesso de discagem. Certifique-se de que pelo menos uma regra de normalização em cada plano de discagem converte ramais de telefone em números de telefone completos no formato E. 164. Os usuários da conferência discada participam de conferências como usuários corporativos autenticados, digitando seu número de identificação pessoal (PIN) e seu número de telefone. Você precisa de uma regra de normalização para converter ramais em números de telefone completos, de forma que os usuários possam ser autenticados ao inserir somente um ramal telefônico.

Para configurar planos de discagem para conferência discada, faça o seguinte:

  - Independente de implantar o Enterprise Voice, modifique o plano de discagem global para adicionar uma região de conferência discada e para garantir que uma regra de normalização converta seus números de acesso discado de modo preciso. Para obter instruções detalhadas, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Se você não implantou o Enterprise Voice, crie planos de discagem para todos os seus números de acesso de conferência discada. Certifique-se de incluir uma região de conferência discada. Para obter instruções detalhadas, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Se você implantou o Enterprise Voice, modifique os planos de discagem do Enterprise Voice conforme necessário para incluir regiões e usar regras de normalização apropriadas para números de acesso de discagem. Para obter instruções detalhadas, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). Você também pode criar planos de discagem dedicados, usados somente para números de acesso de discagem. Para obter instruções detalhadas, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Para obter detalhes sobre regiões de planejamento, consulte [requisitos de conferência discada no Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) na documentação de planejamento.

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

