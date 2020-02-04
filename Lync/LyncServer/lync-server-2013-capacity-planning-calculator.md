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
ms.openlocfilehash: 26abf069d7c1686fe8abb804d6de4508ba6333fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>Usar a calculadora de planejamento de capacidade para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-21_

A calculadora de planejamento de capacidade do Microsoft® Lync™ Server 2013 está disponível <http://www.microsoft.com/en-us/download/details.aspx?id=36828>para download em. Ele foi projetado para ajudar você a determinar os requisitos do servidor com base em números de usuários e modalidades de comunicação habilitados em sua organização. Você insere o perfil da sua organização e a calculadora fornece recomendações que ajudam você a planejar sua topologia.

As recomendações criadas pela calculadora são somente para fins de planejamento. A simulação de carga real é necessária para garantir que o Lync Server 2013 seja provisionado de forma adequada. Para executar testes de stress em uma carga simulada, use a [ferramenta de stress e desempenho do Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=282724).

Depois de determinar seu perfil de usuário e as modalidades que você deseja habilitar para seus usuários, é hora de usar a calculadora para planejar o número de servidores, memória e largura de banda de que você precisa. Esta versão da calculadora não fornece orientação quanto às exigências de E/S do disco.

Esta calculadora complementa o [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) e o [Microsoft Lync Server](lync-server-2013-planning.md). Use a calculadora após ter revisado o guia e criado uma topologia recomendada usando a Ferramenta de Planejamento.

Você poderá aproveitar grande parte da calculadora se tiver informações precisas e detalhadas sobre seu perfil do usuário específico. Por exemplo, a porcentagem dos usuários de voz, chamadas médias por usuário e por hora, duração da chamada e porcentagem dos usuários simultâneos em conferências podem fazer uma diferença enorme nas exigências do servidor. A precisão das recomendações criadas pela calculadora depende da precisão das informações fornecidas.

<div>

## <a name="using-the-capacity-calculator"></a>Usando a capacidade da calculadora

A calculadora é uma planilha® do Microsoft Excel. As células coloridas em laranja são para entrada a partir de você. Os valores padrão são inseridos (os usuários do 80.000 em um pool com doze servidores front-end), mas você pode alterar esses valores de acordo com as necessidades da sua organização.

O modelo de uso contém as seguintes seções. Para calcular seus requisitos de capacidade, insira os dados conforme descrito:

**Mensagem instantânea e presença**

  - Em número de usuários, digite o número de usuários que entrarão simultaneamente. Esse número normalmente é 80% do número total de usuários provisionados. Na maioria das situações, 100% de seus usuários simultâneos estarão ativados para mensagens instantâneas e presença. O padrão é 80.000.

  - Número médio de contatos na lista Contatos indica o número de contatos que nós estamos usando para validar as exigências de seu sistema. Esse número não é alterado.

**Enterprise Voice**

  - Em usuários habilitados para o Enterprise Voice, digite a porcentagem dos seus usuários que estão habilitados para o Enterprise Voice. O padrão é 60%

  - Em número médio de chamadas por hora por hora (pico), digite o número de chamadas por hora em que você espera que o usuário médio participe durante horários de carga de pico. O padrão é 4.

  - Em Porcentagem de chamadas que usam o bypass de mídia, digite a porcentagem de chamadas feitas por seus usuários que ignorará o Servidor de Mediação. O padrão é 65%.

  - Em Porcentagem de usuários por voz envolvidos nas chamadas UC-PSTN, digite a porcentagem de chamadas de sua organização que são chamadas telefônicas UC-PSTN. O padrão é 60%

  - Em porcentagem de usuários de voz envolvidos nas chamadas de comunicação unificada, mostra a porcentagem de usuários que estão habilitados para o Enterprise Voice que serão habilitados somente para as chamadas UC-UC. Esse número é calculado com base no que você digita para a Porcentagem de usuários de voz ativados para as chamadas UC-PSTN.

