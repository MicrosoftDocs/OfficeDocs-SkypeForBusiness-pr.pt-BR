---
title: 'Lync Server 2013: Implantando monitoramento'
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
ms.openlocfilehash: 49d62537f91145803f60f51c18b86816a0af657f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="f76f3-102">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f76f3-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f76f3-103">_**Última modificação do tópico:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="f76f3-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="f76f3-104">Alterações importantes foram feitas na infraestrutura de monitoramento do Microsoft Lync Server 2013, começando com o fato de que a função de servidor de monitoramento foi preterida.</span><span class="sxs-lookup"><span data-stu-id="f76f3-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="f76f3-105">Em vez de separar funções Servidor de Monitoramento (o que normalmente exigia que as organizações definissem computadores dedicados para agir como servidores de Monitoramento), os serviços de monitoramento são agora colocados em cada servidor de Front End.</span><span class="sxs-lookup"><span data-stu-id="f76f3-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="f76f3-106">Juntamente com outras coisas, essa alteração ajuda a:</span><span class="sxs-lookup"><span data-stu-id="f76f3-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="f76f3-107">Diminuir o número de funções de servidor necessárias ao implementar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f76f3-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="f76f3-108">Neste caso, reduzir a função de servidor Servidor de Monitoramento também ajuda a reduzir custos, eliminando a necessidade de manter servidores dedicados para monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f76f3-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="f76f3-109">Reduzir a complexidade da instalação e administração do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f76f3-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="f76f3-110">Colocando automaticamente os serviços de monitoramento em cada servidor de Front End, não é mais necessário instalar, configurar e gerenciar a função Servidor de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f76f3-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f76f3-111">A função de servidor de arquivamento também foi preterida no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f76f3-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="f76f3-112">Como os serviços de monitoramento, os serviços de arquivamento do Lync Server 2013 agora estão posicionados em cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f76f3-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="f76f3-113">Isso é importante observar simplesmente porque o monitoramento e o arquivamento frequentemente compartilham a mesma instância de banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f76f3-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="f76f3-114">Como você pode esperar, essas alterações têm um grande impacto sobre como os serviços de monitoramento são instalados e gerenciados.</span><span class="sxs-lookup"><span data-stu-id="f76f3-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="f76f3-115">Por exemplo, como a função de servidor de monitoramento não existe mais, o nó do Monitoring Server foi removido do construtor de topologias do Lync Server; por sua vez, isso significa que você não usa mais o assistente de novo servidor de monitoramento do construtor de topologias para adicionar um novo servidor de monitoramento à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="f76f3-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="f76f3-116">(Esse assistente não existe mais.) Em vez disso, você geralmente implementará serviços de monitoramento em sua topologia executando as duas etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="f76f3-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="f76f3-117">Habilitar o monitoramento ao mesmo tempo você configura um novo pool do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f76f3-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="f76f3-118">(No Lync Server 2013, o monitoramento é habilitado ou desabilitado em um pool por pool.) Observe que você pode habilitar o monitoramento de um pool sem realmente coletar dados de monitoramento, um processo explicado na seção Configuring Call Detail Recording and Quality of Experience Settings desta documentação.</span><span class="sxs-lookup"><span data-stu-id="f76f3-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="f76f3-p107">Associando um repositório de monitoramento (ou seja, um banco de dados de monitoramento) ao novo pool. Observe que um único repositório pode ser associado a vários pools. Dependendo do número de usuários hospedados em seus pools de registradores, isso significa que não é necessário configurar um banco de dados de monitoramento separado para cada um dos seus pools. Em vez disso, um único repositório de monitoramento pode ser usado por vários pools.</span><span class="sxs-lookup"><span data-stu-id="f76f3-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="f76f3-p108">Embora normalmente seja mais fácil habilitar o monitoramento ao mesmo tempo em que o novo pool é criado, também é possível criar um novo pool com o monitoramento desabilitado. Se o fizer, você pode usar o Construtor de Topologias mais tarde para habilitar o serviço: o Construtor de Topologias fornece uma maneira de habilitar ou desabilitar o monitoramento para um pool ou de associar um pool a um repositório de monitoramento diferente. Tenha em mente que embora não exista mais uma função Servidor de Monitoramento, ainda será necessário criar um ou mais repositórios de monitoramento: bancos de dados de backend usados para armazenar os dados reunidos pelo serviço de monitoramento. Esses bancos de dados de backend podem ser criados usando o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="f76f3-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f76f3-127">Se o monitoramento tiver sido habilitado para um pool, você poderá desabilitar o processo de coleta de dados de monitoramento sem precisar alterar sua topologia: o Shell de gerenciamento do Lync Server oferece uma maneira de desabilitar (e depois reabilitar) o CDR (registro de detalhes das chamadas) ou a qualidade coleta de dados da QoE (of Experience).</span><span class="sxs-lookup"><span data-stu-id="f76f3-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="f76f3-128">Para mais informações, consulte a seção Como Configurar o Registro de Detalhes de Chamadas e Configurações de Qualidade de Experiência deste documento.</span><span class="sxs-lookup"><span data-stu-id="f76f3-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="f76f3-129">Outro aprimoramento importante do monitoramento no Lync Server 2013 é o fato de que os relatórios de monitoramento do Lync Server agora dão suporte a IPv6: os relatórios que usam o campo endereço IP exibirão endereços IPv4 ou IPv6, dependendo de: 1) a consulta SQL que está sendo usada; e 2) onde ou não o endereço IPv6 é armazenado no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f76f3-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f76f3-130">Certifique-se de que o tipo de inicialização do serviço SQL Server Agent seja automático e que o serviço SQL Server Agent esteja em execução para a instância SQL que está mantendo os bancos de dados de monitoramento, para que os trabalhos de manutenção do SQL Server de monitoramento padrão possam ser executados na base agendada sob o controle do serviço do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="f76f3-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="f76f3-131">Esta documentação o orienta durante o processo de instalação e configuração de relatórios de monitoramento e monitoramento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f76f3-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="f76f3-132">A documentação fornece instruções passo a passo que o ajudarão a:</span><span class="sxs-lookup"><span data-stu-id="f76f3-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="f76f3-133">Habilitar o monitoramento na sua topologia e associar um repositório de monitoramento a um pool de Front End.</span><span class="sxs-lookup"><span data-stu-id="f76f3-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="f76f3-134">Instale o SQL Server Reporting Services e os relatórios de monitoramento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f76f3-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="f76f3-135">Relatórios de Monitoramento são relatórios pré-configurados que fornecem visões diferentes das informações armazenadas em um banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f76f3-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="f76f3-136">Configurar o registro de detalhes de chamadas (CDR) e a coleta de dados de Qualidade de Experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="f76f3-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="f76f3-137">A gravação de detalhes da chamada oferece uma maneira de controlar o uso de recursos do Lync Server, como chamadas telefônicas de voz sobre IP (VoIP); mensagens instantâneas (IM); transferências de arquivos; Conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f76f3-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="f76f3-138">Métricas de QoE rastreiam a qualidade de chamadas de áudio/vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, ruídos de fundo e o volume de "tremulação" (diferenças no intervalo de pacotes).</span><span class="sxs-lookup"><span data-stu-id="f76f3-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="f76f3-139">Limpar manualmente registros de CDR e/ou QoE do banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f76f3-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

