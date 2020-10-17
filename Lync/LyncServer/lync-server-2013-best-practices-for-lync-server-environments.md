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
# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="e6d92-103">Práticas recomendadas para ambientes do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d92-103">Best practices for Lync Server 2013 environments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6d92-104">_**Última modificação do tópico:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="e6d92-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="e6d92-105">Os princípios gerais a seguir devem ser aplicados às operações contínuas do sistema:</span><span class="sxs-lookup"><span data-stu-id="e6d92-105">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="e6d92-106">**Entender e usar o MOF**     O MOF é um conjunto de práticas recomendadas, princípios e modelos que oferecem orientações técnicas sobre o gerenciamento de ativos de ti, como operações diárias do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6d92-106">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="e6d92-107">As diretrizes MOF a seguir podem ajudá-lo a alcançar confiabilidade, disponibilidade, suporte e capacidade de gerenciamento de sistemas de produção críticos para os produtos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e6d92-107">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="e6d92-108">Para obter mais informações, consulte [Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span><span class="sxs-lookup"><span data-stu-id="e6d92-108">For more information, see [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="e6d92-109">**Saiba mais sobre as práticas recomendadas para o Lync Server 2013**     Recomendamos que você implemente procedimentos práticos e comprovados para gerenciar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6d92-109">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="e6d92-110">O uso dos métodos tentado, testados e documentados de operações de gerenciamento pode ser mais eficiente do que desenvolver seus próprios métodos.</span><span class="sxs-lookup"><span data-stu-id="e6d92-110">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="e6d92-111">**Operações separadas em processos diários, semanais e mensais**     Documente as tarefas operacionais necessárias que você executará regularmente.</span><span class="sxs-lookup"><span data-stu-id="e6d92-111">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="e6d92-112">A documentação de como realizar tarefas ajuda a garantir que suas informações sejam preservadas quando houver uma alteração no ambiente operacional, como quando novas tecnologias são implantadas ou as alterações na equipe ocorrem.</span><span class="sxs-lookup"><span data-stu-id="e6d92-112">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="e6d92-113">Recomendamos que as tarefas operacionais sejam separadas em cargas de trabalho gerenciáveis nas quais as tarefas são realizadas diariamente, semanalmente e mensalmente.</span><span class="sxs-lookup"><span data-stu-id="e6d92-113">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="e6d92-114">As tarefas diárias concentrarão esforços no funcionamento de um sistema e tarefas mensais se concentrarão mais em garantir a integridade de longo prazo de um sistema.</span><span class="sxs-lookup"><span data-stu-id="e6d92-114">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="e6d92-115">Este documento pode ser usado em ambientes que implantam apenas componentes de mensagens instantâneas/presença (IM/P) ou IM/P com Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e6d92-115">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="e6d92-116">Quando tarefas ou itens de lista de verificação são específicos para o Enterprise Voice, isso é mencionado e, se seu ambiente não incluir o Enterprise Voice, a parte pode ser ignorada.</span><span class="sxs-lookup"><span data-stu-id="e6d92-116">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="e6d92-117">**Implantar as ferramentas necessárias para o Lync Server 2013 operacional**     Muitas ferramentas estão disponíveis para ajudar a solucionar problemas, automatizar tarefas e ajudar a monitorar e manter o ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6d92-117">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="e6d92-118">Definir um conjunto padrão de ferramentas para sua organização para que as tarefas executadas pela equipe de operações sejam realizadas com precisão, de forma eficiente, consistente e de forma controlada.</span><span class="sxs-lookup"><span data-stu-id="e6d92-118">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="e6d92-119">Você também deve implementar processos para rastrear incidentes e alterações de configuração principais.</span><span class="sxs-lookup"><span data-stu-id="e6d92-119">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="e6d92-120">Referência</span><span class="sxs-lookup"><span data-stu-id="e6d92-120">Reference</span></span>

