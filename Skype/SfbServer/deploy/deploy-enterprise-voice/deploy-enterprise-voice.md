---
title: Implantar o Enterprise Voice no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Resumo: Saiba como implantar o Enterprise Voice para Skype para Business Server em um site central.'
ms.openlocfilehash: 8fb434a4fe02ec5755d78d549f870da9860b2910
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892710"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="078cd-103">Implantar o Enterprise Voice no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="078cd-104">**Resumo:** Aprenda a implantar o Enterprise Voice para Skype para Business Server em um site central.</span><span class="sxs-lookup"><span data-stu-id="078cd-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="078cd-105">Use este tópico para implantar o Enterprise Voice em um site central.</span><span class="sxs-lookup"><span data-stu-id="078cd-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="078cd-106">Para implantar o Enterprise Voice em um site de filial, pule para a [Implantação de Sites de filiais](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="078cd-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="078cd-107">Esta seção inclui procedimentos para implantações em que um servidor de mediação é colocado em cada servidor Front-End ou servidor Standard Edition, conforme recomendado e também para implantações com um pool de servidor de mediação autônomo. Você pode ignorar o conteúdo a seguir se você usou o construtor de topologias para definir e publicar uma topologia que coloca um servidor de mediação em cada servidor Front-End ou servidor Standard Edition, porque o Assistente de implantação já automaticamente instalado os arquivos para Servidor de mediação quando você instalou os arquivos para o pool do servidor Front-End ou servidor Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="078cd-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="078cd-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="078cd-108">In this section</span></span>

- [<span data-ttu-id="078cd-109">Pré-requisitos de segurança e configuração para o Enterprise Voice no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="078cd-110">Implantar um servidor de mediação no construtor de topologia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="078cd-111">Definir um gateway no construtor de topologia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="078cd-112">Definir troncos adicionais no construtor de topologia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="078cd-113">Instalar os arquivos para o servidor de mediação em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="078cd-114">Configurar troncos no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="078cd-115">Criar ou modificar uma regra de conversão para a apresentação de ID do chamador em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="078cd-116">Criar ou modificar uma regra de conversão para apresentação da ID chamada no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="078cd-117">Criar ou modificar uma regra de normalização no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="078cd-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="078cd-118">Criar ou modificar um plano de discagem no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="078cd-119">Configurar políticas de voz, registros de uso PSTN e roteamentos de voz no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="078cd-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="078cd-120">Habilitar usuários para o Enterprise Voice no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="078cd-121">Implantar os recursos avançados do Enterprise Voice do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="078cd-122">Implantar os recursos de gerenciamento de chamada do Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="078cd-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="078cd-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="078cd-123">See also</span></span>

[<span data-ttu-id="078cd-124">Planejar o Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="078cd-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

