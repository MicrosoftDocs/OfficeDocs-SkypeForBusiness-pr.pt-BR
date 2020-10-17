---
title: 'Lync Server 2013: rotas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0f457fc96981927ea2b6cb4d4177488dc3f5231
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535488"
---
# <a name="voice-routes-in-lync-server-2013"></a>Rotas de voz no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

As rotas de chamada especificam como o Lync Server trata as chamadas de saída feitas por usuários do Enterprise Voice. Quando um usuário disca um número, o servidor front-end normaliza a cadeia de caracteres de discagem para o formato E. 164, se necessário, e tenta fazer a correspondência com um URI de SIP. Se o servidor não conseguir fazer a correspondência, aplicará a lógica de encaminhamento de chamadas realizadas com base no número. A etapa final na definição dessa lógica é a criação de uma rota de chamada nomeada separada para cada conjunto de números de telefone listados em cada plano de discagem.

Antes de definir as rotas de chamadas de saída, você deve concluir as seguintes etapas:

  - Implantar um ou mais troncos.

  - Criar planos de discagem conforme a necessidade para sites, indivíduos e objetos de Contato.

  - Criar registros de uso de rede telefônica pública comutada (PSTN).

Além disso, para habilitar o roteamento de chamadas de saída, você deve criar e atribuir uma ou mais políticas de voz. Você pode fazer isso antes ou depois de definir as rotas das chamadas de saída.

Para cada rota, você deve especificar:

  - Um nome pelo qual a rota possa ser facilmente identificada.

  - Uma descrição opcional, caso apenas o nome não seja suficiente para descrevê-la.

  - O padrão de correspondência da expressão regular que identifica os números de telefone de destino aos quais a rota será aplicada, junto com as exceções às quais o padrão de correspondência não será aplicado.

  - Um ou mais troncos que você desejar atribuir à rota.

  - Os registros de uso do PSTN que os usuários devem ter para fazer chamadas para números que correspondam à expressão regular do número de telefone de destino.

Você pode especificar rotas de chamadas no painel de controle do Lync Server. Essas rotas de chamadas preenchem a tabela de roteamento do servidor, que o Lync Server usa para rotear chamadas destinadas à PSTN.

<div>

## <a name="mn-trunk-support"></a>Suporte de Tronco M:N

O Lync Server oferece flexibilidade em como as chamadas são encaminhadas para o PSTN. Uma rota de voz especifica um conjunto de troncos ao PSTN que pode ser usado para uma chamada de voz específica. Um tronco associa um servidor de mediação e um número de porta com um gateway PSTN e um número de porta de escuta. Essa associação lógica permite que um servidor de mediação seja associado a vários gateways e tenha várias conexões com o mesmo gateway. Ao definir uma rota de chamada, você especifica os troncos associados a essa rota, mas não especifica quais servidores de mediação estão associados à rota. Para criar troncos definindo as relações entre os servidores de mediação e os gateways PSTN, IP-PBXs e SBCs (controladores de borda de sessão), use o construtor de topologias.

</div>

<div>

## <a name="least-cost-routing"></a>Roteamento de Custo Mínimo

A capacidade de especificar os troncos para os quais os diversos números são roteados permite determinar as rotas de menor custo e implementá-las adequadamente. A regra geral para selecionar troncos é escolher o tronco com o gateway mais próximo da localidade do número de destino para reduzir as tarifas de interurbano. Por exemplo, caso você esteja em Nova York telefonando para um número em Roma, a chamada seguiria pela rede IP até o tronco com o gateway no escritório de Roma e os custos seriam os de uma chamada local.

Para um exemplo de como o roteamento de custo mínimo poderia ser usado, considere o seguinte: a Fabrikam decide permitir que os usuários alemães façam chamadas para os números dos EUA usando o tronco norte-americano. A Fabrikam também deseja configurar o sistema para que todas as chamadas de usuários do Lync Server dos EUA para a Alemanha e países/regiões adjacentes terminem no tronco com o gateway na Alemanha. Este roteamento economizará dinheiro porque uma chamada da Alemanha para a Áustria, por exemplo, é mais barata do que uma chamada dos EUA para a Áustria.

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>Como traduzir cadeias de caracteres de discagem de saída

O Lync Server 2013, como seus predecessores imediatos, exige que todas as cadeias de caracteres de discagem sejam normalizadas para o formato E. 164 para o propósito de executar a pesquisa de número reverso (RNL). Para troncos com gateways ou PBXs (Private Branch eXchanges) que exigem números convertidos em formatos de discagem locais, o Lync Server 2013 permite que você crie uma ou mais regras que auxiliam na manipulação do número chamado (ou seja, URI de solicitação) antes de roteá-lo ao tronco. Por exemplo, você pode escrever uma regra para remover +44 do início da cadeia de caracteres de discagem e subsituí-lo por 0144.

Com o Lync Server 2013, é possível criar uma ou mais regras que auxiliam na manipulação do número de chamada antes de encaminhá-lo ao tronco.

Ao planejar seus troncos que associam gateways: pares de porta com servidor de mediação: pares de porta, pode ser útil agrupar troncos com requisitos de discagem locais semelhantes e, portanto, reduzir o número de regras de conversão necessárias e o tempo necessário para escrevê-las.

</div>

<div>

## <a name="configuring-caller-id"></a>Como configurar o ID de chamador

O Lync Server oferece uma maneira de manipular a ID de chamada para chamadas de saída. Por exemplo, se uma organização deseja mascarar as extensões de discagem direta dos funcionários e substituí-las com o número genérico corporativo ou departamental, um administrador pode fazer isso usando o painel de controle do Lync Server para suprimir a ID de chamadas e substituí-la por uma ID de chamador alternativa especificada. Ao planejar a lógica do seu roteamento, considere para quais indivíduos, grupos e sites você deseja essa opção - talvez, mesmo, para todos os funcionários.

<div>


> [!NOTE]  
> Para chamadas que são roteadas novamente através do PSTN, o ID de chamador genérico será apresentado em vez do ID de chamador original. Isso pode fazer com que a chamada ignore configurações de Não Incomodar ou de privacidade que o receptor possa ter configurado.



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>Lógica de roteamento adicional

Ao criar rotas de chamadas de saída, você deve estar ciente dos seguintes fatores que podem afetar a lógica de roteamento:

  - Onde uma chamada passa por uma fronteira federada, a parte do domínio do URI é usada para rotear a chamada até a empresa responsável por aplicar a lógica de roteamento de saída.

  - Se a parte do domínio do URI de solicitação não contiver um domínio suportado para a empresa, o componente de roteamento de saída no servidor não processa a chamada.

  - Se um usuário não estiver habilitado para o Enterprise Voice, o servidor aplicará outra lógica de roteamento, conforme apropriado.

  - Se uma chamada for roteada para um gateway que está completamente ocupado (todas as linhas do tronco estão ocupadas), o gateway rejeita a chamada e a lógica de roteamento de saída a redireciona para a próxima rota de menor custo. Considere isso cuidadosamente, porque um gateway dimensionado para um escritório pequeno no exterior (por exemplo, em Zurique) pode na verdade carregar um volume significativo de tráfego não-local para chamadas internacionais para a Suíça. Se o gateway não for dimensionado corretamente para esse tráfego adicional, as chamadas para a Suíça poderão ser roteadas por um gateway na Alemanha, resultando em tarifas maiores.

</div>

</div>

<span> </span>

</div>

</div>

</div>

