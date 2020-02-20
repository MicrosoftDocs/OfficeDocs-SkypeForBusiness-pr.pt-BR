---
title: Requisitos de conferência discada do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dcdf30ac0fc35f470e74991b2127cd81b05c5c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Requisitos de conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-30_

Antes de iniciar o processo de implantação do Lync Server 2013, você precisa planejar o seguinte:

  - A configuração a ser usada para se conectar à rede telefônica pública comutada (PSTN)

  - Sua estratégia para atribuir regiões de conferência discada a números de acesso de discagem

  - Sua estratégia para criar diretórios de conferência

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>Planejando a conectividade PSTN de discagem

A conferência discada requer pelo menos um servidor de mediação e pelo menos um gateway PSTN.

Você pode implantar um servidor de mediação em um site central ou em um site de filial. Em um site central, você pode colocar um servidor de mediação em um pool de front-ends ou servidor Standard Edition, ou pode implantá-lo em um servidor ou pool autônomo. Em um site de filial, você pode implantar um servidor de mediação em um servidor autônomo ou como um componente do aparelho de filial persistente.

Você pode implantar um gateway PSTN em um site central ou em um site de filial. Em um site de filial, o gateway PSTN pode ser autônomo ou um componente do aparelho de filial persistente.

<div>


> [!NOTE]  
> A conferência discada não usa o bypass de mídia porque o servidor de conferência A/V não oferece suporte A bypass de mídia.



</div>

Para obter detalhes sobre como planejar a configuração para o servidor de mediação e gateways PSTN para conferência discada, consulte [componentes e topologias para o servidor de mediação no Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) na documentação de planejamento.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>Planejamento de regiões de conferência discada

Durante a configuração de discagem, você cria planos de discagem e números de acesso de conferência discada. Os planos de discagem são conjuntos de regras de normalização que especificam o número e o padrão de dígitos em um número de telefone e convertem o número de telefone no formato E. 164 padrão para roteamento de chamadas. Os números de acesso de conferência discada são os números que os participantes chamam para ingressar em uma conferência.

Cada número de acesso de conferência discada deve ser associado a pelo menos um plano de discagem. As regiões de conferência discada associam um número de acesso de conferência discada com seus planos de discagem. Ao configurar um plano de discagem, você especifica a região de conferência discada que se aplica ao plano de discagem. Ao criar o número de acesso de discagem, selecione as regiões que associam o número de acesso aos planos de discagem apropriados.

Ao criar um plano de discagem, você especifica o escopo do plano de discagem: escopo do usuário, escopo do pool ou escopo do site. Cada usuário recebe o plano de discagem do escopo mais estreito que se aplica ao usuário. Por exemplo, um usuário recebe um plano de discagem de nível de usuário, se for aplicável. Se um plano de discagem de nível de usuário não se aplicar, o usuário receberá um plano de discagem de nível de pool. Se um plano de discagem de nível de pool não se aplicar, o usuário receberá um plano de discagem de nível de site. Se um plano de discagem no nível do site não se aplicar, será atribuído ao usuário o plano de discagem global.

Antes de configurar os planos de discagem, é importante planejar como você deseja nomear e usar regiões. As seguintes considerações se aplicam às regiões de conferência discada:

  - Uma região normalmente é uma área geográfica associada a um escritório ou grupo de escritórios.

  - Os idiomas são associados aos números de acesso de discagem. Se você oferecer suporte a áreas geográficas com vários idiomas, deverá decidir como deseja definir regiões para dar suporte a vários idiomas. Por exemplo, você pode definir várias regiões com base em uma combinação de Geografia e idioma, ou você pode definir uma única região com base na geografia e ter vários números de acesso de discagem para cada idioma.

  - Quando um usuário agenda uma reunião, por padrão a reunião usa a região especificada pelo plano de discagem do usuário.

  - Por padrão, todos os números de acesso de discagem para a região são incluídos no convite da reunião.

  - É importante nomear regiões para que elas sejam claramente reconhecíveis. O usuário pode usar os nomes das regiões para alterar a região de uma reunião para que diferentes números de acesso sejam incluídos no convite. (Quando os usuários usam o Outlook para agendar uma reunião, o usuário usa o suplemento de reunião online para o Lync 2013 para alterar a região).

  - As regiões devem ser criadas para que qualquer convidado que deseje discar para uma conferência possa ver um número de acesso local no convite da conferência.

  - Você pode configurar a ordem na qual os números de acesso dentro de uma região aparecem na página Configurações de conferência discada (e, portanto, a ordem em que aparecem no convite de conferência) usando os cmdlets do Shell de gerenciamento do Lync Server.

  - Qualquer usuário de qualquer local pode chamar qualquer número de acesso de discagem para ingressar em uma conferência.

</div>

<div>

## <a name="planning-for-conference-directories"></a>Planejamento de diretórios de conferência

Os diretórios de conferência mantêm um mapeamento entre a ID de reunião alfanumérica que um participante usa para ingressar em uma conferência ao usar o Lync 2013 e a ID de conferência somente numérica que um participante de conferência discada usa para ingressar na conferência. O formato da ID de conferência é o seguinte:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

A criação de vários diretórios de conferência garantirá que as IDs de conferência permaneçam curtas até que uma quantidade significativa de conferências tenha sido criada. Em uma organização com um número típico de conferências por usuário, recomendamos que você crie um diretório de conferência para cada 999 usuários no pool. Usando essa diretriz, as IDs de conferência geralmente podem ser mantidas pequenas. No entanto, depois que o número de diretórios de conferência (em todos os pools) ultrapassar 9, o número de ID da conferência aumentará para suportar conferências adicionais.

</div>

<div>

## <a name="see-also"></a>Confira também


[Componente do servidor de mediação no Lync Server 2013](lync-server-2013-mediation-server-component.md)  
[Planos de discagem e regras de normalização no Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

