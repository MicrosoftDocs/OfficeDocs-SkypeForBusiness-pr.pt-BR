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
description: Saiba como configurar o Skype for Business Cloud Connector Edition, uma topologia local mínima para habilitar a integração da infraestrutura de voz local com os serviços de voz do Sistema de Telefonia (Cloud PBX) no Skype for Business Online.
ms.openlocfilehash: 4d24e5a312275158f276856aa78396ad63dff615
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094869"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="e9da9-103">Configurar e gerenciar o Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="e9da9-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="e9da9-104">O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="e9da9-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="e9da9-105">Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="e9da9-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="e9da9-106">Saiba como configurar o Skype for Business Cloud Connector Edition, uma topologia local mínima para habilitar a integração da infraestrutura de voz local com os serviços de voz do Sistema de Telefonia (Cloud PBX) no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="e9da9-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="e9da9-107">Antes de começar, você deve revisar os pré-requisitos em [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="e9da9-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e9da9-108">As etapas deste tópico aplicam-se somente ao Cloud Connector Edition 1.4.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="e9da9-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="e9da9-109">Se você ainda não tiver atualizado para o Cloud Connector Edition 2.1, consulte [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="e9da9-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="e9da9-110">Você pode baixar o arquivo de instalação de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="e9da9-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="e9da9-111">Etapas para configurar o Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="e9da9-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="e9da9-112">A tabela a seguir lista as etapas necessárias para instalar e configurar o Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="e9da9-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="e9da9-113">**Etapa**</span><span class="sxs-lookup"><span data-stu-id="e9da9-113">**Step**</span></span>|<span data-ttu-id="e9da9-114">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e9da9-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e9da9-115">Preparar o dispositivo do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e9da9-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="e9da9-116">Baixe o arquivo de instalação, prepare certificados, configure o Hyper-V e prepare seu ambiente para a implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e9da9-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="e9da9-117">Implantar um único site no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e9da9-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="e9da9-118">Crie um site em sua implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e9da9-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="e9da9-119">Implantar vários sites no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e9da9-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="e9da9-120">Adicione sites à sua implantação e saiba mais sobre as diferenças entre implantações individuais e multi-sites.</span><span class="sxs-lookup"><span data-stu-id="e9da9-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="e9da9-121">Configurar a integração do Cloud Connector com sua organização do Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="e9da9-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="e9da9-122">Adicionar registros DNS, configurar híbridos, configurar gateways PSTN e habilitar usuários para caixa postal do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="e9da9-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="e9da9-123">Validar a implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e9da9-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="e9da9-124">Certifique-se de que sua implantação está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="e9da9-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="e9da9-125">Atualizar para uma nova versão do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e9da9-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="e9da9-126">Atualize sua implantação existente do Cloud Connector para a versão 2.1.</span><span class="sxs-lookup"><span data-stu-id="e9da9-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="e9da9-127">Modificar a configuração de uma implantação do Cloud Connector existente</span><span class="sxs-lookup"><span data-stu-id="e9da9-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="e9da9-128">Altere as configurações no Cloud Connector depois que ele já for implantado.</span><span class="sxs-lookup"><span data-stu-id="e9da9-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="e9da9-129">Implantar bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="e9da9-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="e9da9-130">Saiba como implantar o bypass de mídia no Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e9da9-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="e9da9-131">Referência de cmdlet do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e9da9-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="e9da9-132">Saiba mais sobre os cmdlets do PowerShell usados no Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e9da9-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="e9da9-133">Solução de problemas de implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e9da9-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="e9da9-134">Soluções para problemas comuns encontrados com uma implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e9da9-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
