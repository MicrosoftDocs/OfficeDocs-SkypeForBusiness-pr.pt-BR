---
title: 'Lync Server 2013: gerenciamento de capacidade e disponibilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 169c2e383a1799f5f3ab7ca810de32f86350e51b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Gerenciamento de capacidade e disponibilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-08-18_

A finalidade do gerenciamento de capacidade e gerenciamento de disponibilidade é medir e controlar o desempenho do sistema. Recomendamos que você implemente os procedimentos de gerenciamento de capacidade e gerenciamento de disponibilidade para poder medir e controlar o desempenho do sistema. Você precisa saber se o sistema está disponível e se pode atender às demandas atuais e projetadas definindo linhas de base e monitorando o sistema para procurar tendências.

<div>

## <a name="capacity-management"></a>Gerenciamento de capacidade

O gerenciamento de capacidade envolve o planejamento, o dimensionamento e o controle da capacidade do serviço para ajudar a garantir que os níveis mínimos de desempenho especificados no seu SLA sejam excedidos. O bom gerenciamento de capacidade ajuda a garantir que você possa fornecer serviços de ti a um custo razoável e ainda atender aos níveis de desempenho definidos em seus SLAs com o cliente. Esses critérios podem incluir o seguinte:

  - **Tempo de resposta do sistema**   é o tempo medido que o sistema executa para realizar ações típicas. Os exemplos incluem o tempo necessário para que a função de servidor de áudio/vídeo processe o tráfego de áudio/vídeo, o tempo necessário para o cliente criar e ingressar em uma conferência, ou o tempo necessário para que a presença seja atualizada em todos os clientes do Inspetor.

  - **Capacidade de armazenamento**   essa é a capacidade de um sistema de armazenamento, seja um banco de dados de conteúdo, um dispositivo de backup ou uma unidade local. Os exemplos incluem a quantidade máxima de espaço de armazenamento a ser fornecida por site e o momento em que os backups devem ser armazenados antes de serem substituídos.

Ajustar a capacidade geralmente é um caso de garantir que recursos físicos suficientes estejam disponíveis, como espaço em disco e largura de banda de rede. A tabela a seguir lista as resoluções típicas de problemas relacionados à capacidade.

### <a name="typical-resolutions-for-capacity-related-issues"></a>Soluções típicas para problemas relacionados à capacidade

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Problema</th>
<th>Resolução possível</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuários remotos com desempenho ruim de áudio/vídeo</p></td>
<td><p>Verifique se a largura de banda apropriada está disponível no WAN links e se a QoS está habilitada e devidamente configurada. Verifique os dados de QoE.</p></td>
</tr>
<tr class="even">
<td><p>A resposta geral do ambiente do Lync é lenta.</p></td>
<td><p>Execute testes para verificar se os servidores front-end existentes podem lidar com a carga. Apresente um novo servidor front-end, se necessário. Verifique os tempos de resposta do banco de dados SQL e corrija as causas dos atrasos (por exemplo, melhorar a e/s de disco).</p></td>
</tr>
</tbody>
</table>


A solução de problemas com mais detalhes é abordada no guia de rede do Lync Server.

A capacidade é afetada pela configuração do sistema e depende de recursos físicos, como largura de banda de rede. Por exemplo, se um ambiente do Lync estiver configurado para executar um backup completo durante a noite, deve-se tomar cuidado para ajudar a garantir que o efeito sobre o desempenho interativo de usuários finais seja minimizado.

Gerenciamento de capacidade é o processo de manter a capacidade de um sistema dentro dos níveis aceitáveis e soluciona os seguintes problemas:

  - **Reagindo a alterações nos requisitos de**   capacidade devem ser ajustados para fazer alterações no sistema ou na organização. Por exemplo, se o seu ambiente decidir implementar o Enterprise Voice, o número e o posicionamento dos servidores de mediação e dos gateways da rede de telefonia pública comutada (PSTN) serão muito importantes. Se você estiver fazendo entroncamento SIP ou Direct SIP, o design geral será alterado de forma significativa para fornecer o melhor desempenho de voz empresarial.

  - **Prevendo requisitos**   futuros alguns requisitos de capacidade mudam de forma previsível ao longo do tempo. Rastreando tendências você pode planejar atualizações com antecedência. Por exemplo, a largura de banda disponível entre vários sites do Lync deve ser monitorada para criar uma linha de base. Esta linha de base permitirá que você se preveja quando precisa adicionar mais largura de banda a esses links, pois a contagem de usuários nesses sites remotos aumenta com o tempo.