<span data-ttu-id="e6d92-121">Para o benefício dos leitores já não familiarizados com as noções básicas do gerenciamento de servidor em geral, fornecemos uma visão geral das práticas de gerenciamento de servidor.</span><span class="sxs-lookup"><span data-stu-id="e6d92-121">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="e6d92-122">Os leitores já familiarizados com o gerenciamento de servidor podem optar por ignorar esta seção.</span><span class="sxs-lookup"><span data-stu-id="e6d92-122">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="e6d92-123">As práticas recomendadas são recomendações baseadas no conhecimento e na experiência que os profissionais de ti ganharam em vários ambientes.</span><span class="sxs-lookup"><span data-stu-id="e6d92-123">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="e6d92-124">Eles fornecem procedimentos padrão para tarefas típicas que os administradores do Lync Server devem executar diariamente e listar as ferramentas que devem usar para gerenciar um ambiente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6d92-124">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="e6d92-125">As tarefas típicas para administradores do Lync incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6d92-125">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="e6d92-126">Gerenciamento de capacidade **e disponibilidade**     Defina como e o que medir para prever os requisitos de capacidade futura e para relatar a capacidade, a confiabilidade e a disponibilidade de seus sistemas.</span><span class="sxs-lookup"><span data-stu-id="e6d92-126">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="e6d92-127">Você deve verificar se os servidores que estão executando o Lync Server são dimensionados para lidar com a carga no sistema e se o tempo de inatividade não planejado é mantido sob os níveis definidos no contrato de nível de serviço (SLA).</span><span class="sxs-lookup"><span data-stu-id="e6d92-127">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="e6d92-128">Além disso, você precisará atualizar o hardware para continuar atendendo aos requisitos definidos.</span><span class="sxs-lookup"><span data-stu-id="e6d92-128">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="e6d92-129">Gerenciamento **de alterações e gerenciamento**     de configuração Controlar como as alterações são feitas nos sistemas de ti.</span><span class="sxs-lookup"><span data-stu-id="e6d92-129">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="e6d92-130">Isso deve incluir testes, comentários sobre o aplicativo e planos de contingência, documentação de todas as alterações e aprovação do gerenciamento se ocorrerem problemas.</span><span class="sxs-lookup"><span data-stu-id="e6d92-130">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="e6d92-131">Mantenha um registro de seus ativos de software e hardware e suas configurações.</span><span class="sxs-lookup"><span data-stu-id="e6d92-131">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="e6d92-132">**Administração**     do sistema Descrever métodos padrão para realizar tarefas administrativas, como administração de banco de dados e administração de sites.</span><span class="sxs-lookup"><span data-stu-id="e6d92-132">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="e6d92-133">**Administração**     de segurança Ter uma política e um plano detalhados que protegem a confidencialidade dos dados, a integridade dos dados e a disponibilidade de dados da infraestrutura de ti.</span><span class="sxs-lookup"><span data-stu-id="e6d92-133">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="e6d92-134">Isso inclui atividades e tarefas diárias relacionadas à manutenção e ao ajuste da infraestrutura de segurança de ti.</span><span class="sxs-lookup"><span data-stu-id="e6d92-134">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="e6d92-135">**Solução de problemas**     do sistema Métodos de estrutura de tópicos para lidar com problemas inesperados, incluindo etapas para evitar problemas semelhantes no futuro.</span><span class="sxs-lookup"><span data-stu-id="e6d92-135">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="e6d92-136">Contratos de nível de **serviço**     Mantenha um conjunto de metas para o desempenho dos sistemas de ti e meça regularmente o desempenho dessas metas.</span><span class="sxs-lookup"><span data-stu-id="e6d92-136">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="e6d92-137">**Documentação**     do Documentar procedimentos padrão, como informações de configuração e lições aprendidas, e disponibilizá-las aos membros da equipe que precisam delas.</span><span class="sxs-lookup"><span data-stu-id="e6d92-137">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="e6d92-138">Conforme as alterações na configuração são feitas, atualize a documentação apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="e6d92-138">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="e6d92-139">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="e6d92-139">Related Sections</span></span>

<span data-ttu-id="e6d92-140">Revise os tópicos a seguir referentes às operações do sistema antes de prosseguir:</span><span class="sxs-lookup"><span data-stu-id="e6d92-140">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="e6d92-141">Gerenciamento de capacidade e disponibilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d92-141">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="e6d92-142">Gerenciamento de alterações no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d92-142">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="e6d92-143">Gerenciamento de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d92-143">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="e6d92-144">Administração do sistema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d92-144">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="e6d92-145">Contratos de nível de serviço no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d92-145">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="e6d92-146">Documentação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d92-146">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="e6d92-147">Procedimentos padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d92-147">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="e6d92-148">Procedimentos de emergência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d92-148">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6d92-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="e6d92-149">See Also</span></span>


[<span data-ttu-id="e6d92-150">Microsoft Operations Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="e6d92-150">Microsoft Operations Framework 4.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

