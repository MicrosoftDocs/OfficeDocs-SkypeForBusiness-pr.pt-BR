---
title: Implantar o Enterprise Voice no Skype for Business Server
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
description: 'Resumo: saiba como implantar o Enterprise Voice para Skype for Business Server em um site central.'
ms.openlocfilehash: 246c1e5c03401b885b297ada08677fb40faad60d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812491"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="40327-103">Implantar o Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="40327-104">**Resumo:** Saiba como implantar o Enterprise Voice para Skype for Business Server em um site central.</span><span class="sxs-lookup"><span data-stu-id="40327-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="40327-105">Use este tópico para implantar o Enterprise Voice em um site central.</span><span class="sxs-lookup"><span data-stu-id="40327-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="40327-106">Para implantar o Enterprise Voice em um site de filial, pule para [Implantar Sites de Filial.](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)</span><span class="sxs-lookup"><span data-stu-id="40327-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="40327-107">Esta seção inclui procedimentos para implantações nas quais um Servidor de Mediação é alocado em cada Servidor front-end ou servidor Standard Edition, conforme recomendado, e também para implantações com um pool de Servidor de Mediação autônomo. Você pode ignorar o seguinte conteúdo se tiver usado o Construtor de Topologias para definir e publicar uma topologia que coloca um Servidor de Mediação em cada servidor Front End ou Standard Edition, pois o Assistente de Implantação já instalou automaticamente os arquivos para o Servidor de Mediação quando você instalou arquivos para seu pool de Servidores Front-End ou servidor Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="40327-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="40327-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="40327-108">In this section</span></span>

- [<span data-ttu-id="40327-109">Pré-requisitos de segurança e configuração para o Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="40327-110">Implantar um Servidor de Mediação no Construtor de Topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="40327-111">Definir um gateway no Construtor de Topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="40327-112">Definir troncos adicionais no Construtor de Topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="40327-113">Instalar os arquivos do Servidor de Mediação no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="40327-114">Configurar troncos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="40327-115">Criar ou modificar uma regra de conversão para apresentação de ID de chamadas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="40327-116">Criar ou modificar uma regra de conversão para apresentação de ID chamada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="40327-117">Criar ou modificar uma regra de normalização no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="40327-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="40327-118">Criar ou modificar um plano de discagem no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="40327-119">Configurar políticas de voz, registros de uso de PSTN e rotas de voz no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="40327-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="40327-120">Habilitar usuários para o Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="40327-121">Implantar recursos avançados do Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="40327-122">Implantar recursos de gerenciamento de chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="40327-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="40327-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="40327-123">See also</span></span>

[<span data-ttu-id="40327-124">Planejar o Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40327-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

