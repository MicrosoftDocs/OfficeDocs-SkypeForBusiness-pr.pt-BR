---
title: Instalar componentes de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Resumo: Leia este tópico para saber como usar o assistente de implantação do Skype for Business Server para instalar componentes e serviços do Skype for Business Server 2015.'
ms.openlocfilehash: 019700b169c3507540c93a3a152c3741de2681fb
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795682"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="ac689-103">Instalar componentes de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ac689-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ac689-104">**Resumo:** Leia este tópico para saber como usar o assistente de implantação do Skype for Business Server para instalar componentes e serviços do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ac689-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="ac689-105">Antes de instalar componentes de chat persistente, certifique-se de que você já tenha instalado o hardware e o software de pré-requisito e criou a topologia apropriada para dar suporte ao servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ac689-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="ac689-106">Para obter detalhes sobre planejamento e requisitos, consulte [requisitos para o seu ambiente Skype for Business](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) e [plano para servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="ac689-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="ac689-107">Para obter informações sobre como atualizar e publicar sua topologia para incluir um servidor de chat persistente, consulte [Adicionar servidor de chat persistente à sua topologia do Skype for Business Server 2015](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="ac689-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="ac689-108">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ac689-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ac689-109">A mesma funcionalidade está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac689-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="ac689-110">Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="ac689-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="ac689-111">Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ac689-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="ac689-112">Instalar e iniciar serviços</span><span class="sxs-lookup"><span data-stu-id="ac689-112">Install and start services</span></span>

<span data-ttu-id="ac689-113">Usando o assistente de implantação do Skype for Business Server, escolha instalar ou atualizar o sistema do Skype for Business Server para executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ac689-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="ac689-114">Instalar Repositório de Configuração Local</span><span class="sxs-lookup"><span data-stu-id="ac689-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="ac689-115">Configurar ou Remover Componentes do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ac689-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="ac689-116">Solicitar, Instalar ou Atribuir Certificados</span><span class="sxs-lookup"><span data-stu-id="ac689-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="ac689-117">Iniciar serviços</span><span class="sxs-lookup"><span data-stu-id="ac689-117">Start services</span></span>
    
<span data-ttu-id="ac689-118">Para obter detalhes sobre como usar o assistente de implantação para instalar componentes, atribuir certificados e iniciar serviços, consulte [instalar o Skype for Business server 2015](../../deploy/install/install.md) e [instalar o Skype for Business Server 2015 em servidores na topologia](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="ac689-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