**Conferências**

  - Em porcentagem de usuários em conferências simultâneas, digite a porcentagem de usuários que participarão de conferências de forma simultânea. O padrão é 5%.

  - Em porcentagem de conferências com apenas mensagens de chat em grupo (sem voz), digite a porcentagem de conferências das quais as conferências envolverão apenas mensagens instantâneas; ou seja, que não incluem um componente de áudio. O padrão é 10%

  - Em porcentagem de usuários usando conferência discada, digite a porcentagem de participantes simultâneos em conferências que usarão a conferência discada. O padrão é 15%.

  - Em porcentagem de conferências usando voz, digite a porcentagem de conferências que incluirão um componente de áudio.
    
      - Se 20% das conferências de voz incluírem também um vídeo normal, marque a caixa de seleção Incluir vídeo (sem Multi-View).
    
      - Se 20% de suas conferências incluírem o vídeo Multi-View, marque a caixa de seleção Incluir Multi-View.
    
      - Se 50% de suas conferências de voz incluírem o compartilhamento de aplicativos, marque a caixa de seleção Incluir compartilhamento de aplicativos.
    
      - Se 20% das suas conferências de voz incluírem carregamentos de dados, como apresentações do Microsoft PowerPoint®, marque a caixa de seleção incluir Webconferência.

**Mobilidade**

  - Em porcentagem de usuários habilitados para mobilidade, digite a porcentagem dos usuários que serão habilitadas para se conectar ao Lync Server usando dispositivos móveis. O padrão é 40%.

Quando você tiver digitado todas as informações necessárias, a calculadora de capacidade estimará as exigências. As células amarelas mostram os valores calculados para requisitos de CPU, memória e largura de banda com base nos testes executados nos laboratórios de desempenho do Lync Server 2013. Os números são fornecidos como uma diretriz e nem toda variação é testada e validada. Os seguintes valores são calculados:

  - CPU de front-end: porcentagem de uso da CPU se a carga inteira estivesse sendo manipulada por um servidor front-end das mesmas especificações do servidor usado no teste da Microsoft.

  - Rede em Mbps: as exigências da largura de banda em megabits por segundo (Mbps) para a carga de trabalho correspondente.

  - Memória em GB: a memória requerida em gigabytes (GB) para a carga de trabalho correspondente.

As células verdes mostram as recomendações para o modelo de uso inserido.

  - Total de servidores front end: o número de servidores físicos necessários é baseado em servidores dedicados que executam o Lync Server 2013 com processador duplo,-Core, com 2.260 megacycles.

  - Note que é recomendado ativar o hyperthreading e foi comprovado que melhora o desempenho para os servidores que suportam áudio/vídeo.

  - Servidores de borda: o número de Servidores de borda requeridos, com base em 30% de todos os usuários simultâneos comunicando-se por meio dos Servidores de borda. Essa porcentagem não pode ser alterada na calculadora.

  - Armazenamento de serviços de Arquivamento/Registro de detalhes da camada/Qualidade da experiência: o número de armazenamentos requeridos para os recursos de Arquivamento ou Monitoramento, se estiverem ativados em sua organização.

  - Servidor requerido do banco de dados de back-end (pools requeridos): o número de servidores do banco de dados de back-end requeridos para suportar a carga de trabalho selecionada.

E mais, na linha próxima de 'Servidores de front-end totais, mais informações são fornecidas sobre a carga em seus servidores e rede para todas as cargas de trabalho planejadas e combinadas.

  - Carga média da CPU: o uso médio da CPU por servidor de front-end server.

  - Rede em Mbps: a alocação da largura de banda requerida para suportar o modelo de uso fornecido.

  - Memória em GB: a memória, em gigabytes, requerida para cada servidor de front-end server.

</div>

<div>

## <a name="adjusting-for-your-processors"></a>Ajustando para seus processadores

Todos os valores de uso da CPU supõem que cada servidor tem um processador dual, núcleo hex com 2.26 GHz, pelo menos 32 GB de memória, 8 ou mais drives de disco rídigo com 10.000 RPM e pelo menos 72 GB de espaço em disco livre.

Se seus servidores tiverem processadores diferentes, você poderá ajustar os valores para corresponderem ao seu hardware.

</div>

</div>

<span> </span>

</div>

</div>

</div>

