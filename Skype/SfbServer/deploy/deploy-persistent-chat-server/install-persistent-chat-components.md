---
title: Instalar componentes de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Resumo: Leia este tópico para saber como usar o Assistente de Implantação do Skype for Business Server para instalar componentes e serviços do Skype for Business Server 2015.'
ms.openlocfilehash: c3e68d5b5a41d06544f030df6877828da4b87c9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802081"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="72fa9-103">Instalar componentes de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="72fa9-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="72fa9-104">**Resumo:** Leia este tópico para saber como usar o Assistente de Implantação do Skype for Business Server para instalar componentes e serviços do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="72fa9-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="72fa9-105">Antes de instalar os componentes de Chat Persistente, certifique-se de já ter instalado o hardware e o software de pré-requisito e criado a topologia apropriada para dar suporte ao Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="72fa9-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="72fa9-106">Para obter detalhes sobre planejamento e requisitos, consulte [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and Plan for Persistent Chat Server in Skype for Business Server [2015.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="72fa9-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="72fa9-107">Para obter informações sobre como atualizar e publicar sua topologia para incluir o Servidor de Chat Persistente, consulte Adicionar Servidor de Chat Persistente à sua topologia do [Skype for Business Server 2015.](add-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="72fa9-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="72fa9-108">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="72fa9-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="72fa9-109">A mesma funcionalidade está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="72fa9-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="72fa9-110">Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="72fa9-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="72fa9-111">Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="72fa9-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="72fa9-112">Instalar e iniciar serviços</span><span class="sxs-lookup"><span data-stu-id="72fa9-112">Install and start services</span></span>

<span data-ttu-id="72fa9-113">Usando o Assistente de Implantação do Skype for Business Server, escolha Instalar ou Atualizar o Sistema Skype for Business Server para executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="72fa9-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="72fa9-114">Instalar Repositório de Configuração Local</span><span class="sxs-lookup"><span data-stu-id="72fa9-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="72fa9-115">Configurar ou Remover Componentes do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="72fa9-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="72fa9-116">Solicitar, Instalar ou Atribuir Certificados</span><span class="sxs-lookup"><span data-stu-id="72fa9-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="72fa9-117">Iniciar serviços</span><span class="sxs-lookup"><span data-stu-id="72fa9-117">Start services</span></span>
    
<span data-ttu-id="72fa9-118">Para obter detalhes sobre como usar o Assistente de Implantação para instalar componentes, atribuir certificados e iniciar serviços, consulte Instalar o [Skype for Business Server 2015](../../deploy/install/install.md) e instalar o Skype for Business Server [2015](../../deploy/install/install-skype-for-business-server.md)em servidores na topologia.</span><span class="sxs-lookup"><span data-stu-id="72fa9-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

