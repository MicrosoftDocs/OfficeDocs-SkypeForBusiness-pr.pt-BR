---
title: 'Lync Server 2013: Políticas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3998bd6f879b20b1a22f46818a22f26bbb2cc29a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a>Políticas de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

*As políticas de voz* do Lync Server definem os seguintes itens para cada usuário, site ou organização ao qual a política está atribuída:

  - Um conjunto de recursos de chamada que pode ser habilitado ou desabilitado para determinar a funcionalidade Enterprise Voice disponível para os usuários.

  - Um conjunto de registros de uso de PSTN (Rede Telefônica Pública Comutada) que define quais tipos de chamadas são autorizadas.

<div>

## <a name="planning-for-voice-policies"></a>Planejando políticas de voz

As etapas a seguir ajudarão você a planejar as políticas de voz necessárias para a implantação do Enterprise Voice:

  - Determine como você configurará sua política de voz global (a política de voz padrão instalada com o produto). Essa política será aplicada a todos os usuários do Enterprise Voice que não tiverem atribuído explicitamente uma política no nível do site ou por usuário.

  - Identifique as políticas de voz em nível de local das quais você possa precisar.

  - Identifique as políticas de voz por usuário que você possa precisar.

  - Decida quais recursos de chamada serão habilitados para cada política de voz.

  - Determine quais registros de uso de PSTN configurar para cada política de voz.

<div>

## <a name="voice-policy-scope"></a>Escopo da política de voz

O *escopo da política de voz* determina o nível hierárquico no qual a política pode ser aplicada. No Lync Server, você pode configurar políticas de voz com os níveis de escopo a seguir (listados da mais específica para a mais geral).

  - A **política de voz de usuário** pode ser atribuída a usuários individuais, grupos ou objetos de contato. Essa á política de nível mais baixo. As políticas de voz de usuário podem ser implantadas para habilitar recursos para determinados usuários ou grupos em um local, mas não para outros no mesmo local. Por exemplo, talvez você queira desabilitar a discagem de longa distância para alguns funcionários. Para a finalidade de atribuição de uma política de voz, um objeto de contato será tratado como um usuário individual.
    
    <div>
    

    > [!NOTE]  
    > Recomendamos que você implante uma política de voz de usuário para os usuários de site de filial da empresa que estão registrados com a implantação de site central ou com os usuários que estão registrados em um aparelho de ramificação sobreviventes.

    
    </div>

  - A **política de voz de local** é aplicada a todo o local, exceto para quaisquer usuários, grupos ou objetos de contato que recebam uma política de voz de usuário. Para definir uma política de voz de local, você precisa especificar o local ao qual a política será aplicada. Se uma política de voz de usuário não tiver sido atribuída, a política de voz de local será usada.

  - A **política de voz global** é a política de voz padrão, instalada com o produto. É possível editar a política de voz global para atender às necessidades específicas de sua organização, mas não é possível renomeá-la ou excluí-la. Esta política de voz aplica-se a todos os usuários do Enterprise Voice, grupos e objetos de contato na sua implantação, a menos que você configure e atribua uma política de voz com um escopo mais específico. Se você quiser desabilitar totalmente essa política, certifique-se de que todos os locais e usuários tenham políticas personalizadas atribuídas a eles.

</div>

<div>

## <a name="call-features"></a>Recursos de chamada

É possível habilitar ou desabilitar os recursos de chamada a seguir para cada política de voz:

  - O **encaminhamento de chamadas** permite que os usuários encaminhem chamadas para outros telefones e dispositivos cliente. Habilitado por padrão.

  - A **delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. Habilitado por padrão.

  - A **transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.

  - O **estacionamento de chamada** permite que os usuários estacionem chamadas e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.

  - O **toque simultâneo** permite que as chamadas de entrada toquem em um telefone adicional (por exemplo, um celular) ou outros dispositivos do ponto de extremidade. Habilitado por padrão.

  - A **chamada de equipe** permite que os usuários de uma equipe definida atendam às chamadas de outros membros da equipe. Habilitado por padrão.

  - O **redirecionamento de PSTN** permite que as chamadas feitas pelos usuários que receberam essa política para outros usuários corporativos sejam redirecionadas na PSTN (Rede Telefônica Pública Comutada) se a WAN estiver congestionada ou indisponível. Habilitado por padrão.

  - A **substituição da política de largura de banda** permite que os administradores substituam as decisões da política de controle de admissão de chamadas de um usuário específico. Desabilitada por padrão.

  - O **rastreamento de chamadas maliciosas** permite que os usuários relatem chamadas mal-intencionadas usando o cliente do Lync e, em seguida, sinalizam tais chamadas nos registros de detalhes da chamada. Desabilitado por padrão.

  - O **wscape do correio de voz** impede que as chamadas sejam encaminhadas imediatamente para o sistema de correio de voz do celular do usuário quando a chamada simultânea está configurada e o telefone está desligado, sem bateria ou fora de área, tendo por base um valor de temporizador. Essa configuração habilita e desabilita o temporizador e define o valor dele. Ele pode ser configurado somente usando o Shell de gerenciamento do Lync Server. Desabilitado por padrão.

  - O **encaminhamento de chamadas e o uso simultâneo do toque da PSTN** permitem que os administradores especifiquem o mesmo uso de PSTN da política de voz para encaminhamento de chamadas e toque simultâneo, restrinja o encaminhamento de chamadas e o toque simultâneo somente para usuários do Lync internos ou especifique um uso de PSTN personalizado diferente do uso PSTN da política de voz. O padrão é usar a PSTN da mesma forma que a política de voz para encaminhamento de chamadas e toque simultâneo.

</div>

<div>

## <a name="pstn-usage-records"></a>Registros de uso de PSTN

Cada política de voz deve ter um ou mais registros de uso de PSTN associados. Os usos de PSTN podem ser associados a uma política de voz somente para toque simultâneo e encaminhamento de chamadas. Para obter detalhes sobre o planejamento de registros de uso PSTN, consulte [registros de uso PSTN no Lync Server 2013](lync-server-2013-pstn-usage-records.md).

<div>


> [!NOTE]  
> A ordem de uso de PSTN é fundamental, pois, o se comparar usuários a rotas, a funcionalidade de roteamento de saída compara as utilizações de PSTN do início ao fim. Se o primeiro uso corresponder à rota da chamada, essa rota será usada. Caso contrário, a funcionalidade de roteamento de saída analisará o próximo uso de PSTN na lista e continuará até que uma correspondência seja encontrada. Na verdade, os usos de PSTN subsequentes fornecerão backup se o primeiro da lista não estiver disponível.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

