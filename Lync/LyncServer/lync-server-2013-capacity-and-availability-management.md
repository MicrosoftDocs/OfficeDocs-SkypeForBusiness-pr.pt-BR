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
ms.openlocfilehash: efef66bcac833bb67c67dc453c25f3e0f6d51ba1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512848"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Gerenciamento de capacidade e disponibilidade no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-08-18_

O objetivo do gerenciamento de capacidade e gerenciamento de disponibilidade é medir e controlar o desempenho do sistema. É recomendável implementar os procedimentos de gerenciamento de capacidade e gerenciamento de disponibilidade para que você possa medir e controlar o desempenho do sistema. Você deve saber se o sistema está disponível e se pode lidar com as demandas atuais e projetadas configurando as linhas de base e monitorando o sistema para procurar tendências.

<div>

## <a name="capacity-management"></a>Gerenciamento de capacidade

O gerenciamento de capacidade envolve planejamento, dimensionamento e controle da capacidade de serviço para ajudar a garantir que os níveis de desempenho mínimos especificados no SLA sejam excedidos. O bom gerenciamento de capacidade ajuda a garantir que você possa fornecer serviços de ti a um custo razoável e ainda atender aos níveis de desempenho definidos em seus SLAs com o cliente. Esses critérios podem incluir o seguinte:

  - Tempo de resposta do **sistema**     Esse é o tempo medido que o sistema leva para executar ações típicas. Os exemplos incluem o tempo necessário para que a função de servidor de áudio/vídeo processe o tráfego de áudio/vídeo, o tempo necessário para um cliente criar e ingressar em uma conferência ou o tempo gasto para que a presença seja atualizada em todos os clientes do observador.

  - **Capacidade**     de armazenamento Esta é a capacidade de um sistema de armazenamento, seja um banco de dados de conteúdo, um dispositivo de backup ou uma unidade local. Os exemplos incluem a quantidade máxima de espaço de armazenamento a ser fornecida por site e o momento em que os backups devem ser armazenados antes de serem substituídos.

O ajuste da capacidade geralmente é um caso de garantir que recursos físicos suficientes estejam disponíveis, como espaço em disco e largura de banda da rede. A tabela a seguir lista as resoluções típicas para problemas relacionados à capacidade.

### <a name="typical-resolutions-for-capacity-related-issues"></a>Soluções típicas para problemas relacionados à capacidade

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Problema</th>
<th>Solução possível</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuários remotos com desempenho ruim de áudio/vídeo</p></td>
<td><p>Verifique se a largura de banda apropriada está disponível nos links WAN e se a QoS está habilitada e corretamente configurada. Verifique os dados de QoE.</p></td>
</tr>
<tr class="even">
<td><p>A resposta geral do ambiente do Lync é lenta.</p></td>
<td><p>Execute testes para verificar se os servidores front-end existentes podem lidar com a carga. Introduza um novo servidor front-end, se necessário. Verifique os tempos de resposta do banco de dados SQL e corrija as causas dos atrasos (por exemplo, melhorar a e/s de disco).</p></td>
</tr>
</tbody>
</table>


A solução de problemas mais detalhada é abordada no guia de rede do Lync Server.

A capacidade é afetada pela configuração do sistema e depende de recursos físicos, como a largura de banda da rede. Por exemplo, se um ambiente do Lync é configurado para executar um backup completo à noite, deve-se tomar cuidado para ajudar a garantir que o efeito no desempenho interativo experiente por usuários finais seja minimizado.

O gerenciamento de capacidade é o processo de manter a capacidade de um sistema em níveis aceitáveis e aborda os seguintes problemas:

  - **Reagindo a alterações nos requisitos**     Os requisitos de capacidade precisam ser ajustados para que as alterações sejam feitas no sistema ou na organização. Por exemplo, se seu ambiente decidir implementar o Enterprise Voice, o número e o posicionamento de servidores de mediação e gateways PSTN (rede telefônica pública comutada) serão muito importantes. Se você estiver fazendo um tronco SIP (Session Initiation Protocol) ou SIP direto, o design geral será alterado significativamente para fornecer o melhor desempenho do Enterprise Voice.

  - **Prever requisitos futuros**     Alguns requisitos de capacidade mudam de forma preditiva com o passar do tempo. Ao controlar as tendências, você pode planejar atualizações com antecedência. Por exemplo, a largura de banda disponível entre vários sites do Lync deve ser monitorada para criar uma linha de base. Essa linha de base permitirá a você prever quando você precisa adicionar mais largura de banda a esses links, já que a contagem de usuários nesses sites remotos aumenta com o tempo.

