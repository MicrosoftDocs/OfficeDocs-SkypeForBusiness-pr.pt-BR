---
title: 'Lync Server 2013: práticas recomendadas para ambientes do Lync Server'
description: 'Lync Server 2013: práticas recomendadas para ambientes do Lync Server.'
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
ms.openlocfilehash: ae6c02621bd6506d2a1d379aeaf92b20ce3f7ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552207"
---
# <a name="best-practices-for-lync-server-2013-environments"></a>Práticas recomendadas para ambientes do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-08-04_

Os princípios gerais a seguir devem ser aplicados às operações contínuas do sistema:

  - **Entender e usar o MOF**     O MOF é um conjunto de práticas recomendadas, princípios e modelos que oferecem orientações técnicas sobre o gerenciamento de ativos de ti, como operações diárias do Lync Server 2013. As diretrizes MOF a seguir podem ajudá-lo a alcançar confiabilidade, disponibilidade, suporte e capacidade de gerenciamento de sistemas de produção críticos para os produtos da Microsoft. Para obter mais informações, consulte [Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939).

  - **Saiba mais sobre as práticas recomendadas para o Lync Server 2013**     Recomendamos que você implemente procedimentos práticos e comprovados para gerenciar o Lync Server 2013. O uso dos métodos tentado, testados e documentados de operações de gerenciamento pode ser mais eficiente do que desenvolver seus próprios métodos.

  - **Operações separadas em processos diários, semanais e mensais**     Documente as tarefas operacionais necessárias que você executará regularmente. A documentação de como realizar tarefas ajuda a garantir que suas informações sejam preservadas quando houver uma alteração no ambiente operacional, como quando novas tecnologias são implantadas ou as alterações na equipe ocorrem. Recomendamos que as tarefas operacionais sejam separadas em cargas de trabalho gerenciáveis nas quais as tarefas são realizadas diariamente, semanalmente e mensalmente. As tarefas diárias concentrarão esforços no funcionamento de um sistema e tarefas mensais se concentrarão mais em garantir a integridade de longo prazo de um sistema.
    
    Este documento pode ser usado em ambientes que implantam apenas componentes de mensagens instantâneas/presença (IM/P) ou IM/P com Enterprise Voice. Quando tarefas ou itens de lista de verificação são específicos para o Enterprise Voice, isso é mencionado e, se seu ambiente não incluir o Enterprise Voice, a parte pode ser ignorada.

  - **Implantar as ferramentas necessárias para o Lync Server 2013 operacional**     Muitas ferramentas estão disponíveis para ajudar a solucionar problemas, automatizar tarefas e ajudar a monitorar e manter o ambiente do Lync Server 2013. Definir um conjunto padrão de ferramentas para sua organização para que as tarefas executadas pela equipe de operações sejam realizadas com precisão, de forma eficiente, consistente e de forma controlada. Você também deve implementar processos para rastrear incidentes e alterações de configuração principais.

<div>

## <a name="reference"></a>Referência

Para o benefício dos leitores já não familiarizados com as noções básicas do gerenciamento de servidor em geral, fornecemos uma visão geral das práticas de gerenciamento de servidor. Os leitores já familiarizados com o gerenciamento de servidor podem optar por ignorar esta seção.

As práticas recomendadas são recomendações baseadas no conhecimento e na experiência que os profissionais de ti ganharam em vários ambientes. Eles fornecem procedimentos padrão para tarefas típicas que os administradores do Lync Server devem executar diariamente e listar as ferramentas que devem usar para gerenciar um ambiente do Lync Server.

As tarefas típicas para administradores do Lync incluem o seguinte:

  - Gerenciamento de capacidade **e disponibilidade**     Defina como e o que medir para prever os requisitos de capacidade futura e para relatar a capacidade, a confiabilidade e a disponibilidade de seus sistemas. Você deve verificar se os servidores que estão executando o Lync Server são dimensionados para lidar com a carga no sistema e se o tempo de inatividade não planejado é mantido sob os níveis definidos no contrato de nível de serviço (SLA). Além disso, você precisará atualizar o hardware para continuar atendendo aos requisitos definidos.

  - Gerenciamento **de alterações e gerenciamento**     de configuração Controlar como as alterações são feitas nos sistemas de ti. Isso deve incluir testes, comentários sobre o aplicativo e planos de contingência, documentação de todas as alterações e aprovação do gerenciamento se ocorrerem problemas. Mantenha um registro de seus ativos de software e hardware e suas configurações.

  - **Administração**     do sistema Descrever métodos padrão para realizar tarefas administrativas, como administração de banco de dados e administração de sites.

  - **Administração**     de segurança Ter uma política e um plano detalhados que protegem a confidencialidade dos dados, a integridade dos dados e a disponibilidade de dados da infraestrutura de ti. Isso inclui atividades e tarefas diárias relacionadas à manutenção e ao ajuste da infraestrutura de segurança de ti.

  - **Solução de problemas**     do sistema Métodos de estrutura de tópicos para lidar com problemas inesperados, incluindo etapas para evitar problemas semelhantes no futuro.

  - Contratos de nível de **serviço**     Mantenha um conjunto de metas para o desempenho dos sistemas de ti e meça regularmente o desempenho dessas metas.

  - **Documentação**     do Documentar procedimentos padrão, como informações de configuração e lições aprendidas, e disponibilizá-las aos membros da equipe que precisam delas. Conforme as alterações na configuração são feitas, atualize a documentação apropriadamente.

</div>

<div>

## <a name="related-sections"></a>Seções Relacionadas

Revise os tópicos a seguir referentes às operações do sistema antes de prosseguir:

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


[Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

