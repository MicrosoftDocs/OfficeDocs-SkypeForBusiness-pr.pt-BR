---
title: Expansor de Configurações de Borda
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar as configurações de um pool de Borda de um único ou vários servidores existente, você pode usar as seguintes seções:'
ms.openlocfilehash: 1125073d1f733959c9c0312fe3f0d36ad5369f8f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876261"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="a650e-103">Expansor de Configurações de Borda</span><span class="sxs-lookup"><span data-stu-id="a650e-103">Edge Settings Expander</span></span>

<span data-ttu-id="a650e-104">Para editar as configurações de um pool de Borda de um único ou vários servidores existente, você pode usar as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="a650e-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="a650e-105">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="a650e-105">General settings</span></span>

- <span data-ttu-id="a650e-106">Configurações de seleção de próximo salto</span><span class="sxs-lookup"><span data-stu-id="a650e-106">Next hop selection settings</span></span>

- <span data-ttu-id="a650e-107">Configuração do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="a650e-107">Edge Server configuration</span></span>


## <a name="general-settings"></a><span data-ttu-id="a650e-108">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="a650e-108">General settings</span></span>

<span data-ttu-id="a650e-p101">FQDN (nome de domínio totalmente qualificado) de pool interno do pool de Servidor de Borda. Edite o FQDN do pool para alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="a650e-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="a650e-111">Marque a caixa de seleção **Habilitar federação para este pool de borda (porta 5061)** se você irá configurar federação com um Skype para servidor Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a650e-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Skype for Business Server 2015 server.</span></span>

<span data-ttu-id="a650e-112">Especifique o número da porta para **Porta de Replicação de Configuração Interna (HTTPS)**.</span><span class="sxs-lookup"><span data-stu-id="a650e-112">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="a650e-113">Configurações de seleção de próximo salto</span><span class="sxs-lookup"><span data-stu-id="a650e-113">Next hop selection settings</span></span>

<span data-ttu-id="a650e-114">Para configurar ou modificar o **Pool de próximo salto** que os Servidores de Borda utilizarão para se comunicar com a infraestrutura interna, selecione um Diretor, pool de Diretores, Servidor Front-Ends ou pool de Servidor Front-Ends na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a650e-114">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="a650e-115">Apenas os diretores ou Front-Ends que tiverem sido configuradas no construtor de topologia aparecerá para seleção.</span><span class="sxs-lookup"><span data-stu-id="a650e-115">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="a650e-116">Configuração do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="a650e-116">Edge Server configuration</span></span>

<span data-ttu-id="a650e-117">Para editar ou especificar as configurações das **Configurações Externas** de Servidores de Borda, é possível determinar primeiro se você utilizará endereços IP separados para o acesso SIP, webconferência e serviço de Áudio/Vídeo.</span><span class="sxs-lookup"><span data-stu-id="a650e-117">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="a650e-p103">Caso pretenda usar endereços IP separados para cada, marque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Cada serviço deve ter um registro de host DNS (A) correspondente criado para ele.</span><span class="sxs-lookup"><span data-stu-id="a650e-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="a650e-p104">Especifique um FQDN e uma porta associada para cada um dos serviços externos. Por exemplo, o **Acesso SIP** utilizaria sip.contoso.com e 5061 como porta associada.</span><span class="sxs-lookup"><span data-stu-id="a650e-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a650e-p105">Caso você selecione FQDNs separados para cada um dos serviços externos, cada serviço deve ter um valor de porta único associado a ele. Por padrão, SIP está na porta 5061/TLS, o serviço de borda de webconferência está na porta 444/TLS e o Servidor de Conferência A/V está na porta 443/TLS. Se alterar alguma destas configurações, incluindo usar FQDN e endereços IP ou portas separadas, você deverá atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="a650e-p105">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="a650e-p106">Caso você determine que sua organização utilizará um único endereço IP e FQDN para os serviços externos, desmarque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Você poderá então editar o FQDN de pool e os valores de porta do **Acesso SIP**, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="a650e-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a650e-127">Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="a650e-127">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="a650e-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a650e-128">See also</span></span>

<span data-ttu-id="a650e-129">Para obter detalhes sobre como definir e configurar serviços de Borda, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="a650e-129">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


