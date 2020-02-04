---
title: 'Lync Server 2013: estabelecendo um plano de backup e restauração'
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
ms.openlocfilehash: cee1c4571dafa4e513f42613de13205ecec9de42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Como estabelecer um plano de backup e restauração para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-17_

A criação de um plano de backup e restauração envolve as seguintes etapas:

  - Desenvolvendo o plano.

  - Implementação do plano.

  - Manutenção do plano.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>Desenvolvendo um plano de backup e restauração

Depois de desenvolver sua estratégia de backup e restauração para o Lync Server, use-a para documentar um plano detalhado de backup e restauração. Seu plano deve transmitir claramente as prioridades e os requisitos para fazer backup de dados e configurações. Você pode usar as informações em [estabelecer uma estratégia de backup e restauração para o Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) e as planilhas nas [planilhas de backup e restauração do Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) para facilitar a documentação da sua estratégia. Seu plano também deve conter critérios para decidir quando e como restaurar o serviço.

Ao desenvolver seu plano, você precisa considerar e fazer uma conta do seguinte:

  - Como você vai recuperar os servidores em um novo hardware.

  - Como você recuperará os serviços que exigem uma ação na parte de várias áreas comerciais ou departamentos.

  - Como você pode adquirir servidores sobressalentes rapidamente.

  - O tempo que leva para fazer a recuperação usando sua estratégia. Considere os requisitos da sua organização para o objetivo de tempo de recuperação (RTO).

Modifique os procedimentos de backup e restauração neste tópico, adicionando e excluindo procedimentos conforme apropriado, para refletir os servidores e componentes na sua implantação. Você também pode adicionar os detalhes apropriados, como o agendamento de backup, aos procedimentos apropriados para garantir que as informações não sejam ignoradas.

<div>


> [!NOTE]  
> É uma prática recomendada criar scripts para o maior número possível de etapas, para ajudar a garantir a qualidade e a Reproducibility de procedimentos.



</div>

Em seu plano, especifique quem é o responsável por revisar o plano, quem é responsável por testar e validar quaisquer novos procedimentos ou ferramentas e quem deve aprovar qualquer alteração no plano e nos procedimentos relacionados.

Para garantir que seu plano de backup e restauração atenda totalmente a todas as metas e prioridades estabelecidas, obtenha a aprovação dos tomadores de decisões de negócios e tomadores de decisões técnicas adequados em sua organização antes de implementar o plano.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>Implementando o plano de backup e restauração

A implementação de um plano de backup e restauração requer as seguintes etapas:

  - Testar e validar o plano.

  - Comunicar o plano.

  - Validando operações de backup e restauração.

<div>

## <a name="testing-and-validating-the-plan"></a>Testando e validando o plano

Os procedimentos descritos aqui foram testados e validados em um ambiente de laboratório. Para garantir que esses ou outros procedimentos funcionem em seu ambiente, você deve testar e validar cada procedimento que pretende implementar. Conclua o teste e a validação antes de enviar seu plano para aprovação final.

</div>

<div>

## <a name="communicating-the-plan"></a>Comunicando o plano

Seu plano de backup e restauração deve descrever claramente quem implementa procedimentos e instruções passo a passo para executar os procedimentos. Você deve certificar-se de que todos responsáveis por qualquer aspecto de backup e restauração compreendam o plano, como ele deve ser implementado e qual é a função deles. Isso inclui todos os requisitos de implementação para o seguinte:

  - Backup do pool e do servidor.

  - Restauração do serviço.

**Backup do pool e do servidor**

O plano de backup e restauração deve incluir todas as informações necessárias para concluir os procedimentos de backup continuamente. As informações principais a serem comunicadas aos membros da equipe responsável incluem o seguinte:

  - Equipe ou pessoa (especificada como uma pessoa ou função) responsável por fazer backup de cada servidor.

  - Agendas específicas para fazer backup de cada servidor.

  - Locais de backup para cada tipo de dados (configurações, banco de dados e compartilhamentos de arquivos).

  - Procedimentos de backup a serem usados, incluindo as ferramentas necessárias para concluir cada procedimento.

  - Informações necessárias para concluir backups, conforme abordado nas [planilhas de backup e restauração do Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Métodos de validação a serem usados para ajudar a garantir que os dados e configurações sejam backups adequadamente e disponíveis para restauração, que podem incluir auditorias periódicas e restaurações de teste.

**Restauração do serviço**

O plano de backup e restauração deve incluir todas as informações necessárias para restaurar o serviço, caso um ou mais servidores tenham uma perda que torna o serviço indisponível. As informações principais a serem comunicadas aos membros da equipe responsável incluem o seguinte:

  - Equipe ou pessoa (especificada como uma pessoa ou uma função) que é responsável por determinar quando a restauração do serviço é necessária e os procedimentos a serem usados para restaurar o serviço e também a equipe ou pessoa responsável pela implementação de procedimentos para cada um cenário de restauração.

  - Os critérios para determinar quais procedimentos de restauração são mais apropriados para uma situação específica.

  - Estimativas de tempo para restauração do RTO (objetivo de tempo de recuperação) e de serviço (RTO) em cada cenário de restauração.

  - Procedimentos de restauração a serem usados, incluindo as ferramentas necessárias para concluir cada procedimento.

  - Informações necessárias para restaurar dados e configurações. As planilhas são fornecidas em [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>Validando operações de backup e restauração

Depois de concluir os esforços iniciais de backup em seu ambiente de produção e em intervalos específicos (conforme abordado em seu plano de backup e restauração), você deve verificar o seguinte:

  - Os backups ocorrem conforme necessário.

  - Dados de backup e configurações são acessíveis.

  - Os procedimentos de restauração podem ser executados dentro dos tempos de objetivo de tempo de recuperação especificados no plano de backup e restauração, e os resultados atendem a todas as necessidades de negócios.

  - As planilhas de backup foram concluídas e verificadas e são armazenadas em um local seguro. Essas planilhas são fornecidas em [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Procedimentos de restauração foram testados e verificados para funcionar como esperado, conforme especificado no seu plano de backup e restauração.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>Manutenção do plano de backup e restauração

Uma topologia do Lync Server é um ambiente dinâmico que muda para a sua organização. Reavalie seu plano de backup e restauração à medida que sua organização muda e revise-a periodicamente para garantir que ela continue atendendo às necessidades da sua empresa.

</div>

</div>

<span> </span>

</div>

</div>

</div>

