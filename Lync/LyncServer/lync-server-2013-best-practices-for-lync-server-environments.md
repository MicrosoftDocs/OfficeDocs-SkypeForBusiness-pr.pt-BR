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

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="8e085-102">Práticas recomendadas para ambientes do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e085-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e085-103">_**Tópico da última modificação:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="8e085-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="8e085-104">Os seguintes princípios gerais devem ser aplicados a operações contínuas do seu sistema:</span><span class="sxs-lookup"><span data-stu-id="8e085-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="8e085-105">**Entender e usar**   MOF MOF é uma coleção de práticas recomendadas, princípios e modelos que fornecem diretrizes técnicas de organizações sobre o gerenciamento de ativos de ti, como operações diárias do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e085-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="8e085-106">As diretrizes da MOF a seguir podem ajudá-lo a obter confiabilidade, disponibilidade, compatibilidade e capacidade de gerenciamento de sistemas de produção essenciais para os produtos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e085-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="8e085-107">Para obter mais informações, consulte [Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span><span class="sxs-lookup"><span data-stu-id="8e085-107">For more information, see [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="8e085-108">**Saiba mais sobre as práticas recomendadas para o Lync Server 2013**   recomendamos que você implemente procedimentos práticos e comprovados para gerenciar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e085-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="8e085-109">Usar métodos testados, testados e documentados de gerenciamento de operações pode ser mais eficiente do que desenvolver seus próprios métodos.</span><span class="sxs-lookup"><span data-stu-id="8e085-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="8e085-110">**Operações separadas em processos**   diários, semanais e mensais documentam as tarefas operacionais necessárias que você executará regularmente.</span><span class="sxs-lookup"><span data-stu-id="8e085-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="8e085-111">Documentar a maneira como você executa tarefas ajuda a garantir que as suas informações sejam preservadas quando houver uma alteração no ambiente operacional, como quando novas tecnologias são implantadas ou quando ocorrem mudanças na equipe.</span><span class="sxs-lookup"><span data-stu-id="8e085-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="8e085-112">Recomendamos que as tarefas operacionais sejam separadas em cargas de trabalho gerenciáveis nas quais as tarefas são realizadas diariamente, semanalmente e mensalmente.</span><span class="sxs-lookup"><span data-stu-id="8e085-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="8e085-113">As tarefas diárias concentrarão esforços no funcionamento de um sistema e as tarefas mensais se concentrarão mais em garantir a integridade de longo prazo de um sistema.</span><span class="sxs-lookup"><span data-stu-id="8e085-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="8e085-114">Este documento pode ser usado em ambientes que implantam apenas componentes de mensagem instantânea/presença (IM/P) ou IM/P com Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="8e085-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="8e085-115">Quando tarefas ou itens da lista de verificação são específicos do Enterprise Voice, isso é mencionado e, se o ambiente não inclui o Enterprise Voice, a parte pode ser ignorada.</span><span class="sxs-lookup"><span data-stu-id="8e085-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="8e085-116">**Implantar as ferramentas necessárias para operar o Lync Server 2013**   muitas ferramentas estão disponíveis para ajudar a solucionar problemas, automatizar tarefas e ajudar a monitorar e manter o ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e085-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="8e085-117">Defina um conjunto padrão de ferramentas para a sua organização para que as tarefas realizadas pela equipe de operações sejam executadas de maneira precisa, eficiente, consistente e de forma controlada.</span><span class="sxs-lookup"><span data-stu-id="8e085-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="8e085-118">Você também deve implementar processos para acompanhar incidentes e alterações de configuração importantes.</span><span class="sxs-lookup"><span data-stu-id="8e085-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="8e085-119">Referência</span><span class="sxs-lookup"><span data-stu-id="8e085-119">Reference</span></span>

