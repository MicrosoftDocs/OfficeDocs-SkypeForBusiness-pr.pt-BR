---
title: Configurar e gerenciar o Skype for Business Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Saiba como configurar o Skype for Business Cloud Connector Edition, uma topologia mínima local para habilitar a integração da sua infraestrutura de voz local com o sistema telefônico no Office 365 (Cloud PBX) serviços de voz no Skype for Business online.
ms.openlocfilehash: 5966fb4cc6bd7bd09e82f4a2907420f657a9097c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799731"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="2c28f-103">Configurar e gerenciar o Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="2c28f-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="2c28f-104">Saiba como configurar o Skype for Business Cloud Connector Edition, uma topologia mínima local para habilitar a integração da sua infraestrutura de voz local com o sistema telefônico no Office 365 (Cloud PBX) serviços de voz no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="2c28f-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="2c28f-105">Antes de começar, você deve revisar os pré-requisitos em [planejar o Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="2c28f-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2c28f-106">As etapas neste tópico se aplicam apenas ao Cloud Connector Edition 1.4.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="2c28f-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="2c28f-107">Se você ainda não tiver atualizado para o Cloud Connector Edition 2.1, veja [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="2c28f-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="2c28f-108">Você pode fazer o download do arquivo [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)de instalação do.</span><span class="sxs-lookup"><span data-stu-id="2c28f-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="2c28f-109">Etapas para configurar o Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="2c28f-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="2c28f-110">A tabela a seguir lista as etapas necessárias para instalar e configurar o Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="2c28f-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="2c28f-111">**Etapa**</span><span class="sxs-lookup"><span data-stu-id="2c28f-111">**Step**</span></span>|<span data-ttu-id="2c28f-112">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2c28f-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2c28f-113">Preparar o dispositivo do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="2c28f-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="2c28f-114">Baixe o arquivo de instalação, prepare certificados, configure o Hyper-V e prepare o seu ambiente para a implantação do seu conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="2c28f-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="2c28f-115">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="2c28f-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="2c28f-116">Criar um site na implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2c28f-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="2c28f-117">Implantar vários sites no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="2c28f-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="2c28f-118">Adicionar sites à implantação e conhecer as diferenças entre implantações com um ou vários sites.</span><span class="sxs-lookup"><span data-stu-id="2c28f-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="2c28f-119">Configure Cloud Connector integration with your Office 365 tenant</span><span class="sxs-lookup"><span data-stu-id="2c28f-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="2c28f-120">Adicione registros DNS, configure a implantação híbrida, configure os gateways PSTN e habilite os usuários para a caixa postal do Sistema de Telefonia do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c28f-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="2c28f-121">Validate your Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="2c28f-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="2c28f-122">Verificar se a implantação está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="2c28f-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="2c28f-123">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="2c28f-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="2c28f-124">Atualize a implantação atual do Cloud Connector para a versão 2.1.</span><span class="sxs-lookup"><span data-stu-id="2c28f-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="2c28f-125">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="2c28f-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="2c28f-126">Altere as configurações no conector de nuvem depois que ela já estiver implantada.</span><span class="sxs-lookup"><span data-stu-id="2c28f-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="2c28f-127">Implantar o bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="2c28f-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="2c28f-128">Saiba como implantar o bypass de mídia no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="2c28f-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="2c28f-129">Cloud Connector cmdlet reference</span><span class="sxs-lookup"><span data-stu-id="2c28f-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="2c28f-130">Conhecer os cmdlets do PowerShell usados no Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="2c28f-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="2c28f-131">Solução de problemas de implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="2c28f-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="2c28f-132">Soluções para problemas comuns encontrados em uma implantação do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="2c28f-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

