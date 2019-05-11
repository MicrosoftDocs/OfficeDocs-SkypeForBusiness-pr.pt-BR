---
title: Instalar componentes de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Resumo: Leia este tópico para saber como usar o Skype para o Assistente de implantação do Business Server para instalar o Skype para serviços e componentes de negócios Server 2015.'
ms.openlocfilehash: 16b967c2f90ae5811be6bd6436b2025217a1efab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894539"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="3584e-103">Instalar componentes de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3584e-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3584e-104">**Resumo:** Leia este tópico para saber como usar o Skype para o Assistente de implantação do Business Server para instalar o Skype para serviços e componentes de negócios Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3584e-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="3584e-105">Antes de instalar os componentes de Chat persistente, certifique-se de que você já instalou pré-requisitos de hardware e software e criada a topologia apropriada para dar suporte ao servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3584e-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="3584e-106">Para obter detalhes sobre o planejamento e requisitos, consulte [Requirements for sua Skype para ambiente de negócios](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) e [Planejar Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="3584e-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="3584e-107">Para obter informações sobre como atualizar e publicar sua topologia para incluir o servidor de Chat persistente, consulte [Adicionar servidor de Chat persistente para seu Skype para a topologia de negócios Server 2015](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="3584e-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="3584e-108">Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3584e-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3584e-109">A mesma funcionalidade está disponível em equipes.</span><span class="sxs-lookup"><span data-stu-id="3584e-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="3584e-110">Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="3584e-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="3584e-111">Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3584e-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="3584e-112">Instalar e iniciar serviços</span><span class="sxs-lookup"><span data-stu-id="3584e-112">Install and start services</span></span>

<span data-ttu-id="3584e-113">Usando o Skype para o Assistente de implantação de servidor de negócios, escolha instalar ou Skype de atualização para o sistema de servidor de negócios para executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3584e-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="3584e-114">Instalar Repositório de Configuração Local</span><span class="sxs-lookup"><span data-stu-id="3584e-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="3584e-115">Configurar ou Remover Componentes do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3584e-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="3584e-116">Solicitar, Instalar ou Atribuir Certificados</span><span class="sxs-lookup"><span data-stu-id="3584e-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="3584e-117">Iniciar serviços</span><span class="sxs-lookup"><span data-stu-id="3584e-117">Start services</span></span>
    
<span data-ttu-id="3584e-118">Para obter detalhes sobre como usar o Assistente de implantação para instalar componentes, atribuir certificados e iniciar os serviços, consulte [Instalar Skype para Business Server 2015](../../deploy/install/install.md) e [Instale o Skype para negócios 2015 de servidor nos servidores na topologia](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="3584e-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

