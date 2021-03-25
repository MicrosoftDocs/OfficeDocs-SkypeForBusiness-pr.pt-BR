---
title: Expansor de Configurações Gerais de Aparelho de Filial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Para editar as configurações para um Aparelho de Filial Persistente ou um Servidor de Borda Persistente, veja as seções a seguir:'
ms.openlocfilehash: 8f77a7b12800d9eba091218de92f4eec17bf2154
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119690"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="0049d-103">Expansor de Configurações Gerais de Aparelho de Filial</span><span class="sxs-lookup"><span data-stu-id="0049d-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="0049d-104">Para editar as configurações para um Aparelho de Filial Persistente ou um Servidor de Borda Persistente, veja as seções a seguir:</span><span class="sxs-lookup"><span data-stu-id="0049d-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="0049d-105">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="0049d-105">General settings</span></span>

- <span data-ttu-id="0049d-106">Configurações de resiliência</span><span class="sxs-lookup"><span data-stu-id="0049d-106">Resiliency settings</span></span>

- <span data-ttu-id="0049d-107">Configurações de Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="0049d-107">Mediation Server settings</span></span>



<span data-ttu-id="0049d-108">Para um Aparelho de Filial Persistente ou Servidor de Filial Persistente, você encontrará:</span><span class="sxs-lookup"><span data-stu-id="0049d-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="0049d-109">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="0049d-109">General settings</span></span>

<span data-ttu-id="0049d-p101">O FQDN (nome de domínio totalmente qualificado) do Aparelho de Filial Persistente ou Servidor de Filial Persistente. Edite o FQDN do servidor para alterar o valor. Você deve ter um registro de hospedeiro (A) DNS (Domain Name System) coincidente com o novo valor.</span><span class="sxs-lookup"><span data-stu-id="0049d-p101">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="0049d-p102">Você pode escolher  **Usar todos os endereços IP configurados** ou  **Limitar uso do serviço aos endereços IP selecionados**. Caso escolha  **Limitar uso do serviço aos endereços IP selecionados**, você definirá o endereço IP primário que o servidor utilizará para todas as comunicações, exceto para o gateway PSTN (rede telefônica pública comutada). Você define um endereço IP separado para utilização de PSTN.</span><span class="sxs-lookup"><span data-stu-id="0049d-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="0049d-116">In **Associations**, you can edit or specify the following:</span><span class="sxs-lookup"><span data-stu-id="0049d-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="0049d-117">Associar o Servidor de Arquivamento permite que você selecione associar um Servidor de Arquivamento ao Aparelho de Filial Desavivável ou Servidor de Filial Desavivável.</span><span class="sxs-lookup"><span data-stu-id="0049d-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0049d-118">Você pode selecionar em um Servidor de Arquivamento já definido selecionando o servidor na listada ou clique em **Novo** para especificar um novo Servidor de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0049d-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0049d-119">O servidor especificado por você deve existir e fazer parte do domínio antes de a publicação da nova topologia recentemente definida.</span><span class="sxs-lookup"><span data-stu-id="0049d-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="0049d-120">Associar o Servidor de Monitoramento permite que você selecione associar um Servidor de Monitoramento ao Aparelho de Filial Desavivável ou Ao Servidor de Filial Desavivável.</span><span class="sxs-lookup"><span data-stu-id="0049d-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0049d-121">Você pode selecionar em um Servidor de Monitoramento já definido selecionando o servidor na listada ou clique em **Novo** para especificar um novo Servidor de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="0049d-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="0049d-122">Associar pool de Borda permite que você selecione associar um Servidor de Borda ou pool ao Aparelho de Filial Desavivável ou Servidor de Filial Suportável.</span><span class="sxs-lookup"><span data-stu-id="0049d-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0049d-123">Você pode selecionar a partir de um pool ou Servidor de Borda já definido, selecionando o servidor a partir da lista suspensa, ou clicar em **Novo** para especificar um novo pool ou Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="0049d-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="0049d-124">Resiliência</span><span class="sxs-lookup"><span data-stu-id="0049d-124">Resiliency</span></span>

