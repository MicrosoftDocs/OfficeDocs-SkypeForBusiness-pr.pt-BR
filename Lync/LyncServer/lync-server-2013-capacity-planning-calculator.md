---
title: Calculadora de planejamento de capacidade do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 230b731bf7b63a1ce86b5652d9e3d3b2956c94a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512818"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>Usando a calculadora de planejamento de capacidade para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-21_

A calculadora de planejamento de capacidade do Microsoft® Lync™ Server 2013 está disponível para download em <https://www.microsoft.com/download/details.aspx?id=36828> . Ele foi projetado para ajudá-lo a determinar os requisitos de servidor com base em números de usuários e modalidades de comunicação habilitados em sua organização. Você insere o perfil da sua organização e a calculadora fornece recomendações que ajudam você a planejar sua topologia.

As recomendações criadas pela calculadora são apenas para fins de planejamento. A simulação de carga real é necessária para garantir que o Lync Server 2013 seja adequadamente provisionado. Para realizar testes de estresse sob uma carga simulada, use a [ferramenta de estresse e desempenho do Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=282724).

Depois de determinar o perfil do usuário e as modalidades que você deseja habilitar para os usuários, é hora de usar a calculadora para planejar o número de servidores, memória e largura de banda de que você precisa. Esta versão da calculadora não fornece orientações para os requisitos de e/s de disco.

Esta calculadora complementa o [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) e o [Microsoft Lync Server](lync-server-2013-planning.md). Use a calculadora após revisar o guia e criar uma topologia recomendada usando a ferramenta de planejamento.

Você pode aproveitar a maior parte da calculadora se tiver informações precisas e detalhadas sobre seu perfil de usuário específico. Por exemplo, a porcentagem de usuários habilitados para voz, média de chamadas por usuário por hora, duração da chamada e a porcentagem de usuários simultâneos em conferências podem fazer uma grande diferença nos requisitos do servidor. A precisão das recomendações criadas pela calculadora depende da precisão das informações que você fornece.

<div>

## <a name="using-the-capacity-calculator"></a>Usando a calculadora de capacidade

A calculadora é uma planilha do Microsoft Excel®. As células coloridas de laranja são para entrada. Os valores padrão são inseridos (80.000 usuários em um pool com doze servidores front-end), mas você pode alterar esses valores de acordo com as necessidades da sua organização.

O modelo de uso contém as seções a seguir. Para calcular os requisitos de capacidade, insira os dados descritos:

**Mensagens instantâneas e presença**

  - Em número de usuários, digite o número de usuários que serão conectados simultaneamente. Esse número geralmente é de 80% do número total de usuários provisionados. Na maioria das situações, 100% de seus usuários simultâneos serão habilitados para IM e presença. O padrão é 80.000.

  - Número médio de contatos na lista de contatos indica o número de contatos que estamos usando para validar os requisitos do sistema. Esse número não é alterado.

**Enterprise Voice**

  - Em usuários habilitados para o Enterprise Voice, digite a porcentagem de seus usuários que estão habilitados para o Enterprise Voice. O padrão é 60%.

  - Em número médio de chamadas por usuário por hora (pico), digite o número de chamadas por hora que você espera que o usuário médio participe durante horários de carga de pico. O padrão é 4.

  - Em porcentagem de chamadas que usam bypass de mídia, digite a porcentagem de chamadas feitas por seus usuários que irão ignorar o servidor de mediação. O padrão é 65%.

  - Em porcentagem de usuários de voz envolvidos nas chamadas UC-PSTN, digite a porcentagem das chamadas da sua organização que são chamadas telefônicas UC-PSTN. O padrão é 60%

  - Em percentual de usuários de voz envolvidos nas chamadas UC-UC mostra a porcentagem de usuários que estão habilitados para o Enterprise Voice que serão habilitados apenas para as chamadas UC-UC. Esse número é calculado com base no que você insere para porcentagem de usuários de voz habilitados para chamadas UC-PSTN.