</div>

<div>

## <a name="availability-management"></a>Gerenciamento de disponibilidade

O gerenciamento de disponibilidade é o processo de garantir que todos os serviços de ti de forma consistente e econômico forneça o nível de serviço consistente e confiável exigido pelo cliente. O gerenciamento de disponibilidade lida com a redução da perda de serviço e com a execução da ação apropriada se o serviço for perdido. Em um ambiente do Lync, você pode estar preocupado se o serviço Enterprise Voice está disponível, se os usuários podem participar de conferências agendadas e assim por diante. Um SLA define uma frequência e um comprimento aceitáveis e permite determinados períodos quando o sistema não está disponível para manutenção planejada.

Se você precisar fornecer relatórios para seu gerenciamento sobre a disponibilidade de sistemas, ou se você tiver penalidades financeiras ou outras, você deve registrar os dados de disponibilidade. Mesmo que você não tenha esses requisitos formais, é uma boa ideia, pelo menos, saber com que frequência um sistema falhou em um determinado período de tempo. Por exemplo, a disponibilidade do sistema nos últimos 12 meses e quanto tempo levou para se recuperar de cada falha. Essas informações ajudarão você a medir e aprimorar a eficácia da sua equipe em responder a uma falha do sistema. Ele também pode fornecer informações úteis se houver uma contestação.

As medidas relacionadas à disponibilidade são as seguintes:

  - **Disponibilidade**     Isso é normalmente expresso como o tempo que um sistema ou serviço pode ser acessado em comparação com o momento em que ele está desativado. Normalmente, é expresso como uma porcentagem. (Você pode ver referências de "três noves" ou "cinco noves". Eles se referem à disponibilidade de 99,9% ou 99,999%.)

  - **Confiabilidade**     Essa é uma medida do tempo entre as falhas de um sistema e, às vezes, é expressa como média (ou média) de tempo entre falhas (MTBF).

  - **Tempo para reparar**     Esse é o tempo necessário para recuperar um serviço após uma falha, e geralmente é expresso como média (significando média) tempo para reparar (MTTR).

Disponibilidade, confiabilidade e tempo para reparo estão relacionados da seguinte maneira:

**Disponibilidade = (MTBF – MTTR)/MTBF**     Por exemplo, se um servidor falhar duas vezes em um período de seis meses e não estiver disponível para uma média de 20 minutos, o MTBF será de três meses ou 90 dias e o MTTR será de 20 minutos. Portanto, disponibilidade = (90 dias – 20 minutos)/90 dias = 99,985%.

O gerenciamento de disponibilidade é o processo de garantir que a disponibilidade seja maximizada e mantida nos parâmetros definidos em SLAs. O gerenciamento de disponibilidade inclui os seguintes processos:

  - **Monitoramento**     Examinando quando e por quanto tempo os serviços não estão disponíveis.

  - **Relatórios**     Os números de disponibilidade devem ser fornecidos regularmente para equipes de gerenciamento, usuários e operações. Esses relatórios devem realçar tendências e identificar áreas que são bem e áreas que exigem atenção. O relatório deve resumir a conformidade com os destinos definidos nos SLAs.

  - **Melhoria**     Se a disponibilidade não atender aos destinos definidos nos SLAs ou em que a tendência estiver em relação à disponibilidade reduzida, o processo de gerenciamento de disponibilidade deverá planejar as etapas de correções. Isso deve incluir o trabalho com outras equipes responsáveis realçar os motivos de paralisações e planejar ações corretivas para evitar uma recorrência das interrupções.

As medições de capacidade e disponibilidade são tarefas repetitivas que são ideais para ferramentas automatizadas e scripts como o Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que é abordado posteriormente neste documento.

</div>

<div>

## <a name="see-also"></a>Confira também


[Monitoramento do Lync Server 2013 com o System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

