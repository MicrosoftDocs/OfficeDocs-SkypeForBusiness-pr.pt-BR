---
title: Expansor de Configurações FQDNs de Servidor de Borda
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Para editar ou especificar Configurações Externas para os Servidores de Borda, primeiro você deve determinar se usará endereços IP separados para acesso SIP, o serviço de Borda de Webconferência e o serviço de Borda de Áudio/Vídeo.
ms.openlocfilehash: 7bca4f934e321edbf3c32d9d075b4a1cccd2bbf6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807081"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="b53cf-103">Expansor de Configurações FQDNs de Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="b53cf-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="b53cf-104">Para editar ou especificar Configurações Externas para os Servidores de Borda, primeiro você deve determinar se usará endereços IP **separados** para acesso SIP, o serviço de Borda de Webconferência e o serviço de Borda de Áudio/Vídeo.</span><span class="sxs-lookup"><span data-stu-id="b53cf-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="b53cf-p101">Caso você pretenda usar endereços IP separados para cada um, marque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Cada serviço deve possuir um registro de hospedeiro (A) DNS (Domain Name System) correspondente criado para ele.</span><span class="sxs-lookup"><span data-stu-id="b53cf-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="b53cf-p102">Para cada serviço externamente focado, especifique um FQDN (nome de domínio totalmente qualificado) e uma porta associada. Por exemplo, para   **Acesso SIP**, você poderia usar sip.contoso.com com uma porta 5061 associada.</span><span class="sxs-lookup"><span data-stu-id="b53cf-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b53cf-p103">Caso você selecione FQDNs separados para cada um dos serviços externamente focados, cada serviço deve ter um valor de porta único associado a ele. Por padrão, o SIP está na porta 5061/TLS, o serviço de Borda de Conferência Web está na porta 444/TLS e o serviço de Borda de Conferência A/V está na porta 443/TLS. Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="b53cf-p103">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="b53cf-p104">Caso você determine que sua organização utilizará um único endereço IP e FQDN para os serviços externamente focados, limpe a caixa de seleção  **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Você então pode editar o pool FQDN de  **Acesso SIP** e valores de porta, se necessário.</span><span class="sxs-lookup"><span data-stu-id="b53cf-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b53cf-114">Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="b53cf-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="b53cf-115">Para obter detalhes sobre como definir e configurar as configurações para os serviços de Borda, consulte [Definir sua topologia de borda.](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)</span><span class="sxs-lookup"><span data-stu-id="b53cf-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


