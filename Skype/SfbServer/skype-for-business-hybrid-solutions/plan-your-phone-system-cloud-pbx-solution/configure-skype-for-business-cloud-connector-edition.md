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
description: Saiba como configurar o Skype for Business Cloud Connector Edition, uma topologia local mínima para permitir a integração de sua infraestrutura de voz local com os serviços de voz do sistema de telefonia (Cloud PBX) no Skype for Business online.
ms.openlocfilehash: a7c157836497383d89055f8ab986aa15f7e11870
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219511"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="cfa4e-103">Configurar e gerenciar o Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="cfa4e-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="cfa4e-104">Saiba como configurar o Skype for Business Cloud Connector Edition, uma topologia local mínima para permitir a integração de sua infraestrutura de voz local com os serviços de voz do sistema de telefonia (Cloud PBX) no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="cfa4e-105">Antes de começar, examine os pré-requisitos em [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="cfa4e-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cfa4e-106">As etapas neste tópico se aplicam apenas ao Cloud Connector Edition 1.4.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="cfa4e-107">Se você ainda não tiver atualizado para o Cloud Connector Edition 2,1, consulte [upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="cfa4e-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="cfa4e-108">Você pode baixar o arquivo de instalação do [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="cfa4e-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="cfa4e-109">Etapas para configurar o Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="cfa4e-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="cfa4e-110">A tabela a seguir lista as etapas necessárias para instalar e configurar o Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="cfa4e-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="cfa4e-111">**Etapa**</span><span class="sxs-lookup"><span data-stu-id="cfa4e-111">**Step**</span></span>|<span data-ttu-id="cfa4e-112">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cfa4e-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="cfa4e-113">Preparar o dispositivo do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="cfa4e-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="cfa4e-114">Baixar o arquivo de instalação, preparar certificados, configurar o Hyper-V e preparar seu ambiente para a implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="cfa4e-115">Implantar um único site no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="cfa4e-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="cfa4e-116">Criar um site em sua implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="cfa4e-117">Implantar vários sites no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="cfa4e-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="cfa4e-118">Adicione sites à sua implantação e saiba mais sobre as diferenças entre implantações de um ou vários sites.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="cfa4e-119">Configurar a integração do Cloud Connector com sua organização do Microsoft 365 ou do Office 365</span><span class="sxs-lookup"><span data-stu-id="cfa4e-119">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="cfa4e-120">Adicione registros DNS, configure híbrido, configure gateways PSTN e habilite usuários para a caixa postal do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="cfa4e-121">Validar a implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="cfa4e-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="cfa4e-122">Certifique-se de que sua implantação está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="cfa4e-123">Atualizar para uma nova versão do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="cfa4e-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="cfa4e-124">Atualize sua implantação do Cloud Connector existente para a versão 2,1.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="cfa4e-125">Modificar a configuração de uma implantação do Cloud Connector existente</span><span class="sxs-lookup"><span data-stu-id="cfa4e-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="cfa4e-126">Altere as configurações no Cloud Connector depois que ele já estiver implantado.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="cfa4e-127">Implantar bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="cfa4e-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="cfa4e-128">Saiba como implantar o bypass de mídia no Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="cfa4e-129">Referência de cmdlet do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="cfa4e-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="cfa4e-130">Saiba mais sobre os cmdlets do PowerShell usados no Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="cfa4e-131">Solução de problemas de implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="cfa4e-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="cfa4e-132">Soluções para problemas comuns encontrados com uma implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="cfa4e-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

