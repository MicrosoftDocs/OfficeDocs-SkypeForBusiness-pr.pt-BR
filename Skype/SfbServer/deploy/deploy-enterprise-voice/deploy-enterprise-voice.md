---
title: Implantar o Enterprise Voice no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Resumo: Saiba como implantar o Enterprise Voice para Skype para negócios 2015 de servidor em um site central.'
ms.openlocfilehash: d7c6dc347991c198d445932463a44d9fe1a4ff89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="c71d9-103">Implantar o Enterprise Voice no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-103">Deploy Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c71d9-104">**Resumo:** Aprenda a implantar o Enterprise Voice para Skype para negócios 2015 de servidor em um site central.</span><span class="sxs-lookup"><span data-stu-id="c71d9-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server 2015 at a central site.</span></span>
  
<span data-ttu-id="c71d9-105">Use este tópico para implantar o Enterprise Voice em um site central.</span><span class="sxs-lookup"><span data-stu-id="c71d9-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="c71d9-106">Para implantar o Enterprise Voice em um site de filial, pule para a [Implantação de Sites de filiais](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="c71d9-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>
  
<span data-ttu-id="c71d9-107">Esta seção inclui procedimentos para implantações em que um servidor de mediação é colocado em cada servidor Front-End ou servidor Standard Edition, conforme recomendado e também para implantações com um pool de servidor de mediação autônomo. Você pode ignorar o conteúdo a seguir se você usou o construtor de topologias para definir e publicar uma topologia que coloca um servidor de mediação em cada servidor Front-End ou servidor Standard Edition, porque o Assistente de implantação já automaticamente instalado os arquivos para Servidor de mediação quando você instalou os arquivos para o pool do servidor Front-End ou servidor Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="c71d9-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="c71d9-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c71d9-108">In this section</span></span>

- [<span data-ttu-id="c71d9-109">Pré-requisitos de segurança e configuração para o Enterprise Voice no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>](enterprise-voice-security.md)
    
- [<span data-ttu-id="c71d9-110">Implantar um servidor de mediação no construtor de topologia no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>](deploy-a-mediation-server.md)
    
- [<span data-ttu-id="c71d9-111">Definir um gateway no construtor de topologia no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-111">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>](define-a-gateway.md)
    
- [<span data-ttu-id="c71d9-112">Definir troncos adicionais no construtor de topologia no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-112">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>](define-additional-trunks.md)
    
- [<span data-ttu-id="c71d9-113">Instalar os arquivos para o servidor de mediação em Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-113">Install the files for Mediation Server in Skype for Business Server 2015</span></span>](install-mediation-server.md)
    
- [<span data-ttu-id="c71d9-114">Configurar troncos no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-114">Configure trunks in Skype for Business Server 2015</span></span>](configure-trunks.md)
    
- [<span data-ttu-id="c71d9-115">Criar ou modificar uma regra de conversão para a apresentação de ID do chamador em Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server 2015</span></span>](caller-id-presentation-rules.md)
    
- [<span data-ttu-id="c71d9-116">Criar ou modificar uma regra de conversão para apresentação da ID chamada no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-116">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>](called-id-presentation-rules.md)
    
- [<span data-ttu-id="c71d9-117">Criar ou modificar uma regra de normalização no Skype para negócios 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-117">Create or modify a normalization rule in Skype for Business 2015</span></span>](normalization-rules.md)
    
- [<span data-ttu-id="c71d9-118">Criar ou modificar um plano de discagem no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-118">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)
    
- [<span data-ttu-id="c71d9-119">Configurar políticas de voz, registros de uso PSTN e roteamentos de voz no Skype para negócios 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>](voice-and-pstn.md)
    
- [<span data-ttu-id="c71d9-120">Habilitar usuários para o Enterprise Voice no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-120">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](enable-users-for-enterprise-voice.md)
    
- [<span data-ttu-id="c71d9-121">Implantar os recursos avançados do Enterprise Voice do Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-121">Deploy advanced Enterprise Voice features in Skype for Business Server 2015</span></span>](deploy-advanced-enterprise-voice-features.md)
    
- [<span data-ttu-id="c71d9-122">Implantar os recursos de gerenciamento de chamada do Skype para negócios 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-122">Deploy call management features in Skype for Business 2015</span></span>](deploy-call-management-features.md)
    
## <a name="see-also"></a><span data-ttu-id="c71d9-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c71d9-123">See also</span></span>

#### 

[<span data-ttu-id="c71d9-124">Planejar o Enterprise Voice no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c71d9-124">Plan for Enterprise Voice in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

