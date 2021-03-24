---
title: Implantar Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Resumo: Saiba como implantar o Enterprise Voice para o Skype for Business Server em um site central.'
ms.openlocfilehash: c2aead4d42a02acce6b0db9f92866dba3a6e956d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104967"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="18388-103">Implantar Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="18388-104">**Resumo:** Saiba como implantar o Enterprise Voice para o Skype for Business Server em um site central.</span><span class="sxs-lookup"><span data-stu-id="18388-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="18388-105">Use este tópico para implantar Enterprise Voice em um site central.</span><span class="sxs-lookup"><span data-stu-id="18388-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="18388-106">Para implantar Enterprise Voice em um site de filial, pule para [Deploying Branch Sites](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).</span><span class="sxs-lookup"><span data-stu-id="18388-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).</span></span>

<span data-ttu-id="18388-107">Esta seção inclui procedimentos para implantações nas quais um Servidor de Mediação é alocado em cada servidor Front-End ou Standard Edition, conforme recomendado, e também para implantações com um pool de Servidor de Mediação autônomo. Você pode ignorar o conteúdo a seguir se você usou o Construtor de Topologias para definir e publicar uma topologia que coloca um Servidor de Mediação em cada Servidor de Front-End ou servidor Standard Edition, pois o Assistente de Implantação já instalou automaticamente os arquivos para o Servidor de Mediação quando você instalou arquivos para seu pool de Servidores Front-End ou servidor Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="18388-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="18388-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="18388-108">In this section</span></span>

- [<span data-ttu-id="18388-109">Pré-requisitos de segurança e configuração para Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="18388-110">Implantar um Servidor de Mediação no Construtor de Topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="18388-111">Definir um gateway no Construtor de Topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="18388-112">Definir troncos adicionais no Construtor de Topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="18388-113">Instalar os arquivos para o Servidor de Mediação no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="18388-114">Configurar troncos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="18388-115">Criar ou modificar uma regra de conversão para apresentação de ID do chamador no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="18388-116">Criar ou modificar uma regra de conversão para apresentação chamada de ID no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="18388-117">Criar ou modificar uma regra de normalização no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="18388-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="18388-118">Criar ou modificar um plano de discagem no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="18388-119">Configurar políticas de voz, registros de uso de PSTN e rotas de voz no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="18388-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="18388-120">Habilitar usuários para Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="18388-121">Implantar recursos Enterprise Voice avançados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="18388-122">Implantar recursos de gerenciamento de chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="18388-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="18388-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="18388-123">See also</span></span>

[<span data-ttu-id="18388-124">Planejar Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18388-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)