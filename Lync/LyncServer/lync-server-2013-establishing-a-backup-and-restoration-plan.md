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
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="37efb-103">Estabelecendo um plano de backup e restauração para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37efb-103">Establishing a backup and restoration plan for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37efb-104">_**Última modificação do tópico:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="37efb-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="37efb-105">Criar um plano de backup e restauração envolve as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="37efb-105">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="37efb-106">Desenvolver o plano.</span><span class="sxs-lookup"><span data-stu-id="37efb-106">Developing the plan.</span></span>

  - <span data-ttu-id="37efb-107">Implementar o plano.</span><span class="sxs-lookup"><span data-stu-id="37efb-107">Implementing the plan.</span></span>

  - <span data-ttu-id="37efb-108">Manutenção do plano.</span><span class="sxs-lookup"><span data-stu-id="37efb-108">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="37efb-109">Como desenvolver um plano de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="37efb-109">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="37efb-110">Depois de desenvolver sua estratégia de backup e restauração para o Lync Server, use-a para documentar um plano detalhado de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="37efb-110">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="37efb-111">Seu plano deve transmitir claramente as prioridades e requisitos para fazer backup de dados e configurações.</span><span class="sxs-lookup"><span data-stu-id="37efb-111">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="37efb-112">Você pode usar as informações [para estabelecer uma estratégia de backup e restauração para o Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) e as planilhas em [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) para facilitar a documentação da sua estratégia.</span><span class="sxs-lookup"><span data-stu-id="37efb-112">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="37efb-113">Seu plano também deve conter critérios para decidir quando e como restaurar serviços.</span><span class="sxs-lookup"><span data-stu-id="37efb-113">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="37efb-114">À medida que desenvolver seu plano, você precisará considerar e fazer a conta do seguinte:</span><span class="sxs-lookup"><span data-stu-id="37efb-114">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="37efb-115">Como recuperará servidores no novo hardware.</span><span class="sxs-lookup"><span data-stu-id="37efb-115">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="37efb-116">Como recuperará serviços que exigem ações da parte de várias áreas de negócio ou departamentos.</span><span class="sxs-lookup"><span data-stu-id="37efb-116">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="37efb-117">Como poderá obter servidores sobressalentes de forma rápida.</span><span class="sxs-lookup"><span data-stu-id="37efb-117">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="37efb-118">O tempo necessário para recuperar usando sua estratégia.</span><span class="sxs-lookup"><span data-stu-id="37efb-118">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="37efb-119">Considere os requisitos da sua organização para o objetivo de tempo de recuperação (RTO).</span><span class="sxs-lookup"><span data-stu-id="37efb-119">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="37efb-120">Modifique os procedimentos de backup e restauração neste tópico, adicionando e excluindo procedimentos conforme apropriado, para refletir os servidores e componentes em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="37efb-120">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="37efb-121">Você também pode adicionar detalhes apropriados, como o agendamento de backup, aos procedimentos adequados para garantir que as informações não sejam ignoradas.</span><span class="sxs-lookup"><span data-stu-id="37efb-121">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37efb-122">É uma boa prática criar scripts para o máximo de etapas possíveis, para ajudar a garantir a qualidade e a reprodutibilidade de procedimentos.</span><span class="sxs-lookup"><span data-stu-id="37efb-122">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="37efb-123">Em seu plano, especifique quem é responsável por analisar o plano, que é responsável por testar e validar quaisquer novos procedimentos ou ferramentas e quem deve aprovar qualquer alteração no plano e nos procedimentos relacionados.</span><span class="sxs-lookup"><span data-stu-id="37efb-123">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="37efb-124">Para garantir que seu plano de backup e restauração atenda totalmente a todas as metas e prioridades estabelecidas, obtenha a aprovação dos tomadores de decisões de negócios e dos tomadores de decisões técnicos apropriados em sua organização antes de implementar o plano.</span><span class="sxs-lookup"><span data-stu-id="37efb-124">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="37efb-125">Como implementar o plano de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="37efb-125">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="37efb-126">A implementação de um plano de backup e restauração exige as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="37efb-126">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="37efb-127">Testar e validar o plano.</span><span class="sxs-lookup"><span data-stu-id="37efb-127">Testing and validating the plan.</span></span>

  - <span data-ttu-id="37efb-128">Comunicar o plano.</span><span class="sxs-lookup"><span data-stu-id="37efb-128">Communicating the plan.</span></span>

  - <span data-ttu-id="37efb-129">Validar as operações de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="37efb-129">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="37efb-130">Testar e validar o plano</span><span class="sxs-lookup"><span data-stu-id="37efb-130">Testing and Validating the Plan</span></span>

<span data-ttu-id="37efb-131">Os procedimentos descritos aqui foram testados e validados em um ambiente de laboratório.</span><span class="sxs-lookup"><span data-stu-id="37efb-131">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="37efb-132">Para certificar-se de que esses ou outros procedimentos funcionam em seu ambiente, você deve testar e validar cada procedimento que pretende implementar.</span><span class="sxs-lookup"><span data-stu-id="37efb-132">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="37efb-133">Conclua o teste e a validação antes de enviar seu plano para aprovação final.</span><span class="sxs-lookup"><span data-stu-id="37efb-133">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="37efb-134">Comunicar o plano</span><span class="sxs-lookup"><span data-stu-id="37efb-134">Communicating the Plan</span></span>

