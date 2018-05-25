---
title: Expansor de Configurações de Borda
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Para editar as configurações de um pool de Borda de um único ou vários servidores existente, você pode usar as seguintes seções:'
ms.openlocfilehash: 5e9e916283bf36e0d81af41477920ba19e13e9a8
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="edge-settings-expander"></a><span data-ttu-id="523c5-103">Expansor de Configurações de Borda</span><span class="sxs-lookup"><span data-stu-id="523c5-103">Edge Settings Expander</span></span>
 
<span data-ttu-id="523c5-104">Para editar as configurações de um pool de Borda de um único ou vários servidores existente, você pode usar as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="523c5-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="523c5-105">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="523c5-105">General settings</span></span>
    
- <span data-ttu-id="523c5-106">Configurações de seleção de próximo salto</span><span class="sxs-lookup"><span data-stu-id="523c5-106">Next hop selection settings</span></span>
    
- <span data-ttu-id="523c5-107">Configuração do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="523c5-107">Edge Server configuration</span></span>
    
## 

### <a name="general-settings"></a><span data-ttu-id="523c5-108">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="523c5-108">General settings</span></span>

<span data-ttu-id="523c5-p101">FQDN (nome de domínio totalmente qualificado) de pool interno do pool de Servidor de Borda. Edite o FQDN do pool para alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="523c5-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>
  
<span data-ttu-id="523c5-111">Marque a caixa de seleção **Habilitar federação para este pool de borda (porta 5061)** se você irá configurar federação com o Lync Server 2013, Microsoft Lync Server 2010 ou o Microsoft Office Communications Server 2007 R2 parceiro confiável.</span><span class="sxs-lookup"><span data-stu-id="523c5-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>
  
<span data-ttu-id="523c5-112">Selecione  **Habilitar federação XMPP para este pool de Borda** para habilitar a federação XMPP.</span><span class="sxs-lookup"><span data-stu-id="523c5-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>
  
<span data-ttu-id="523c5-113">Especifique o número da porta para **Porta de Replicação de Configuração Interna (HTTPS)**.</span><span class="sxs-lookup"><span data-stu-id="523c5-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>
  
### <a name="next-hop-selection-settings"></a><span data-ttu-id="523c5-114">Configurações de seleção de próximo salto</span><span class="sxs-lookup"><span data-stu-id="523c5-114">Next hop selection settings</span></span>

<span data-ttu-id="523c5-115">Para configurar ou modificar o **Pool de próximo salto** que os Servidores de Borda utilizarão para se comunicar com a infraestrutura interna, selecione um Diretor, pool de Diretores, Servidor Front-Ends ou pool de Servidor Front-Ends na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="523c5-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="523c5-116">Apenas os diretores ou Front-Ends que tiverem sido configuradas no construtor de topologia aparecerá para seleção.</span><span class="sxs-lookup"><span data-stu-id="523c5-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>
  
### <a name="edge-server-configuration"></a><span data-ttu-id="523c5-117">Configuração do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="523c5-117">Edge Server configuration</span></span>

<span data-ttu-id="523c5-118">Para editar ou especificar as configurações das **Configurações Externas** de Servidores de Borda, é possível determinar primeiro se você utilizará endereços IP separados para o acesso SIP, webconferência e serviço de Áudio/Vídeo.</span><span class="sxs-lookup"><span data-stu-id="523c5-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>
  
<span data-ttu-id="523c5-p103">Caso pretenda usar endereços IP separados para cada, marque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Cada serviço deve ter um registro de host DNS (A) correspondente criado para ele.</span><span class="sxs-lookup"><span data-stu-id="523c5-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>
  
<span data-ttu-id="523c5-p104">Especifique um FQDN e uma porta associada para cada um dos serviços externos. Por exemplo, o **Acesso SIP** utilizaria sip.contoso.com e 5061 como porta associada.</span><span class="sxs-lookup"><span data-stu-id="523c5-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="523c5-p105">Caso você selecione FQDNs separados para cada um dos serviços externos, cada serviço deve ter um valor de porta único associado a ele. Por padrão, SIP está na porta 5061/TLS, o serviço de borda de webconferência está na porta 444/TLS e o Servidor de Conferência A/V está na porta 443/TLS. Se alterar alguma destas configurações, incluindo usar FQDN e endereços IP ou portas separadas, você deverá atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="523c5-p105">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span> 
  
<span data-ttu-id="523c5-p106">Caso você determine que sua organização utilizará um único endereço IP e FQDN para os serviços externos, desmarque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Você poderá então editar o FQDN de pool e os valores de porta do **Acesso SIP**, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="523c5-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="523c5-128">Se alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deverá atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="523c5-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span> 
  
### 

<span data-ttu-id="523c5-129">Para obter detalhes sobre como definir e configurar as definições para os serviços de borda, consulte [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="523c5-129">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>
  

