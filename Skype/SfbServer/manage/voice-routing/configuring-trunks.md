---
title: Configurando troncos no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais pares para fornecer conectividade PSTN (rede) telefônica pública comutada clientes Enterprise Voice e dispositivos em sua organização.
ms.openlocfilehash: 293685436997833c21dbd7b0d98521202e1beb99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896261"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="cf1cd-103">Configurando troncos no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="cf1cd-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="cf1cd-104">Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais dos seguintes computadores para fornecer conectividade PSTN (rede) telefônica pública comutada clientes Enterprise Voice e dispositivos em sua organização:</span><span class="sxs-lookup"><span data-stu-id="cf1cd-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="cf1cd-105">Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="cf1cd-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="cf1cd-106">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="cf1cd-106">PSTN gateway</span></span>
- <span data-ttu-id="cf1cd-107">Central privada de comutação telefônica (PBX)</span><span class="sxs-lookup"><span data-stu-id="cf1cd-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="cf1cd-108">Para obter detalhes, consulte [Planejar a conectividade PSTN em Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="cf1cd-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf1cd-109">Antes de começar a configuração do tronco, verifique se a topologia foi criada e que o servidor de mediação e seu ponto tiverem sido configuradas e associadas umas com as outras.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="cf1cd-110">Para obter detalhes, consulte [Define um gateway no construtor de topologia no Skype para Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="cf1cd-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cf1cd-111">Como parte da configuração de tronco, é possível habilitar o Skype para o recurso de bypass de mídia Business Server, que permite a mídia ignorar o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="cf1cd-112">Troncos podem ser configurados com ou sem o bypass de mídia habilitado, mas é altamente recomendável habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="cf1cd-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="cf1cd-113">Para obter detalhes, consulte [Plan for mídia que o desvio Skype para negócios](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="cf1cd-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
