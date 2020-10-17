---
title: 'Lync Server 2013: estabelecendo um plano de backup e restauração'
description: 'Lync Server 2013: estabelecendo um plano de backup e restauração.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06d93c713364bf6b5f230b255b68a2c1dfe1d04a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555047"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Estabelecendo um plano de backup e restauração para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-17_

Criar um plano de backup e restauração envolve as seguintes etapas:

  - Desenvolver o plano.

  - Implementar o plano.

  - Manutenção do plano.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>Como desenvolver um plano de backup e restauração

Depois de desenvolver sua estratégia de backup e restauração para o Lync Server, use-a para documentar um plano detalhado de backup e restauração. Seu plano deve transmitir claramente as prioridades e requisitos para fazer backup de dados e configurações. Você pode usar as informações [para estabelecer uma estratégia de backup e restauração para o Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) e as planilhas em [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) para facilitar a documentação da sua estratégia. Seu plano também deve conter critérios para decidir quando e como restaurar serviços.

À medida que desenvolver seu plano, você precisará considerar e fazer a conta do seguinte:

  - Como recuperará servidores no novo hardware.

  - Como recuperará serviços que exigem ações da parte de várias áreas de negócio ou departamentos.

  - Como poderá obter servidores sobressalentes de forma rápida.

  - O tempo necessário para recuperar usando sua estratégia. Considere os requisitos da sua organização para o objetivo de tempo de recuperação (RTO).

Modifique os procedimentos de backup e restauração neste tópico, adicionando e excluindo procedimentos conforme apropriado, para refletir os servidores e componentes em sua implantação. Você também pode adicionar detalhes apropriados, como o agendamento de backup, aos procedimentos adequados para garantir que as informações não sejam ignoradas.

<div>


> [!NOTE]  
> É uma boa prática criar scripts para o máximo de etapas possíveis, para ajudar a garantir a qualidade e a reprodutibilidade de procedimentos.



</div>

Em seu plano, especifique quem é responsável por analisar o plano, que é responsável por testar e validar quaisquer novos procedimentos ou ferramentas e quem deve aprovar qualquer alteração no plano e nos procedimentos relacionados.

Para garantir que seu plano de backup e restauração atenda totalmente a todas as metas e prioridades estabelecidas, obtenha a aprovação dos tomadores de decisões de negócios e dos tomadores de decisões técnicos apropriados em sua organização antes de implementar o plano.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>Como implementar o plano de backup e restauração

A implementação de um plano de backup e restauração exige as seguintes etapas:

  - Testar e validar o plano.

  - Comunicar o plano.

  - Validar as operações de backup e restauração.

<div>

## <a name="testing-and-validating-the-plan"></a>Testar e validar o plano

Os procedimentos descritos aqui foram testados e validados em um ambiente de laboratório. Para certificar-se de que esses ou outros procedimentos funcionam em seu ambiente, você deve testar e validar cada procedimento que pretende implementar. Conclua o teste e a validação antes de enviar seu plano para aprovação final.

</div>

<div>

## <a name="communicating-the-plan"></a>Comunicar o plano

Seu plano de backup e restauração deve descrever claramente quem implementará os procedimentos e as instruções passo a passo para executá-los. Você deve certificar-se de que todos os responsáveis por qualquer aspecto do backup e da restauração compreendam o plano, como ele deve ser implementado e qual é sua função. Isso inclui todos os requisitos da implementação para:

  - Backup do pool e do servidor.

  - Restauração do serviço.

**Backup do pool e de servidores**

O plano de backup e restauração deve incluir todas as informações necessárias para concluir os procedimentos de backup continuamente. As principais informações a serem comunicadas aos membros da equipe responsável incluem:

  - Equipe ou pessoa (especificada como uma pessoa ou função) responsável por fazer o backup de cada servidor.

  - Agendas específicas para o backup de cada servidor.

  - Locais de backup para cada tipo de dados (configurações, banco de dados e compartilhamentos de arquivos).

  - Procedimentos de backup a serem usados, incluindo as ferramentas necessárias para concluir cada procedimento.

  - Informações necessárias para concluir backups, conforme abordado em [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Métodos de validação a serem usados para ajudar a garantir que os dados e as configurações sejam incluídos no backup e disponíveis para restauração, o que pode incluir auditorias periódicas e restaurações de teste.

**Restauração de serviços**

O plano de backup e restauração deve incluir todas as informações necessárias para restaurar o serviço, no caso de um ou mais servidores experimentarem uma perda que torna o serviço indisponível. As principais informações a serem comunicadas aos membros da equipe responsável incluem:

  - Equipe ou pessoa (especificado como indivíduo ou função) responsável por determinar quando a restauração de serviços será necessária e os procedimentos a serem usados para restaurá-los e, também, a equipe ou pessoa responsável por implementar procedimentos para cada cenário de restauração.

  - Critérios para determinar quais procedimentos de restauração são mais apropriados para uma situação específica.

  - Estimativas de tempo para restauração de RTO (objetivo de tempo de recuperação) e de serviço em cada cenário de restauração.

  - Procedimentos de restauração a serem usados, incluindo as ferramentas necessárias para concluir cada um deles.

  - As informações necessárias para restaurar dados e configurações. As planilhas são fornecidas em [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>Como validar as operações de backup e restauração

Depois de concluir os esforços iniciais de backup em seu ambiente de produção e a intervalos específicos (conforme descrito em seu plano de backup e restauração), você deve verificar se:

  - Os backups estão ocorrendo conforme o solicitado.

  - Dados de backup e configurações estão acessíveis.

  - Os procedimentos de restauração podem ser executados dentro dos tempos de objetivo de tempo de recuperação (RTO) especificados no plano de backup e restauração, e os resultados atendem a todos os requisitos de negócios.

  - Planilhas de backup foram preenchidas e verificadas e estão armazenadas em um local seguro. Essas planilhas são fornecidas em [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Procedimentos de restauração foram testados e verificados se funcionam conforme o esperado, de acordo com o especificado no plano.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>Como manter o plano de backup e restauração

Uma topologia do Lync Server é um ambiente dinâmico que muda com sua organização. Reavalie o plano de backup e restauração à medida que sua organização mudar e revise-o periodicamente para garantir que ele continue atendendo às necessidades da sua empresa.

</div>

</div>

<span> </span>

</div>

</div>

</div>

