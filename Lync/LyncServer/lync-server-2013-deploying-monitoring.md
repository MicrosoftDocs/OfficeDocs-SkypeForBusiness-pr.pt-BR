---
title: 'Lync Server 2013: Implantando monitoramento'
description: 'Lync Server 2013: Implantando o monitoramento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1821198ddd0b4164f6932122aa9cf00ac34aada
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561537"
---
# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="2fc0f-103">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fc0f-103">Deploying monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fc0f-104">_**Última modificação do tópico:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="2fc0f-104">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="2fc0f-105">Alterações importantes foram feitas na infraestrutura de monitoramento do Microsoft Lync Server 2013, começando com o fato de que a função de servidor de monitoramento foi preterida.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-105">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="2fc0f-106">Em vez de separar funções Servidor de Monitoramento (o que normalmente exigia que as organizações definissem computadores dedicados para agir como servidores de Monitoramento), os serviços de monitoramento são agora colocados em cada servidor de Front End.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-106">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="2fc0f-107">Juntamente com outras coisas, essa alteração ajuda a:</span><span class="sxs-lookup"><span data-stu-id="2fc0f-107">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="2fc0f-108">Diminuir o número de funções de servidor necessárias ao implementar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-108">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="2fc0f-109">Neste caso, reduzir a função de servidor Servidor de Monitoramento também ajuda a reduzir custos, eliminando a necessidade de manter servidores dedicados para monitoramento.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-109">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="2fc0f-110">Reduzir a complexidade da instalação e administração do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-110">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="2fc0f-111">Colocando automaticamente os serviços de monitoramento em cada servidor de Front End, não é mais necessário instalar, configurar e gerenciar a função Servidor de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-111">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2fc0f-112">A função de servidor de arquivamento também foi preterida no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-112">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="2fc0f-113">Como os serviços de monitoramento, os serviços de arquivamento do Lync Server 2013 agora estão posicionados em cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-113">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="2fc0f-114">Isso é importante observar simplesmente porque o monitoramento e o arquivamento frequentemente compartilham a mesma instância de banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-114">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="2fc0f-115">Como você pode esperar, essas alterações têm um grande impacto sobre como os serviços de monitoramento são instalados e gerenciados.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-115">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="2fc0f-116">Por exemplo, como a função de servidor de monitoramento não existe mais, o nó do Monitoring Server foi removido do construtor de topologias do Lync Server; por sua vez, isso significa que você não usa mais o assistente de novo servidor de monitoramento do construtor de topologias para adicionar um novo servidor de monitoramento à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-116">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="2fc0f-117">(Esse assistente não existe mais.) Em vez disso, você geralmente implementará serviços de monitoramento em sua topologia executando as duas etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="2fc0f-117">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="2fc0f-118">Habilitar o monitoramento ao mesmo tempo você configura um novo pool do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-118">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="2fc0f-119">(No Lync Server 2013, o monitoramento é habilitado ou desabilitado em um pool por pool.) Observe que você pode habilitar o monitoramento de um pool sem realmente coletar dados de monitoramento, um processo explicado na seção Configuring Call Detail Recording and Quality of Experience Settings desta documentação.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-119">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="2fc0f-p107">Associando um repositório de monitoramento (ou seja, um banco de dados de monitoramento) ao novo pool. Observe que um único repositório pode ser associado a vários pools. Dependendo do número de usuários hospedados em seus pools de registradores, isso significa que não é necessário configurar um banco de dados de monitoramento separado para cada um dos seus pools. Em vez disso, um único repositório de monitoramento pode ser usado por vários pools.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="2fc0f-p108">Embora normalmente seja mais fácil habilitar o monitoramento ao mesmo tempo em que o novo pool é criado, também é possível criar um novo pool com o monitoramento desabilitado. Se o fizer, você pode usar o Construtor de Topologias mais tarde para habilitar o serviço: o Construtor de Topologias fornece uma maneira de habilitar ou desabilitar o monitoramento para um pool ou de associar um pool a um repositório de monitoramento diferente. Tenha em mente que embora não exista mais uma função Servidor de Monitoramento, ainda será necessário criar um ou mais repositórios de monitoramento: bancos de dados de backend usados para armazenar os dados reunidos pelo serviço de monitoramento. Esses bancos de dados de backend podem ser criados usando o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2fc0f-128">Se o monitoramento tiver sido habilitado para um pool, você poderá desabilitar o processo de coleta de dados de monitoramento sem ter que alterar sua topologia: o Shell de gerenciamento do Lync Server oferece uma maneira de desabilitar (e depois reabilitar) a coleta de dados da chamada (registro de detalhes das chamadas) ou de QoE (qualidade da experiência).</span><span class="sxs-lookup"><span data-stu-id="2fc0f-128">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="2fc0f-129">Para mais informações, consulte a seção Como Configurar o Registro de Detalhes de Chamadas e Configurações de Qualidade de Experiência deste documento.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-129">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="2fc0f-130">Outro aprimoramento importante do monitoramento no Lync Server 2013 é o fato de que os relatórios de monitoramento do Lync Server agora dão suporte a IPv6: os relatórios que usam o campo endereço IP exibirão endereços IPv4 ou IPv6, dependendo de: 1) a consulta SQL que está sendo usada; e 2) onde ou não o endereço IPv6 é armazenado no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-130">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2fc0f-131">Certifique-se de que o tipo de inicialização do serviço do SQL Server Agent seja automático e que o serviço SQL Server Agent esteja em execução para a instância SQL que está mantendo os bancos de dados de monitoramento, para que os trabalhos de manutenção do SQL Server de monitoramento padrão possam ser executados em sua base agendada sob o controle do serviço do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-131">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="2fc0f-132">Esta documentação o orienta durante o processo de instalação e configuração de relatórios de monitoramento e monitoramento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-132">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="2fc0f-133">A documentação fornece instruções passo a passo que o ajudarão a:</span><span class="sxs-lookup"><span data-stu-id="2fc0f-133">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="2fc0f-134">Habilitar o monitoramento na sua topologia e associar um repositório de monitoramento a um pool de Front End.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-134">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="2fc0f-135">Instale o SQL Server Reporting Services e os relatórios de monitoramento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-135">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="2fc0f-136">Relatórios de Monitoramento são relatórios pré-configurados que fornecem visões diferentes das informações armazenadas em um banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-136">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="2fc0f-137">Configurar o registro de detalhes de chamadas (CDR) e a coleta de dados de Qualidade de Experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="2fc0f-137">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="2fc0f-138">A gravação de detalhes da chamada oferece uma maneira de controlar o uso de recursos do Lync Server, como chamadas telefônicas de voz sobre IP (VoIP); mensagens instantâneas (IM); transferências de arquivos; Conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-138">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="2fc0f-139">Métricas de QoE rastreiam a qualidade de chamadas de áudio/vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, ruídos de fundo e o volume de "tremulação" (diferenças no intervalo de pacotes).</span><span class="sxs-lookup"><span data-stu-id="2fc0f-139">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="2fc0f-140">Limpar manualmente registros de CDR e/ou QoE do banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="2fc0f-140">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

