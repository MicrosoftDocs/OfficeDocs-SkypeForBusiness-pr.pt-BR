---
title: Adicionar Repositório de Servidor SQL de Chat Persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Configure os repositórios do SQL Server que fornecerão bancos de dados para o servidor de Chat persistente ou o pool de servidor de Chat persistente.
ms.openlocfilehash: 062092ff60fa30f7b8ac19725a12a3f62e1b9ec6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="e20b6-103">Adicionar Repositório de Servidor SQL de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="e20b6-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="e20b6-104">Configure os repositórios do SQL Server que fornecerão bancos de dados para o servidor de Chat persistente ou o pool de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e20b6-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="e20b6-105">**O SQL Server store**: selecione um SQL Server existente e, opcionalmente, uma instância para o Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e20b6-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="e20b6-106">Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e20b6-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="e20b6-107">Marque a caixa de seleção **Habilitar o SQL Server store espelhamento** para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e20b6-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="e20b6-108">Selecione na lista **espelhando o SQL Server store** um SQL Server e uma instância opcional para agir como o espelho do SQL Server para o SQL Server de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e20b6-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="e20b6-109">Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento de Persistent Chat SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e20b6-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="e20b6-110">Na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático**, selecione um SQL Server que atuará como o servidor testemunha em cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="e20b6-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="e20b6-111">O servidor testemunha faz não os dados de espelho ou host para os servidores de Chat persistente, mas garante que apenas um SQL Server em uma configuração espelhada esteja ativo SQL Server a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="e20b6-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="e20b6-112">Clique em **novo** para definir uma nova testemunha de SQL Server, opcionalmente, uma instância para o servidor de SQL Chat persistente testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="e20b6-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="e20b6-113">Clique em  **Voltar** para voltar à caixa de diálogo de definição de pool anterior.</span><span class="sxs-lookup"><span data-stu-id="e20b6-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="e20b6-114">Clique em **Avançar** depois de concluir a inserção das opções para configuração de repositório do SQL Server desse pool e para prosseguir com a definição do pool de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e20b6-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="e20b6-115">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="e20b6-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="e20b6-116">Clique em **Ajuda** para acessar a ajuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="e20b6-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e20b6-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e20b6-117">See also</span></span>

#### 

[<span data-ttu-id="e20b6-118">Planejar o servidor de Chat persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e20b6-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="e20b6-119">Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015</span><span class="sxs-lookup"><span data-stu-id="e20b6-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="e20b6-120">Requisitos de hardware e software para o servidor de Chat persistente no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e20b6-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="e20b6-121">Requisitos de servidor do Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e20b6-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="e20b6-122">Noções básicas de topologia para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e20b6-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="e20b6-123">Configurar alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e20b6-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

