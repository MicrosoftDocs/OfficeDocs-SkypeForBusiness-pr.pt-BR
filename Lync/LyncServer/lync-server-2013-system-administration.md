---
title: 'Lync Server 2013: administração do sistema'
description: 'Lync Server 2013: administração do sistema.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b56271d8d90f1d83072af0577692be1ea0b5bc7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562677"
---
# <a name="system-administration-in-lync-server-2013"></a>Administração do sistema no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-08-18_

A administração do sistema inclui as tarefas administrativas do dia-a-dia, planejadas e sob demanda, que são necessárias para manter um sistema de ti operando sem problemas. Normalmente, as tarefas de administração do sistema são cobertas por procedimentos escritos. Esses procedimentos ajudam a garantir que as mesmas ferramentas e métodos padrão sejam usados por toda a equipe de suporte.

Em um ambiente do Lync, as tarefas de administração de sistema típicas incluem o backup e o arquivamento de pools, o monitoramento de logs, a criação e o gerenciamento de usuários e a atualização do software antivírus.

<div>

## <a name="system-troubleshooting"></a>Solução de problemas do sistema

Uma organização deve estar preparada para lidar com problemas inesperados e deve ter um procedimento para gerenciar problemas do ponto em que eles são relatados até a resolução. As informações sobre como a equipe de suporte diagnosticou um problema devem ser registradas e usadas no futuro para evitar o trabalho concluído de repetição desnecessariamente.

</div>

<div>

## <a name="system-troubleshooting-process"></a>Processo de solução de problemas do sistema

O diagrama a seguir mostra o processo de solução de problemas do sistema e as interações com outras funções de operações.

**Fluxograma de solução de problemas do sistema**

![Fluxograma de solução de problemas do sistema](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Fluxograma de solução de problemas do sistema")

  - **Classificar e priorizar**     Essa tarefa geralmente é executada pelo serviço de suporte. Por exemplo, um problema pode ser agrupado como um problema de software ou de hardware. O problema é roteado para a equipe de suporte adequada para investigação. As regras para determinar a prioridade de um problema, junto com o tempo de resposta e o tempo para resolver, normalmente são definidas no SLA.

  - **Investigue e diagnostique**     A equipe de suporte apropriada diagnostica o problema e propõe alterações para resolver o problema. Se a solução for simples e não exigir controle de alterações, a solução poderá ser aplicada imediatamente. Se a solução não for fácil, uma solicitação de alteração deverá ser disparada e o trabalho proposto deverá ser gerenciado pelo processo de gerenciamento de alterações, frequentemente sob um procedimento de "rápido controle". As alterações feitas devem ser registradas usando o processo de gerenciamento de configuração.

  - **Fechar e gravar**     Após testar a resolução, o problema deverá ser fechado. Se houver lições a serem aprendidas do problema, uma entrada deverá ser criada na base de dados de conhecimento.

  - **Revisão e análise**     de tendências Revisões periódicas de problemas recentes devem ser realizadas para identificar tendências de problemas. Por exemplo, se os usuários estiverem enfrentando problemas freqüentes com logons lentos para seus sites do Lync, os problemas de largura de banda da rede poderão ser a causa. Os tempos de solução de problemas e o efeito de qualquer paralisação na disponibilidade do sistema devem ser revisados e comparados com o SLA. A pessoa que liaises com os problemas de serviço do cliente, como um gerente de contas, deve ser informada sobre problemas significativos.

</div>

<div>

## <a name="issue-management-tools"></a>Ferramentas de gerenciamento de problemas

As ferramentas de suporte técnico permitem que a equipe grave, classifique e Priorize novos problemas. As ferramentas fornecerão os processos de fluxo de trabalho para gerenciar a solicitação de serviço de problema através de investigação e diagnóstico, geralmente por mais de uma equipe de suporte. Ferramentas, que freqüentemente fornecem relatórios sobre tempos de resolução e tendências históricas, podem também incluir um banco de dados base de conhecimento, que pode ser usado para pesquisar por problemas passados.

A base de dados de conhecimento da Microsoft é um registro útil de problemas de suporte encontrados pela Microsoft. Para obter mais informações, consulte o site de suporte da Microsoft ( <https://go.microsoft.com/fwlink/?linkid=14898> ).

Geralmente, o software de terceiros requer personalização para atender às necessidades da organização, como a organização do Teams, os requisitos de relatórios e as medidas necessárias para o SLA.

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>Administração centralizada vs. descentralizada

Funções e responsabilidades para executar tarefas de administração do sistema dependem se a organização segue um modelo centralizado, um modelo descentralizado ou uma combinação de ambos.

  - **Modelo**     centralizado Em um modelo centralizado, um ou vários grupos administrativos mantêm o controle total de todo o ambiente do Lync Server. Esse modelo administrativo é semelhante a um Data Center em que todas as tarefas administrativas são realizadas por um único grupo de tecnologia da informação. As funções e responsabilidades dentro da equipe devem ser definidas de acordo com a experiência e o conhecimento especializado.

  - Modelo descentralizado **Decentralized Model**     As organizações descentralizadas estão localizadas em vários locais geográficos e em equipes e servidores do Lync Server funcionando em locais diferentes. Por exemplo, pode haver uma equipe de administração local e um ou mais servidores que executam o Lync Server 2013 para cada país/região. Ou, pode haver um pool de servidores que executam o Lync Server 2013 e uma equipe administrativa para a América do Norte e um para a Europa. Às vezes, convém que os administradores sejam responsáveis apenas por sua própria área geográfica e restrinjam as permissões para administrar recursos em outras áreas.

O Lync Server também permite que você delegue tarefas administrativas específicas para pessoas ou grupos específicos usando o controle de acesso baseado em função (RBAC). O RBAC permite que os administradores deleguem direitos e permissões de usuário específicos a outros administradores para executar um subconjunto das tarefas administrativas possíveis. Usando o RBAC, a capacidade do usuário de realizar tarefas administrativas específicas depende das funções RBAC atribuídas ao usuário. O RBAC fornece uma lista de cmdlets que o usuário pode executar com base nas funções RBAC das quais o usuário é membro.

</div>

</div>

<span> </span>

</div>

</div>

</div>