<span data-ttu-id="8e085-120">Para o benefício dos leitores ainda não familiarizados com as noções básicas de gerenciamento de servidor em geral, fornecemos uma visão geral das práticas de gerenciamento de servidor.</span><span class="sxs-lookup"><span data-stu-id="8e085-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="8e085-121">Os leitores já familiarizados com o gerenciamento de servidor podem optar por ignorar esta seção.</span><span class="sxs-lookup"><span data-stu-id="8e085-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="8e085-122">As práticas recomendadas são recomendações que se baseiam no conhecimento e na experiência que os profissionais de ti obtiveram em vários ambientes.</span><span class="sxs-lookup"><span data-stu-id="8e085-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="8e085-123">Eles fornecem procedimentos padrão para tarefas típicas que os administradores do Lync Server devem executar diariamente e listar as ferramentas que elas devem usar para gerenciar um ambiente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8e085-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="8e085-124">As tarefas típicas para administradores do Lync incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e085-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="8e085-125">**O gerenciamento**   de capacidade e disponibilidade define como e o que medir para prever requisitos de capacidade futuros e para informar sobre a capacidade, a confiabilidade e a disponibilidade de seus sistemas.</span><span class="sxs-lookup"><span data-stu-id="8e085-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="8e085-126">Você deve verificar se servidores que estão executando o Lync Server são dimensionados para manipular a carga no sistema e se o tempo de inatividade não planejado é mantido nos níveis definidos no contrato de nível de serviço (SLA).</span><span class="sxs-lookup"><span data-stu-id="8e085-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="8e085-127">Além disso, você precisará atualizar o hardware para continuar a atender aos requisitos definidos.</span><span class="sxs-lookup"><span data-stu-id="8e085-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="8e085-128">**Gerenciamento de alterações e gerenciamento de configuração**   controle como as alterações são feitas nos sistemas de ti.</span><span class="sxs-lookup"><span data-stu-id="8e085-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="8e085-129">Isso deve incluir testes, comentários sobre o aplicativo e planos de contingência, documentação de todas as alterações e aprovação do gerenciamento se ocorrerem problemas.</span><span class="sxs-lookup"><span data-stu-id="8e085-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="8e085-130">Mantenha um registro dos ativos de software e hardware e suas configurações.</span><span class="sxs-lookup"><span data-stu-id="8e085-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="8e085-131">\*\*\*\*   Estrutura de tópicos de administração do sistema métodos padrão para realizar tarefas administrativas, como administração de banco de dados e administração de sites.</span><span class="sxs-lookup"><span data-stu-id="8e085-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="8e085-132">**A administração**   de segurança tem uma política e um plano detalhados que protegem a confidencialidade dos dados, a integridade dos dados e a disponibilidade de dados da infraestrutura de ti.</span><span class="sxs-lookup"><span data-stu-id="8e085-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="8e085-133">Isso inclui atividades e tarefas do dia-a-dia relacionadas à manutenção e ajuste da infra-estrutura de segurança de ti.</span><span class="sxs-lookup"><span data-stu-id="8e085-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="8e085-134">**Solução de problemas de sistema**   descreve métodos para lidar com problemas inesperados, incluindo etapas para evitar problemas semelhantes no futuro.</span><span class="sxs-lookup"><span data-stu-id="8e085-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="8e085-135">**Os contratos**   de nível de serviço mantêm um conjunto de metas para o desempenho dos sistemas de ti e medem regularmente o desempenho contra essas metas.</span><span class="sxs-lookup"><span data-stu-id="8e085-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="8e085-136">**Documentação**   documentar procedimentos padrão, como informações de configuração e aulas aprendidas, e disponibilizá-las para os membros da equipe que precisam delas.</span><span class="sxs-lookup"><span data-stu-id="8e085-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="8e085-137">Quando forem feitas alterações na configuração, atualize a documentação de acordo com isso.</span><span class="sxs-lookup"><span data-stu-id="8e085-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="8e085-138">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="8e085-138">Related Sections</span></span>

<span data-ttu-id="8e085-139">Examine os tópicos a seguir em relação às operações do sistema antes de prosseguir:</span><span class="sxs-lookup"><span data-stu-id="8e085-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="8e085-140">Gerenciamento de capacidade e disponibilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e085-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="8e085-141">Gerenciamento de alterações no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e085-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="8e085-142">Gerenciamento de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e085-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="8e085-143">Administração do sistema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e085-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="8e085-144">Contratos de nível de serviço no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e085-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="8e085-145">Documentação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e085-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="8e085-146">Procedimentos padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e085-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="8e085-147">Procedimentos de emergência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e085-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e085-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e085-148">See Also</span></span>


[<span data-ttu-id="8e085-149">Microsoft Operations Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="8e085-149">Microsoft Operations Framework 4.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