</div>

<div>

## <a name="availability-management"></a>Gerenciamento de disponibilidade

Gerenciamento de disponibilidade é o processo de garantir que qualquer serviço de ti consistentemente e de forma econômica forneça o nível de serviço confiável, que é necessário para o cliente. O gerenciamento de disponibilidade lida com a minimização da perda de serviço e com a opção de garantir que a ação adequada seja tomada se o serviço for perdido. Em um ambiente do Lync, você pode se preocupar em se o serviço Enterprise Voice está disponível, se os usuários podem ingressar em conferências programadas e assim por diante. Um SLA define uma frequência e uma duração de paralisação aceitáveis e permite determinados períodos quando o sistema não está disponível para manutenção planejada.

Se você precisar fornecer relatórios ao seu gerenciamento sobre a disponibilidade de sistemas ou se tiver outras penalidades financeiras ou de outras penalidades associadas a destinos de disponibilidade ausentes, deverá gravar dados de disponibilidade. Mesmo que você não tenha esses requisitos formais, é uma boa ideia ao menos saber com que frequência um sistema falhou em um determinado período de tempo. Por exemplo, a disponibilidade do sistema nos últimos 12 meses e o tempo necessário para recuperar-se de cada falha. Essas informações ajudarão você a medir e melhorar a eficácia da equipe em responder a uma falha do sistema. Ele também pode lhe fornecer informações úteis se houver uma contestação.

As medidas relacionadas à disponibilidade são as seguintes:

  - **Disponibilidade**   geralmente expressa como o tempo que um sistema ou serviço pode ser acessado em comparação com o tempo em que está inoperante. Geralmente, é expresso como uma porcentagem. (Você pode ver referências a "três noves" ou "cinco noves". Eles fazem referência a 99,9% ou 99,999% de disponibilidade.)

  - **Confiabilidade**   isso é uma medida do tempo entre falhas de um sistema e, às vezes, é expresso como média (ou média) de tempo entre falhas (MTBF).

  - **Tempo para reparar**   isso é o tempo levado para recuperar um serviço após uma falha e geralmente é expresso como média (significando a média) tempo para reparar (MTTR).

A disponibilidade, a confiabilidade e o tempo para reparo estão relacionados da seguinte maneira:

**Disponibilidade = (MTBF – MTTR)/MTBF**   por exemplo, se um servidor falhar duas vezes durante um período de seis meses e não estiver disponível para uma média de 20 minutos, o MTBF será de três meses ou 90 dias, e o MTTR será de 20 minutos. Portanto, Availability = (90 dias – 20 minutos)/90 dias = 99,985%.

Gerenciamento de disponibilidade é o processo de garantir que a disponibilidade seja maximizada e mantida dentro dos parâmetros definidos em SLAs. O gerenciamento de disponibilidade inclui os seguintes processos:

  - **Monitoramento**     examinando quando e por quanto tempo os serviços estão indisponíveis.

  - ****   Os valores de disponibilidade de relatório devem ser regularmente fornecidos a equipes de gerenciamento, usuários e operações. Esses relatórios devem realçar tendências e identificar áreas bem e áreas que exijam atenção. O relatório deve resumir a conformidade com destinos definidos nos SLAs.

  - **Melhorias**   se a disponibilidade não atender aos destinos que são definidos nos SLAs ou em que a tendência está em relação à disponibilidade reduzida, o processo de gerenciamento de disponibilidade deve planejar etapas de mídia. Isso deve incluir trabalhar com outras equipes responsáveis para realçar os motivos de paralisações e planejar ações corretivas para impedir uma recorrência das paralisações.

Medidas de capacidade e disponibilidade são tarefas repetitivas que são ideais para ferramentas automatizadas e scripts como o Microsoft System Center Operations Manager (antigo Microsoft Operations Manager), que é abordado mais adiante neste documento.

</div>

<div>

## <a name="see-also"></a>Confira também


[Monitorar o Lync Server 2013 com o System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

