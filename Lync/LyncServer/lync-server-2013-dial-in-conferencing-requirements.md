---
title: Requisitos de conferência discada do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Requisitos de conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-30_

Antes de iniciar o processo de implantação do Lync Server 2013, você precisa planejar o seguinte:

  - A configuração a ser usada para se conectar à rede telefônica pública comutada (PSTN)

  - Sua estratégia para atribuir regiões de conferência discada para números de acesso discado

  - Sua estratégia para a criação de diretórios de conferência

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>Planejando a conectividade de PSTN discada

A conferência discada requer pelo menos um servidor de mediação e pelo menos um gateway PSTN.

Você pode implantar um Servidor de Mediação em um site central ou em um site de filial. No site central, você pode colocar um Servidor de Mediação em um Pool de Front-Ends ou servidor Standard Edition, ou pode implantá-lo em um servidor ou pool autônomo. Em um site de filial, você pode implantar um Servidor de Mediação em um servidor autônomo ou como um componente do Aparelho de Filial Persistente.

Você pode implantar um gateway PSTN em um site central ou em um site de filial. Em um site de filial, o gateway PSTN pode ser autônomo ou um componente do Aparelho de Filial Persistente.

<div>


> [!NOTE]  
> A conferência discada não usa o bypass de mídia porque o/V Conferência Server não é compatível com o bypass de mídia.



</div>

Para obter detalhes sobre como planejar a configuração do servidor de mediação e dos gateways PSTN para conferência discada, consulte [componentes e topologias do servidor de mediação no Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) na documentação de planejamento.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>Planejando regiões de conferência discada

Durante a configuração de discagem, crie planos de discagem e números de acesso de conferência discada. Os planos de discagem são conjuntos de regras de normalização que especificam o número e o padrão de dígitos em um número de telefone e convertem o número de telefone no formato padrão E. 164 para roteamento de chamadas. Números de acesso de conferência discada são os números para os quais os participantes ligam para entrar em uma conferência.

Todo número de acesso de conferência discada deve ser associado a no mínimo um plano de discagem. Regiões de conferência discada associe um número de acesso à conferência discada com seus planos de discagem. Ao configurar um plano de discagem, especifique a região de conferência discada que se aplica ao plano de discagem. Ao criar o número de acesso de discagem, selecione as regiões que associam o número de acesso aos planos de discagem apropriados.

Quando você cria um plano de discagem, especifica o escopo do plano de discagem: escopo do usuário, escopo do pool ou escopo do site. Todo usuário é atribuído ao plano de discagem do escopo mais estreito que se aplicar a ele. Por exemplo, um usuário é atribuído a um plano de discagem de nível de usuário, caso um se aplique. Se um plano de discagem de nível de usuário não se aplicar, o usuário é atribuído a um plano de discagem de nível de pool. Se um plano de discagem de nível de pool não se aplicar, o usuário é atribuído a um plano de discagem de nível de site. Se um plano de discagem de nível de site não se aplicar, o usuário é atribuído ao plano de discagem global.

Antes de configurar os planos de discagem, é importante planejar como você deseja nomear e usar regiões. As considerações a seguir aplicam-se a regiões de conferência discada:

  - Uma região normalmente é uma área geográfica associada a um escritório ou grupo de escritórios.

  - Idiomas são associados a números de acesso de discagem. Se você oferecer suporte a áreas geográficas que possuam vários idiomas, deve decidir como deseja definir regiões para oferecer suporte a vários idiomas. Por exemplo, você pode definir várias regiões com base em uma combinação de geografia e idioma ou pode definir uma única região com base em geografia e ter diferentes números de acesso de discagem para cada idioma.

  - Quando um usuário agenda uma reunião, por padrão a reunião usa a região especificada pelo plano de discagem do usuário.

  - Por padrão, todos os números de acesso discada da região estão incluídos no convite da reunião.

  - É importante nomear regiões para que sejam claramente reconhecíveis. O usuário pode usar estes nomes das regiões para alterar a região de uma reunião, para que diferentes números de acesso sejam incluídos no convite. (Quando os usuários usam o Outlook para agendar uma reunião, o usuário usa o suplemento de reunião online para o Lync 2013 para alterar a região).

  - Regiões devem ser criadas para que qualquer convidado que deseje discar para uma conferência possa ver um número de acesso local no convite da conferência.

  - Você pode configurar a ordem em que os números de acesso dentro de uma região aparecem na página de configurações da conferência discada (e, portanto, a ordem em que aparecem no convite de conferência) usando cmdlets do Shell de gerenciamento do Lync Server.

  - Qualquer usuário de qualquer localização pode ligar para qualquer número de acesso de discagem para entrar em uma conferência.

</div>

<div>

## <a name="planning-for-conference-directories"></a>Planejando pastas de conferência

As pastas de conferência mantêm um mapeamento entre a ID de reunião alfanumérica que um participante usa para ingressar em uma conferência ao usar o Lync 2013 e a ID de conferência somente numérico que um participante de conferência discada usa para participar da conferência. O formato do ID de conferência é como segue:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Criar vários diretórios de conferência garantirá que os IDs de conferência sejam curtos até que uma quantidade significativa de conferências seja criada. Em uma organização com um número comum de conferências por usuário, recomendamos criar um diretório de conferência para cada 999 usuários no pool. Usando esta diretriz, as IDs de conferência geralmente podem ser mantidas pequenas. No entanto, assim que o número de diretórios de conferência (em todos os pools) ultrapassar 9, o número do ID de conferência aumentará para suportar conferências adicionais.

</div>

<div>

## <a name="see-also"></a>Confira também


[Componente servidor de mediação no Lync Server 2013](lync-server-2013-mediation-server-component.md)  
[Planos de discagem e regras de normalização no Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

