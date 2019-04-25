---
title: Configurar e gerenciar o Skype for Business Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Saiba como configurar Skype para Business Edition de conector de nuvem, uma topologia de local mínima para habilitar a integração da sua infraestrutura de voz no local com o sistema telefônico nos serviços de voz do Office 365 (nuvem PBX) no Skype para negócios Online.
ms.openlocfilehash: 5d057a299e51bfb83bd6711fcf1fbe8b4ee98f02
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227912"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="ca6d2-103">Configurar e gerenciar o Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="ca6d2-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="ca6d2-104">Saiba como configurar Skype para Business Edition de conector de nuvem, uma topologia de local mínima para habilitar a integração da sua infraestrutura de voz no local com o sistema telefônico nos serviços de voz do Office 365 (nuvem PBX) no Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="ca6d2-105">Antes de começar, você deve examinar os pré-requisitos em [Planejar Skype para o conector de nuvem Business Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="ca6d2-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ca6d2-106">As etapas neste tópico se aplicam apenas ao Cloud Connector Edition 1.4.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="ca6d2-107">Se você ainda não tiver atualizado para o Cloud Connector Edition 2.1, veja [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="ca6d2-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="ca6d2-108">Você pode baixar o arquivo de instalação do [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="ca6d2-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="ca6d2-109">Etapas para configurar o Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="ca6d2-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="ca6d2-110">A tabela a seguir lista as etapas necessárias para instalar e configurar o Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="ca6d2-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="ca6d2-111">**Etapa**</span><span class="sxs-lookup"><span data-stu-id="ca6d2-111">**Step**</span></span>|<span data-ttu-id="ca6d2-112">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ca6d2-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ca6d2-113">Preparar o dispositivo do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ca6d2-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="ca6d2-114">Baixe o arquivo de instalação, preparar certificados, configure o Hyper-V e prepare seu ambiente para sua implantação do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="ca6d2-115">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ca6d2-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="ca6d2-116">Criar um site na implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="ca6d2-117">Implantar vários sites no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ca6d2-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="ca6d2-118">Adicionar sites à implantação e conhecer as diferenças entre implantações com um ou vários sites.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="ca6d2-119">Configure Cloud Connector integration with your Office 365 tenant</span><span class="sxs-lookup"><span data-stu-id="ca6d2-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="ca6d2-120">Adicione registros DNS, configure a implantação híbrida, configure os gateways PSTN e habilite os usuários para a caixa postal do Sistema de Telefonia do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="ca6d2-121">Validate your Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="ca6d2-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="ca6d2-122">Verificar se a implantação está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="ca6d2-123">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ca6d2-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="ca6d2-124">Atualize a implantação atual do Cloud Connector para a versão 2.1.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="ca6d2-125">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="ca6d2-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="ca6d2-126">Alterar as configurações no conector de nuvem depois que ele já estiver implantado.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="ca6d2-127">Implantar o bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="ca6d2-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="ca6d2-128">Saiba como implantar o bypass de mídia no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ca6d2-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="ca6d2-129">Cloud Connector cmdlet reference</span><span class="sxs-lookup"><span data-stu-id="ca6d2-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="ca6d2-130">Conhecer os cmdlets do PowerShell usados no Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="ca6d2-131">Solução de problemas de implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ca6d2-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="ca6d2-132">Soluções para problemas comuns encontrados em uma implantação do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="ca6d2-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

