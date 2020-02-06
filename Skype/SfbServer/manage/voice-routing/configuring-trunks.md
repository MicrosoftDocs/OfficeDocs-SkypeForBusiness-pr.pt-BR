---
title: Configurando troncos no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais pares para fornecer conectividade PSTN (rede telefônica pública comutada) para clientes e dispositivos do Enterprise Voice em sua organização.
ms.openlocfilehash: 41e92f994606ea2153359546d408335d13a21f88
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817011"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="9535b-103">Configurando troncos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9535b-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="9535b-104">Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais dos seguintes pares para fornecer conectividade PSTN (rede telefônica pública comutada) para clientes e dispositivos do Enterprise Voice em sua organização:</span><span class="sxs-lookup"><span data-stu-id="9535b-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="9535b-105">Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="9535b-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="9535b-106">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="9535b-106">PSTN gateway</span></span>
- <span data-ttu-id="9535b-107">Central privada de comutação telefônica (PBX)</span><span class="sxs-lookup"><span data-stu-id="9535b-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="9535b-108">Para obter detalhes, consulte [planejar conectividade PSTN no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9535b-109">Antes de começar a configuração de tronco, verifique se a topologia foi criada e se o servidor de mediação e seu par foram configurados e associados uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="9535b-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="9535b-110">Para obter detalhes, consulte [definir um gateway no construtor de topologias no Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9535b-111">Como parte da configuração de tronco, você pode habilitar o recurso de bypass de mídia do Skype for Business Server, que permite que a mídia ignore o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="9535b-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="9535b-112">Os troncos podem ser configurados com ou sem bypass de mídia habilitados, mas é altamente recomendável que você o habilite.</span><span class="sxs-lookup"><span data-stu-id="9535b-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="9535b-113">Para obter detalhes, consulte [plano de bypass de mídia no Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="9535b-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
