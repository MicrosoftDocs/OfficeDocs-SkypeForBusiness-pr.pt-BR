---
title: Teste de escalabilidade do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d702b0a197e6e81fbc6833ca58968a10d8dd3fff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Testes de escalabilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

O Lync Server 2013 fornece a infraestrutura de servidor para todas as comunicações em tempo real do Lync Server, incluindo mensagens instantâneas (IM) e presença, conferência e Enterprise Voice. Isso inclui os recursos que usam os recursos de hardware de um pool do Lync Server 2013 e, portanto, afetam o desempenho e a escala. Todas as organizações não usam todos os recursos da mesma forma.

Por exemplo, algumas organizações podem usar vídeo em conferências muito difíceis enquanto outras podem ter pouco ou nenhum uso de vídeo. Algumas organizações preferem o compartilhamento de slides do PowerPoint ao compartilhamento de aplicativos, enquanto outras preferem o oposto. Essas organizações que implantam o Enterprise Voice podem ou não usar o aplicativo de grupo de resposta pesadamente. A maioria das organizações implanta servidores de monitoramento, mas não muitas delas implantam servidores de arquivamento. Além disso, as organizações não têm todas as mesmas infra-estruturas, incluindo capacidades de hardware, capacidades de rede e o número de pools e o tamanho dos pools implantados. A diversidade de recursos e infraestruturas apresenta um desafio para testes de escalabilidade – não é possível simular todas as combinações possíveis de recursos e infraestruturas.

Para determinar o suporte de escalabilidade do Lync Server, realizamos testes usando todos os recursos do Lync Server simultaneamente, com base em um modelo de uso médio (modelo de usuário). Para determinar um modelo de usuário apropriado para cargas de trabalho do Lync Server, analisamos muitos pontos de dados, incluindo pesquisas de cliente, comentários do programa de aperfeiçoamento da experiência do usuário da Microsoft, dados de uso do Lync Server do departamento de ti interno da Microsoft, e dados minados pelo nosso serviço de reunião ao vivo. Em muitos casos, o modelo de usuário tem um Bias em direção a cargas mais pesadas para fornecer uma margem confortável para uso dentro de uma organização.

Em nossos testes de escalabilidade, configuramos pools do Lync Server 2013 de acordo com as especificações recomendadas de hardware e software, incluindo componentes de infraestrutura, como os serviços de domínio do Active Directory, saldos de carga de hardware e firewalls. Configuramos os ambientes do Lync Server o mais próximo possível para ambientes típicos do mundo real. Em seguida, usamos a ferramenta de stress e desempenho do Lync Server 2013 para simular cargas do Lync Server 2013 (com base em nosso modelo de usuário). .

Fazemos várias iterações de testes de escalabilidade (incluindo várias execuções de teste de três semanas). Usamos os resultados de todos os testes para ajudar com o ajuste de desempenho e para verificar o suporte para os números de escalabilidade em nosso modelo de usuário.

</div>

<span> </span>

</div>

</div>

</div>

