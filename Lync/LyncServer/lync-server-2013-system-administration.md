---
title: 'Lync Server 2013: administração do sistema'
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
ms.openlocfilehash: 8e10f0d340ec0d291d0b184b8649f8f132683e08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>Administração do sistema no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-08-18_

A administração do sistema inclui as tarefas administrativas do dia a dia, planejadas e sob demanda, que são necessárias para manter um sistema de ti operando tranqüilamente. Geralmente, as tarefas de administração do sistema são cobertas pelos procedimentos escritos. Esses procedimentos ajudam a garantir que as mesmas ferramentas e métodos padrão sejam usados por todos os membros da equipe de suporte.

Em um ambiente do Lync, as tarefas típicas de administração do sistema incluem fazer backup e arquivamento de pools, monitorar logs, criar e gerenciar usuários e atualizar o software antivírus.

<div>

## <a name="system-troubleshooting"></a>Solução de problemas do sistema

Uma organização deve estar preparada para lidar com problemas inesperados e deve ter um procedimento para gerenciar problemas do ponto em que são reportados até a resolução. Informações sobre como a equipe de suporte diagnosticou um problema devem ser gravadas e usadas no futuro para evitar o trabalho concluído de repetição desnecessariamente.

</div>

<div>

## <a name="system-troubleshooting-process"></a>Processo de solução de problemas do sistema

O diagrama a seguir mostra o processo de solução de problemas do sistema e as interações com outras funções de operações.

**Fluxograma de solução de problemas do sistema**

![Fluxograma de solução de problemas do sistema](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Fluxograma de solução de problemas do sistema")

  - **Classificar e priorizar**   essa tarefa geralmente é realizada pela mesa do serviço. Por exemplo, um problema pode ser agrupado como um problema de software ou de hardware. O problema é encaminhado para a equipe de suporte apropriada para investigação. As regras para determinar a prioridade de um problema, em conjunto com o tempo de resposta e tempo para resolver, geralmente são definidas no SLA.

  - **Investigue e diagnostique**   a equipe de suporte apropriada diagnostica o problema e propõe mudanças para solucionar o problema. Se a solução for simples e não exigir controle de alterações, a solução poderá ser aplicada imediatamente. Se a solução não for fácil, uma solicitação de alteração deve ser gerada e o trabalho proposto deve ser gerenciado pelo processo de gerenciamento de alterações, frequentemente sob um procedimento de "controle rápido". Todas as alterações feitas devem ser gravadas usando o processo de gerenciamento de configuração.

  - **Fechar e gravar**   após testar a resolução, o problema deve ser fechado. Se houver aulas a serem aprendidas a partir do problema, uma entrada deve ser criada na base de dados de conhecimento.

  - ****   Análises de análise de tendências e análises periódicas de problemas recentes devem ser realizadas para identificar as tendências dos problemas. Por exemplo, se os usuários estiverem experimentando problemas frequentes com logons lentos para seus sites do Lync, problemas de largura de banda de rede podem ser a causa. Problemas de resolução de problemas e o efeito de qualquer paralisação na disponibilidade do sistema deve ser revisado e comparado com o SLA. A pessoa que liaises com os problemas de serviço do cliente, como um gerente de contas, deve ser informada sobre problemas significativos.

</div>

<div>

## <a name="issue-management-tools"></a>Ferramentas de gerenciamento de problemas

As ferramentas de suporte do serviço permitem que a equipe Registre, classifique e Priorize novos problemas. Em seguida, as ferramentas fornecerão os processos de fluxo de trabalho para gerenciar a solicitação de serviço de problemas por meio de investigação e diagnóstico, muitas vezes por mais de uma equipe de suporte. Ferramentas, que freqüentemente fornecem relatórios sobre tempos de resolução e tendências históricas também podem incluir um banco de dados base de conhecimento, que pode ser usado para pesquisar por problemas anteriores.

A base de dados de conhecimento Microsoft é um registro útil de problemas de suporte encontrados pela Microsoft. Para obter mais informações, consulte o site de suporte<http://go.microsoft.com/fwlink/?linkid=14898>da Microsoft ().

Geralmente, o software de terceiros exige a personalização para atender às necessidades da organização, como a organização de equipes, os requisitos de relatórios e as medidas necessárias para o SLA.

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>Administração centralizada versus descentralizada

Funções e responsabilidades para executar tarefas de administração do sistema dependem se a organização segue um modelo centralizado, um modelo descentralizado ou uma combinação de ambos.

  - **O modelo**   centralizado em um modelo centralizado, um ou vários grupos administrativos mantém o controle total de todo o ambiente do Lync Server. Esse modelo administrativo é semelhante a um data center onde todas as tarefas de administração são realizadas por um único grupo de tecnologia da informação. As funções e responsabilidades dentro da equipe devem ser definidas de acordo com a experiência e a experiência.

  - **Modelo descentralizado**   as organizações descentralizadas estão localizadas em diversos locais geográficos e têm servidores do Lync Server em funcionamento e equipes de administradores em diferentes locais. Por exemplo, pode haver um pessoal de administração local e um ou mais servidores que executam o Lync Server 2013 para cada país/região. Ou, pode haver um pool de servidores executando o Lync Server 2013 e uma equipe administrativa para a América do Norte e outro para a Europa. Às vezes, você pode querer que os administradores sejam responsáveis apenas por sua própria área geográfica e restrinja permissões para administrar recursos em outras áreas.

O Lync Server também permite que você delegue tarefas administrativas específicas para pessoas ou grupos específicos usando o controle de acesso baseado em função (RBAC). O RBAC permite que os administradores deleguem direitos de usuário específicos e permissões a outros administradores executem um subconjunto de tarefas administrativas possível. Ao usar o RBAC, a capacidade de o usuário executar tarefas administrativas específicas depende das funções RBAC atribuídas ao usuário. RBAC fornece uma lista de cmdlets que o usuário pode executar com base nas funções RBAC das quais o usuário é membro.

</div>

</div>

<span> </span>

</div>

</div>

</div>

