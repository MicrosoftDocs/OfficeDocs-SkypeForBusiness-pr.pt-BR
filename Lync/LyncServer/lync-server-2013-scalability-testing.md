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
ms.openlocfilehash: b23bd731e123c8dba78c3919f9f2a1ff1a6fd1cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Testes de escalabilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

O Lync Server 2013 fornece a infraestrutura de servidor para todas as comunicações em tempo real do Lync Server, incluindo mensagens instantâneas (IM) e presença, conferência e Enterprise Voice. Isso inclui todos os recursos que usam os recursos de hardware de um pool do Lync Server 2013 e, portanto, afetam o desempenho e a escala. Todas as organizações não usam os mesmos recursos.

Por exemplo, algumas organizações podem usar vídeo em conferências muito pesadas enquanto outros podem não ter ou quase não ter uso de vídeo. Algumas organizações preferem compartilhamento de slides do PowerPoint ao compartilhamento de aplicativos, enquanto outros preferem o oposto. As organizações que implantam o Enterprise Voice podem ou não usar o aplicativo de grupo de resposta de muitas pessoas. A maioria das organizações implanta servidores de monitoramento, mas não muitos deles implantam servidores de arquivamento. Além disso, as organizações não têm a mesma infraestrutura, incluindo capacidade de hardware, capacidade de rede e número de pools e tamanho dos pools implantados. A diversidade dos recursos e infraestrutura é um desafio para o teste de escalabilidade – não é possível simular todas as combinações possíveis de recursos e infraestruturas.

Para determinar o suporte de escalabilidade para o Lync Server, realizamos testes usando todos os recursos do Lync Server simultaneamente, com base em um modelo de uso médio (modelo de usuário). Para determinar um modelo de usuário apropriado para cargas de trabalho do Lync Server, analisamos muitos pontos de dados, incluindo pesquisas de clientes, comentários do programa de aperfeiçoamento da experiência do usuário da Microsoft, dados de uso do Lync Server do departamento de ti interno da Microsoft, e dados minados de nosso serviço do Live Meeting. Em vários casos, o modelo do usuário tem uma tendência em relação às cargas pesadas para oferecer uma margem confortável de uso dentro de uma organização.

Em nossos testes de escalabilidade, configuramos pools do Lync Server 2013 de acordo com as especificações recomendadas de hardware e software, incluindo componentes de infraestrutura, como serviços de domínio do Active Directory, balanceadores de carga de hardware e firewalls. Configuramos os ambientes do Lync Server o mais próximo possível dos ambientes reais típicos. Em seguida, usamos a ferramenta de estresse e desempenho do Lync Server 2013 para simular cargas do Lync Server 2013 (com base no nosso modelo de usuário). .

Realizamos várias iterações de testes de escalabilidade (incluindo várias execuções de testes de três semanas). Usamos os resultados de todos os testes para ajudar com a sintonização do desempenho e verificar o suporte para os números de escalabilidade em nosso modelo do usuário.

</div>

<span> </span>

</div>

</div>

</div>

