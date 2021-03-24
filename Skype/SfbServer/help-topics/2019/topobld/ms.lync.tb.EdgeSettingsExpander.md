---
title: Expansor de Configurações de Borda
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar as configurações de um pool de Borda de um único ou vários servidores existente, você pode usar as seguintes seções:'
ms.openlocfilehash: c887ffaa16818e377035109632871b7bc7ed25d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108797"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="a78eb-103">Expansor de Configurações de Borda</span><span class="sxs-lookup"><span data-stu-id="a78eb-103">Edge Settings Expander</span></span>

<span data-ttu-id="a78eb-104">Para editar as configurações de um pool de Borda de um único ou vários servidores existente, você pode usar as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="a78eb-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="a78eb-105">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="a78eb-105">General settings</span></span>

- <span data-ttu-id="a78eb-106">Configurações de seleção de próximo salto</span><span class="sxs-lookup"><span data-stu-id="a78eb-106">Next hop selection settings</span></span>

- <span data-ttu-id="a78eb-107">Configuração do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="a78eb-107">Edge Server configuration</span></span>


## <a name="general-settings"></a><span data-ttu-id="a78eb-108">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="a78eb-108">General settings</span></span>

<span data-ttu-id="a78eb-p101">FQDN (nome de domínio totalmente qualificado) de pool interno do pool de Servidor de Borda. Edite o FQDN do pool para alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="a78eb-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="a78eb-111">Marque a caixa de seleção Habilitar federação para este pool de Borda **(Porta 5061)** se você configurar a federação com um servidor skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a78eb-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Skype for Business Server 2015 server.</span></span>

<span data-ttu-id="a78eb-112">Especifique o número da porta para **Porta de Replicação de Configuração Interna (HTTPS)**.</span><span class="sxs-lookup"><span data-stu-id="a78eb-112">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="a78eb-113">Configurações de seleção de próximo salto</span><span class="sxs-lookup"><span data-stu-id="a78eb-113">Next hop selection settings</span></span>

<span data-ttu-id="a78eb-114">Para definir ou modificar o **pool** de Próximo salto que os Servidores de Borda usarão para se comunicar com a infraestrutura interna, selecione um diretor, pool de diretores, servidor front-end ou pool de Servidor de Front-End na caixa de listagem lista listada.</span><span class="sxs-lookup"><span data-stu-id="a78eb-114">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="a78eb-115">Somente Diretores ou Front Ends configurados no Construtor de Topologias serão exibidos para seleção.</span><span class="sxs-lookup"><span data-stu-id="a78eb-115">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="a78eb-116">Configuração do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="a78eb-116">Edge Server configuration</span></span>

<span data-ttu-id="a78eb-117">Para editar ou especificar definições para **Definições Externas** para os Servidores de Borda, você deve determinar, primeiro, se você utilizará endereços IP separados para serviço de Áudio/Vídeo, acesso SIP e webconferência.</span><span class="sxs-lookup"><span data-stu-id="a78eb-117">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="a78eb-p103">Caso pretenda usar endereços IP separados para cada, marque a caixa de seleção  **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Cada serviço deve possuir um registro de host DNS (A) correspondente criado para ele.</span><span class="sxs-lookup"><span data-stu-id="a78eb-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="a78eb-p104">Para cada um dos serviços externamente focados, você especifica um FQDN e uma porta associada. Por exemplo, o   **Acesso SIP** utilizaria sip.contoso.com e 5061 como porta associada.</span><span class="sxs-lookup"><span data-stu-id="a78eb-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a78eb-122">Caso você selecione FQDNs separados para cada um dos serviços externamente focados, cada serviço deve ter um valor de porta único associado a ele.</span><span class="sxs-lookup"><span data-stu-id="a78eb-122">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="a78eb-123">Por padrão, o SIP está na porta 5061/TLS, o serviço de borda de webconferência está na porta 444/TLS e o Servidor de Conferência A/V está na porta 443/TLS.</span><span class="sxs-lookup"><span data-stu-id="a78eb-123">By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS.</span></span> <span data-ttu-id="a78eb-124">Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="a78eb-124">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="a78eb-p106">Caso você determine que sua organização utilizará um único endereço IP e FQDN para os serviços externamente focados, limpe a caixa de seleção  **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Você então pode editar o pool FQDN de  **Acesso SIP** e valores de porta, se necessário.</span><span class="sxs-lookup"><span data-stu-id="a78eb-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a78eb-127">Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="a78eb-127">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="a78eb-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="a78eb-128">See also</span></span>

<span data-ttu-id="a78eb-129">Para maiores detalhes sobre como definir e configurar as definições para os Serviços de Borda, consulte [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span><span class="sxs-lookup"><span data-stu-id="a78eb-129">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span></span>