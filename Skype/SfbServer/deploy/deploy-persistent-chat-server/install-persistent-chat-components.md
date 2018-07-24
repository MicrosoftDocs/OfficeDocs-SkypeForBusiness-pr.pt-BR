---
title: Instalar componentes de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Resumo: Leia este tópico para saber como usar o Skype para o Assistente de implantação do Business Server para instalar o Skype para serviços e componentes de negócios Server 2015.'
ms.openlocfilehash: d8c094c09160077dc98f68a9e98e4726f60ecaeb
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006871"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="dd945-103">Instalar componentes de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dd945-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dd945-104">**Resumo:** Leia este tópico para saber como usar o Skype para o Assistente de implantação do Business Server para instalar o Skype para serviços e componentes de negócios Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dd945-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="dd945-105">Antes de instalar os componentes de Chat persistente, certifique-se de que você já instalou pré-requisitos de hardware e software e criada a topologia apropriada para dar suporte ao servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dd945-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="dd945-106">Para obter detalhes sobre o planejamento e requisitos, consulte [Requirements for sua Skype para ambiente de negócios](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) e [Planejar Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd945-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="dd945-107">Para obter informações sobre como atualizar e publicar sua topologia para incluir o servidor de Chat persistente, consulte [Adicionar servidor de Chat persistente para seu Skype para a topologia de negócios Server 2015](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd945-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="dd945-108">Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="dd945-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="dd945-109">A mesma funcionalidade está disponível em equipes.</span><span class="sxs-lookup"><span data-stu-id="dd945-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="dd945-110">Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="dd945-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="dd945-111">Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dd945-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="dd945-112">Instalar e iniciar serviços</span><span class="sxs-lookup"><span data-stu-id="dd945-112">Install and start services</span></span>

<span data-ttu-id="dd945-113">Usando o Skype para o Assistente de implantação de servidor de negócios, escolha instalar ou Skype de atualização para o sistema de servidor de negócios para executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="dd945-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="dd945-114">Instalar Repositório de Configuração Local</span><span class="sxs-lookup"><span data-stu-id="dd945-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="dd945-115">Configurar ou Remover Componentes do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd945-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="dd945-116">Solicitar, Instalar ou Atribuir Certificados</span><span class="sxs-lookup"><span data-stu-id="dd945-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="dd945-117">Iniciar serviços</span><span class="sxs-lookup"><span data-stu-id="dd945-117">Start services</span></span>
    
<span data-ttu-id="dd945-118">Para obter detalhes sobre como usar o Assistente de implantação para instalar componentes, atribuir certificados e iniciar os serviços, consulte [Instalar Skype para Business Server 2015](../../deploy/install/install.md) e [Instale o Skype para negócios 2015 de servidor nos servidores na topologia](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd945-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