<span data-ttu-id="37efb-135">Seu plano de backup e restauração deve descrever claramente quem implementará os procedimentos e as instruções passo a passo para executá-los.</span><span class="sxs-lookup"><span data-stu-id="37efb-135">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="37efb-136">Você deve certificar-se de que todos os responsáveis por qualquer aspecto do backup e da restauração compreendam o plano, como ele deve ser implementado e qual é sua função.</span><span class="sxs-lookup"><span data-stu-id="37efb-136">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="37efb-137">Isso inclui todos os requisitos da implementação para:</span><span class="sxs-lookup"><span data-stu-id="37efb-137">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="37efb-138">Backup do pool e do servidor.</span><span class="sxs-lookup"><span data-stu-id="37efb-138">Pool and server backup.</span></span>

  - <span data-ttu-id="37efb-139">Restauração do serviço.</span><span class="sxs-lookup"><span data-stu-id="37efb-139">Restoration of service.</span></span>

<span data-ttu-id="37efb-140">**Backup do pool e de servidores**</span><span class="sxs-lookup"><span data-stu-id="37efb-140">**Pool and server backup**</span></span>

<span data-ttu-id="37efb-p106">O plano de backup e restauração deve incluir todas as informações necessárias para concluir os procedimentos de backup continuamente. As principais informações a serem comunicadas aos membros da equipe responsável incluem:</span><span class="sxs-lookup"><span data-stu-id="37efb-p106">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis. The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="37efb-143">Equipe ou pessoa (especificada como uma pessoa ou função) responsável por fazer o backup de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="37efb-143">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="37efb-144">Agendas específicas para o backup de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="37efb-144">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="37efb-145">Locais de backup para cada tipo de dados (configurações, banco de dados e compartilhamentos de arquivos).</span><span class="sxs-lookup"><span data-stu-id="37efb-145">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="37efb-146">Procedimentos de backup a serem usados, incluindo as ferramentas necessárias para concluir cada procedimento.</span><span class="sxs-lookup"><span data-stu-id="37efb-146">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="37efb-147">Informações necessárias para concluir backups, conforme abordado em [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="37efb-147">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="37efb-148">Métodos de validação a serem usados para ajudar a garantir que os dados e as configurações sejam incluídos no backup e disponíveis para restauração, o que pode incluir auditorias periódicas e restaurações de teste.</span><span class="sxs-lookup"><span data-stu-id="37efb-148">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="37efb-149">**Restauração de serviços**</span><span class="sxs-lookup"><span data-stu-id="37efb-149">**Restoration of service**</span></span>

<span data-ttu-id="37efb-150">O plano de backup e restauração deve incluir todas as informações necessárias para restaurar o serviço, no caso de um ou mais servidores experimentarem uma perda que torna o serviço indisponível.</span><span class="sxs-lookup"><span data-stu-id="37efb-150">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="37efb-151">As principais informações a serem comunicadas aos membros da equipe responsável incluem:</span><span class="sxs-lookup"><span data-stu-id="37efb-151">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="37efb-152">Equipe ou pessoa (especificado como indivíduo ou função) responsável por determinar quando a restauração de serviços será necessária e os procedimentos a serem usados para restaurá-los e, também, a equipe ou pessoa responsável por implementar procedimentos para cada cenário de restauração.</span><span class="sxs-lookup"><span data-stu-id="37efb-152">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="37efb-153">Critérios para determinar quais procedimentos de restauração são mais apropriados para uma situação específica.</span><span class="sxs-lookup"><span data-stu-id="37efb-153">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="37efb-154">Estimativas de tempo para restauração de RTO (objetivo de tempo de recuperação) e de serviço em cada cenário de restauração.</span><span class="sxs-lookup"><span data-stu-id="37efb-154">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="37efb-155">Procedimentos de restauração a serem usados, incluindo as ferramentas necessárias para concluir cada um deles.</span><span class="sxs-lookup"><span data-stu-id="37efb-155">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="37efb-156">As informações necessárias para restaurar dados e configurações.</span><span class="sxs-lookup"><span data-stu-id="37efb-156">Information required to restore data and settings.</span></span> <span data-ttu-id="37efb-157">As planilhas são fornecidas em [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="37efb-157">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="37efb-158">Como validar as operações de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="37efb-158">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="37efb-159">Depois de concluir os esforços iniciais de backup em seu ambiente de produção e a intervalos específicos (conforme descrito em seu plano de backup e restauração), você deve verificar se:</span><span class="sxs-lookup"><span data-stu-id="37efb-159">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="37efb-160">Os backups estão ocorrendo conforme o solicitado.</span><span class="sxs-lookup"><span data-stu-id="37efb-160">Backups are occurring as required.</span></span>

  - <span data-ttu-id="37efb-161">Dados de backup e configurações estão acessíveis.</span><span class="sxs-lookup"><span data-stu-id="37efb-161">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="37efb-162">Os procedimentos de restauração podem ser executados dentro dos tempos de objetivo de tempo de recuperação (RTO) especificados no plano de backup e restauração, e os resultados atendem a todos os requisitos de negócios.</span><span class="sxs-lookup"><span data-stu-id="37efb-162">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="37efb-163">Planilhas de backup foram preenchidas e verificadas e estão armazenadas em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="37efb-163">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="37efb-164">Essas planilhas são fornecidas em [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="37efb-164">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="37efb-165">Procedimentos de restauração foram testados e verificados se funcionam conforme o esperado, de acordo com o especificado no plano.</span><span class="sxs-lookup"><span data-stu-id="37efb-165">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="37efb-166">Como manter o plano de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="37efb-166">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="37efb-167">Uma topologia do Lync Server é um ambiente dinâmico que muda com sua organização.</span><span class="sxs-lookup"><span data-stu-id="37efb-167">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="37efb-168">Reavalie o plano de backup e restauração à medida que sua organização mudar e revise-o periodicamente para garantir que ele continue atendendo às necessidades da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="37efb-168">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

