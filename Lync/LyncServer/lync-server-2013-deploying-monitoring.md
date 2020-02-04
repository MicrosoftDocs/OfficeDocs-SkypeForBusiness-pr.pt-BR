---
title: 'Lync Server 2013: Implantando o monitoramento'
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
ms.openlocfilehash: 637897bce0a160a8cc3b199ec6aee3ffd7375852
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="42d4b-102">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42d4b-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42d4b-103">_**Tópico da última modificação:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="42d4b-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="42d4b-104">Alterações importantes foram feitas na infraestrutura de monitoramento do Microsoft Lync Server 2013, começando com o fato de que a função de servidor de monitoramento foi preterida.</span><span class="sxs-lookup"><span data-stu-id="42d4b-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="42d4b-105">Em vez de funções separadas de monitoração de servidor (que normalmente são necessárias às organizações para configurar computadores dedicados para atuar como servidores de monitoramento), os serviços de monitoramento são agora posicionados em cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="42d4b-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="42d4b-106">Entre outras coisas, essa alteração ajuda a:</span><span class="sxs-lookup"><span data-stu-id="42d4b-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="42d4b-107">Diminua o número de funções de servidor necessárias ao implementar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42d4b-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="42d4b-108">Nesse caso, decrementar a função de servidor do Monitoring Server também ajuda a reduzir os custos, eliminando a necessidade de manter os servidores dedicados para monitoramento.</span><span class="sxs-lookup"><span data-stu-id="42d4b-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="42d4b-109">Reduzir a complexidade da instalação e da administração do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42d4b-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="42d4b-110">Posicionando automaticamente os serviços de monitoramento em cada servidor front-end que você não precisa mais instalar, configurar e gerenciar a função do servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="42d4b-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42d4b-111">A função de servidor de arquivamento também foi substituída no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42d4b-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="42d4b-112">Como os serviços de monitoramento, os serviços de arquivamento do Lync Server 2013 agora são posicionados em cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="42d4b-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="42d4b-113">Isso é importante observar simplesmente porque o monitoramento e o arquivamento muitas vezes compartilham a mesma instância do banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42d4b-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="42d4b-114">Como você pode esperar, essas alterações têm um grande impacto sobre como os serviços de monitoramento são instalados e gerenciados.</span><span class="sxs-lookup"><span data-stu-id="42d4b-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="42d4b-115">Por exemplo, como a função de servidor de monitoramento não existe mais, o nó do servidor de monitoramento foi removido do construtor de topologias do Lync Server; por sua vez, isso significa que você não usa mais o novo assistente do construtor de topologias para adicionar um novo servidor de monitoramento à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="42d4b-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="42d4b-116">(Esse assistente não existe mais.) Em vez disso, você geralmente implementará serviços de monitoramento na sua topologia completando as duas etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="42d4b-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="42d4b-117">Habilitar o monitoramento ao mesmo tempo em que você configura um novo pool do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42d4b-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="42d4b-118">(No Lync Server 2013, o monitoramento é habilitado ou desabilitado em uma base de pool por pool.) Observe que você pode habilitar o monitoramento de um pool sem coletar dados de monitoramento, um processo explicado na seção como configurar a gravação de detalhes da chamada e as configurações de qualidade da experiência desta documentação.</span><span class="sxs-lookup"><span data-stu-id="42d4b-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="42d4b-p107">Associando um repositório de monitoramento (ou seja, um banco de dados de monitoramento) ao novo pool. Observe que um único repositório pode ser associado a vários pools. Dependendo do número de usuários hospedados em seus pools de registradores, isso significa que não é necessário configurar um banco de dados de monitoramento separado para cada um dos seus pools. Em vez disso, um único repositório de monitoramento pode ser usado por vários pools.</span><span class="sxs-lookup"><span data-stu-id="42d4b-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="42d4b-123">Embora normalmente seja mais fácil habilitar o monitoramento ao mesmo tempo em que o novo pool é criado, também é possível criar um novo pool com o monitoramento desabilitado.</span><span class="sxs-lookup"><span data-stu-id="42d4b-123">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled.</span></span> <span data-ttu-id="42d4b-124">Se o fizer, você pode usar o Construtor de Topologias mais tarde para habilitar o serviço: o Construtor de Topologias fornece uma maneira de habilitar ou desabilitar o monitoramento para um pool ou de associar um pool a um repositório de monitoramento diferente.</span><span class="sxs-lookup"><span data-stu-id="42d4b-124">If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store.</span></span> <span data-ttu-id="42d4b-125">Lembre-se de que, mesmo que não haja mais uma função de servidor de monitoramento, você ainda precisará criar uma ou mais lojas de monitoramento: bancos de dados back-end usados para armazenar os dados coletados pelo serviço de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="42d4b-125">Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service.</span></span> <span data-ttu-id="42d4b-126">Esses bancos de dados back-end podem ser criados usando o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="42d4b-126">These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42d4b-127">Se o monitoramento tiver sido habilitado para um pool, você poderá desabilitar o processo de coleta de dados de monitoramento sem precisar alterar a topologia: o Shell de gerenciamento do Lync Server permite que você desative (e, em seguida, habilite novamente) registro de detalhes da chamada (CDR) ou qualidade coleta de dados da experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="42d4b-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="42d4b-128">Para obter mais informações, consulte a seção Como Configurar o Registro de Detalhes das Chamadas e Configurações de Qualidade da Experiência deste documento.</span><span class="sxs-lookup"><span data-stu-id="42d4b-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="42d4b-129">Outro aprimoramento importante para monitorar no Lync Server 2013 é o fato de que os relatórios de monitoramento do Lync Server agora dão suporte a IPv6: os relatórios que usam o campo endereço IP exibirão endereços IPv4 ou IPv6, dependendo de: 1) a consulta SQL sendo usada; e 2) onde ou não o endereço IPv6 está armazenado no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="42d4b-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42d4b-130">Verifique se o Tipo de inicialização do serviço SQL Server Agent é Automático e se o serviço SQL Server Agent está sendo executado para a Instância SQL que está mantendo os bancos de dados de Monitoramento para que os Trabalhos de manutenção do SQL Server de monitoramento padrão possam ser executados com base em seu agendamento sob o controle do Serviço SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="42d4b-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="42d4b-131">Esta documentação descreve o processo de instalação e configuração de relatórios de monitoramento e monitoramento para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42d4b-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="42d4b-132">A documentação fornece instruções passo a passo que o ajudarão a:</span><span class="sxs-lookup"><span data-stu-id="42d4b-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="42d4b-133">Habilitar o monitoramento na sua topologia e associar um repositório de monitoramento a um Pool de Front-Ends.</span><span class="sxs-lookup"><span data-stu-id="42d4b-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="42d4b-134">Instale os relatórios do SQL Server Reporting Services e do Lync Server Monitoring.</span><span class="sxs-lookup"><span data-stu-id="42d4b-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="42d4b-135">Relatórios de Monitoramento são relatórios pré-configurados que fornecem visões diferentes das informações armazenadas em um banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="42d4b-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="42d4b-136">Configurar a coleta de dados de registro de detalhes de chamadas (CDR) e qualidade da experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="42d4b-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="42d4b-137">A gravação de detalhes da chamada fornece uma maneira de acompanhar o uso de recursos do Lync Server, como chamadas telefônicas de voz sobre IP (VoIP); mensagens instantâneas (IM); transferências de arquivos; Conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="42d4b-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="42d4b-138">Métricas de QoE acompanham a qualidade de chamadas de áudio e vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, ruídos de fundo e o volume de "tremulação" (diferenças no atraso de pacotes).</span><span class="sxs-lookup"><span data-stu-id="42d4b-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="42d4b-139">Limpar manualmente registros de CDR e/ou QoE do banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="42d4b-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