<span data-ttu-id="0049d-p106">A resiliência oferece alta disponibilidade para o pool de Registradores. Ao providenciar um Registrador de backup, se o Registrador primário falhar, o Registrador de backup poderá assumir as funções do Registrador com falha, permitindo que usuários se conectem e comuniquem. Talvez ocorra uma redução de funcionalidades para os usuários, dependendo em quais sistemas tenham falhado com o Registrador primário.</span><span class="sxs-lookup"><span data-stu-id="0049d-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="0049d-128">Na listada, selecione o pool de Front-End enterprise Edition ou o Servidor De Front-End Standard Edition que atuará como o Registrador de backup para o Aparelho de Filial Desavivável ou Servidor de Filial Desavivável.</span><span class="sxs-lookup"><span data-stu-id="0049d-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0049d-129">Você também pode escolher habilitar os intervalos de tempo de Failover e Fallback.</span><span class="sxs-lookup"><span data-stu-id="0049d-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="0049d-130">Habilitar as definições de tempo de failover e fallback (especificadas em segundos) permite a detecção automática da falha de um Registrador, enquanto o tempo de fallback permite a determinação automática de que o primário está funcionando novamente e pode assumir o processo de Registrador.</span><span class="sxs-lookup"><span data-stu-id="0049d-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0049d-131">Tome cuidado, quando definir o intervalo de detecção de falha e de fallback, para não inserir um intervalo que causará com que o failover e fallback ocorram se o Registrador falhar em responder por um curto período de tempo.</span><span class="sxs-lookup"><span data-stu-id="0049d-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="0049d-132">É possível que o Registrador primário não responda por curtos períodos de tempo, baseado no carregamento do pool ou servidores.</span><span class="sxs-lookup"><span data-stu-id="0049d-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="0049d-133">Os valores padrão para um Aparelho de FilialVivível ou um Servidor de Filial Desavivável em um site para um pool ou Servidor De Front-End Standard Edition são 120 segundos para failover e 240 segundos para fallback.</span><span class="sxs-lookup"><span data-stu-id="0049d-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="0049d-134">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="0049d-134">Mediation Server</span></span>

<span data-ttu-id="0049d-135">Para **Servidor de Mediação**, você pode especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0049d-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="0049d-136">A caixa de seleção para **Servidor de Mediação Colocado ativado** não está disponível em um Aparelho de Filial Persistente ou Servidor de Filial Persistente pois o Servidor de Mediação está colocado.</span><span class="sxs-lookup"><span data-stu-id="0049d-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="0049d-p109">Você define a porta de escuta nos servidores de pool para TLS (Transport Layer Security). Por padrão é a porta 5067. Caso escolha **Ativar porta TCP**, você deve definir uma porta TCP para o Servidor de Mediação colocado. Esta é uma definição opcional e você deve consultar os requisitos de seu gateway ou requisitos PSTN para determinar a necessidade disso. Por padrão, o valor da porta TCP é 5068.</span><span class="sxs-lookup"><span data-stu-id="0049d-p109">You define the listening port on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="0049d-p110">Você define gateways PSTN que estão associados ao Servidor de Mediação colocado. Caso já tenha definido gateways, eles estarão disponíveis para associação com o Servidor de Mediação. Caso não tenha definido qualquer gateway, mas estejam disponíveis para definir, você pode selecionar **Novo**. Você também pode remover gateways que já estejam configurados para este Servidor de Mediação, selecionando o gateway e clicando em  **Remover**.</span><span class="sxs-lookup"><span data-stu-id="0049d-p110">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you have not defined any gateways, but you have them available to define, you can select **New**. You can also remove gateways that are already configured for this Mediation Server. Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="0049d-p111">Caso tenha mais de um gateway associado a um Servidor de Mediação, o primeiro gateway associado será o gateway padrão. Caso você deva escolher outro gateway como gateway padrão, selecione o gateway que deseja tornar padrão e clique em **Tornar Padrão**.</span><span class="sxs-lookup"><span data-stu-id="0049d-p111">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0049d-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="0049d-149">See also</span></span>

<span data-ttu-id="0049d-150">Para maiores detalhes sobre como definir e configurar as configurações para o Aparelho de Filial Persistente ou Servidor de Filial Persistente, consulte[Branch-Site Resiliency Solutions](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions).</span><span class="sxs-lookup"><span data-stu-id="0049d-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions).</span></span>