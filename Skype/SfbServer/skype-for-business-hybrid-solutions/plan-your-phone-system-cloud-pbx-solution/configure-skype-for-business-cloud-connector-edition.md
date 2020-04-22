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
description: Saiba como configurar o Skype for Business Cloud Connector Edition, uma topologia local mínima para permitir a integração de sua infraestrutura de voz local com o sistema de telefonia no Office 365 (Cloud PBX) serviços de voz no Skype for Business online.
ms.openlocfilehash: aa0d8fb37dcaddaca3835b25b94eba6a18e03636
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779157"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="b4c6c-103">Configurar e gerenciar o Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="b4c6c-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="b4c6c-104">Saiba como configurar o Skype for Business Cloud Connector Edition, uma topologia local mínima para permitir a integração de sua infraestrutura de voz local com o sistema de telefonia no Office 365 (Cloud PBX) serviços de voz no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="b4c6c-105">Antes de começar, examine os pré-requisitos em [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="b4c6c-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b4c6c-106">As etapas neste tópico se aplicam apenas ao Cloud Connector Edition 1.4.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="b4c6c-107">Se você ainda não tiver atualizado para o Cloud Connector Edition 2,1, consulte [upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b4c6c-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="b4c6c-108">Você pode baixar o arquivo de instalação [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)do.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="b4c6c-109">Etapas para configurar o Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="b4c6c-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="b4c6c-110">A tabela a seguir lista as etapas necessárias para instalar e configurar o Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="b4c6c-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="b4c6c-111">**Etapa**</span><span class="sxs-lookup"><span data-stu-id="b4c6c-111">**Step**</span></span>|<span data-ttu-id="b4c6c-112">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b4c6c-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b4c6c-113">Preparar o dispositivo do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b4c6c-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="b4c6c-114">Baixar o arquivo de instalação, preparar certificados, configurar o Hyper-V e preparar seu ambiente para a implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="b4c6c-115">Implantar um único site no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b4c6c-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="b4c6c-116">Criar um site em sua implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="b4c6c-117">Implantar vários sites no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b4c6c-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="b4c6c-118">Adicione sites à sua implantação e saiba mais sobre as diferenças entre implantações de um ou vários sites.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="b4c6c-119">Configurar a integração do Cloud Connector com sua organização do Office 365</span><span class="sxs-lookup"><span data-stu-id="b4c6c-119">Configure Cloud Connector integration with your Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="b4c6c-120">Adicione registros DNS, configure híbrido, configure gateways PSTN e habilite usuários para o sistema de telefonia na caixa postal do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="b4c6c-121">Validar sua implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b4c6c-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="b4c6c-122">Certifique-se de que sua implantação está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="b4c6c-123">Atualização para uma nova versão do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b4c6c-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="b4c6c-124">Atualize sua implantação do Cloud Connector existente para a versão 2,1.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="b4c6c-125">Modificar a configuração de uma implantação existente do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b4c6c-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="b4c6c-126">Altere as configurações no Cloud Connector depois que ele já estiver implantado.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="b4c6c-127">Implantar bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="b4c6c-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="b4c6c-128">Saiba como implantar o bypass de mídia no Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="b4c6c-129">Referência do cmdlet do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b4c6c-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="b4c6c-130">Saiba mais sobre os cmdlets do PowerShell usados no Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="b4c6c-131">Solucionar problemas de implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b4c6c-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="b4c6c-132">Soluções para problemas comuns encontrados com uma implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b4c6c-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