**Conferências**

  - Em porcentagem de usuários em conferências simultâneas, digite a porcentagem de usuários que participarão simultaneamente em conferências. O padrão é 5%.

  - Em porcentagem de conferências com somente IM de grupo (sem voz), digite a porcentagem de conferências cujas conferências envolverão apenas mensagens instantâneas; Isto é, que não incluem um componente de áudio. O padrão é 10%

  - Em porcentagem de usuários que usam conferência discada, digite a porcentagem de participantes simultâneos em conferências que usarão a conferência discada. O padrão é 15%.

  - Em porcentagem de conferências usando voz, digite a porcentagem de conferências que incluirão um componente de áudio.
    
      - Se 20% de suas conferências de voz também incluirem vídeo normal, marque a caixa de seleção incluindo vídeo (sem exibição múltipla).
    
      - Se 20% de suas conferências também incluir vídeo de várias exibições, marque a caixa de seleção incluir vários modos de exibição.
    
      - Se 50% de suas conferências de voz também incluem compartilhamento de aplicativo, marque a caixa de seleção incluir compartilhamento de aplicativo.
    
      - Se 20% de suas conferências de voz incluírem carregamentos de dados, como apresentações do Microsoft PowerPoint®, marque a caixa de seleção incluir webconferências.

**Mobilidade**

  - Em porcentagem de usuários habilitados para mobilidade, digite a porcentagem de seus usuários que serão habilitados para se conectarem ao Lync Server usando dispositivos móveis. O padrão é 40%.

Quando você inserir todas as informações necessárias, a calculadora de capacidade estimará suas necessidades. As células amarelas mostram valores calculados para requisitos de CPU, memória e largura de banda com base nos testes executados nos laboratórios de desempenho do Lync Server 2013. Os números são fornecidos como uma diretriz, nem cada única variação é testada e validada. Os seguintes valores são calculados:

  - CPU de front end: porcentagem de uso da CPU se a carga inteira estava sendo manipulada por um servidor front-end das mesmas especificações que o servidor usado no teste da Microsoft.

  - Rede em Mbps: requisitos de largura de banda em megabits por segundo (Mbps) para a carga de trabalho correspondente.

  - Memória em GB: memória necessária em gigabytes (GB) para a carga de trabalho correspondente.

As células verdes mostram recomendações para o modelo de uso inserido.

  - Total de servidores front-end: o número de servidores físicos exigidos baseia-se em servidores dedicados que executam o Lync Server 2013 com processador duplo, um núcleo-Core, com 2.260 megaciclos.

  - Observe que a habilitação do hyperthreading é recomendada e comprovada para melhorar o desempenho de servidores que oferecem suporte a áudio/vídeo.

  - Servidores de borda: o número de servidores de borda necessários, com base em 30% de todos os usuários simultâneos que estão se comunicando por meio dos servidores de borda. Essa porcentagem não pode ser alterada na calculadora.

  - Repositório de serviços de arquivamento/registro de detalhes de chamada/qualidade da experiência: o número de repositórios necessários para recursos de arquivamento ou monitoramento, se eles estiverem habilitados em sua organização.

  - Servidor de banco de dados back-end necessário (pools necessários): o número de servidores de banco de dados back-end necessários para suportar a carga de trabalho selecionada.

Além disso, na linha ao lado de total dos servidores front-end, mais informações são fornecidas sobre a carga nos servidores e na rede para todas as cargas de trabalho planejadas combinadas.

  - Carga média da CPU: o uso médio da CPU por servidor de front-end.

  - Rede em Mbps: a alocação de largura de banda necessária para suportar o modelo de uso inserido.

  - Memória em GB: memória, em gigabytes, necessária para cada servidor de front-end.

</div>

<div>

## <a name="adjusting-for-your-processors"></a>Ajustando para seus processadores

Todos os valores de uso da CPU na planilha presumem que cada servidor tenha um processador duplo, um núcleo hex com 2,26 GHz, pelo menos 32 GB de memória, e 8 ou mais unidades de disco rígido de 10.000-RPM com pelo menos 72 GB de espaço livre em disco.

Se seus servidores tiverem processadores diferentes, você poderá ajustar os números para que correspondam ao seu hardware.

</div>

</div>

<span> </span>

</div>

</div>

</div>

