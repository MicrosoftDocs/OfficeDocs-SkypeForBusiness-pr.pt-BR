---
title: 'Lync Server 2013: práticas recomendadas para ambientes do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf207f4cd0303330ccb01dc56e28b949c1df22f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a>Práticas recomendadas para ambientes do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-08-04_

Os seguintes princípios gerais devem ser aplicados a operações contínuas do seu sistema:

  - **Entender e usar**   MOF MOF é uma coleção de práticas recomendadas, princípios e modelos que fornecem diretrizes técnicas de organizações sobre o gerenciamento de ativos de ti, como operações diárias do Lync Server 2013. As diretrizes da MOF a seguir podem ajudá-lo a obter confiabilidade, disponibilidade, compatibilidade e capacidade de gerenciamento de sistemas de produção essenciais para os produtos da Microsoft. Para obter mais informações, consulte [Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939).

  - **Saiba mais sobre as práticas recomendadas para o Lync Server 2013**   recomendamos que você implemente procedimentos práticos e comprovados para gerenciar o Lync Server 2013. Usar métodos testados, testados e documentados de gerenciamento de operações pode ser mais eficiente do que desenvolver seus próprios métodos.

  - **Operações separadas em processos**   diários, semanais e mensais documentam as tarefas operacionais necessárias que você executará regularmente. Documentar a maneira como você executa tarefas ajuda a garantir que as suas informações sejam preservadas quando houver uma alteração no ambiente operacional, como quando novas tecnologias são implantadas ou quando ocorrem mudanças na equipe. Recomendamos que as tarefas operacionais sejam separadas em cargas de trabalho gerenciáveis nas quais as tarefas são realizadas diariamente, semanalmente e mensalmente. As tarefas diárias concentrarão esforços no funcionamento de um sistema e as tarefas mensais se concentrarão mais em garantir a integridade de longo prazo de um sistema.
    
    Este documento pode ser usado em ambientes que implantam apenas componentes de mensagem instantânea/presença (IM/P) ou IM/P com Enterprise Voice. Quando tarefas ou itens da lista de verificação são específicos do Enterprise Voice, isso é mencionado e, se o ambiente não inclui o Enterprise Voice, a parte pode ser ignorada.

  - **Implantar as ferramentas necessárias para operar o Lync Server 2013**   muitas ferramentas estão disponíveis para ajudar a solucionar problemas, automatizar tarefas e ajudar a monitorar e manter o ambiente do Lync Server 2013. Defina um conjunto padrão de ferramentas para a sua organização para que as tarefas realizadas pela equipe de operações sejam executadas de maneira precisa, eficiente, consistente e de forma controlada. Você também deve implementar processos para acompanhar incidentes e alterações de configuração importantes.

<div>

## <a name="reference"></a>Referência

Para o benefício dos leitores ainda não familiarizados com as noções básicas de gerenciamento de servidor em geral, fornecemos uma visão geral das práticas de gerenciamento de servidor. Os leitores já familiarizados com o gerenciamento de servidor podem optar por ignorar esta seção.

As práticas recomendadas são recomendações que se baseiam no conhecimento e na experiência que os profissionais de ti obtiveram em vários ambientes. Eles fornecem procedimentos padrão para tarefas típicas que os administradores do Lync Server devem executar diariamente e listar as ferramentas que elas devem usar para gerenciar um ambiente do Lync Server.

As tarefas típicas para administradores do Lync incluem o seguinte:

  - **O gerenciamento**   de capacidade e disponibilidade define como e o que medir para prever requisitos de capacidade futuros e para informar sobre a capacidade, a confiabilidade e a disponibilidade de seus sistemas. Você deve verificar se servidores que estão executando o Lync Server são dimensionados para manipular a carga no sistema e se o tempo de inatividade não planejado é mantido nos níveis definidos no contrato de nível de serviço (SLA). Além disso, você precisará atualizar o hardware para continuar a atender aos requisitos definidos.

  - **Gerenciamento de alterações e gerenciamento de configuração**   controle como as alterações são feitas nos sistemas de ti. Isso deve incluir testes, comentários sobre o aplicativo e planos de contingência, documentação de todas as alterações e aprovação do gerenciamento se ocorrerem problemas. Mantenha um registro dos ativos de software e hardware e suas configurações.

  - ****   Estrutura de tópicos de administração do sistema métodos padrão para realizar tarefas administrativas, como administração de banco de dados e administração de sites.

  - **A administração**   de segurança tem uma política e um plano detalhados que protegem a confidencialidade dos dados, a integridade dos dados e a disponibilidade de dados da infraestrutura de ti. Isso inclui atividades e tarefas do dia-a-dia relacionadas à manutenção e ajuste da infra-estrutura de segurança de ti.

  - **Solução de problemas de sistema**   descreve métodos para lidar com problemas inesperados, incluindo etapas para evitar problemas semelhantes no futuro.

  - **Os contratos**   de nível de serviço mantêm um conjunto de metas para o desempenho dos sistemas de ti e medem regularmente o desempenho contra essas metas.

  - **Documentação**   documentar procedimentos padrão, como informações de configuração e aulas aprendidas, e disponibilizá-las para os membros da equipe que precisam delas. Quando forem feitas alterações na configuração, atualize a documentação de acordo com isso.

</div>

<div>

## <a name="related-sections"></a>Seções Relacionadas

Examine os tópicos a seguir em relação às operações do sistema antes de prosseguir:

  - [Gerenciamento de capacidade e disponibilidade no Lync Server 2013](lync-server-2013-capacity-and-availability-management.md)

  - [Gerenciamento de alterações no Lync Server 2013](lync-server-2013-change-management.md)

  - [Gerenciamento de configuração no Lync Server 2013](lync-server-2013-configuration-management.md)

  - [Administração do sistema no Lync Server 2013](lync-server-2013-system-administration.md)

  - [Contratos de nível de serviço no Lync Server 2013](lync-server-2013-service-level-agreements.md)

  - [Documentação no Lync Server 2013](lync-server-2013-documentation.md)

  - [Procedimentos padrão no Lync Server 2013](lync-server-2013-standard-procedures.md)

  - [Procedimentos de emergência no Lync Server 2013](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

