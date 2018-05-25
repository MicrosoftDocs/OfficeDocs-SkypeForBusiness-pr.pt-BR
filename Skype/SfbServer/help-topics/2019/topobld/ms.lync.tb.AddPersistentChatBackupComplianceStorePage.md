---
title: Adicionar Repositório de Servidor SQL de Backup de Conformidade de Chat Persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Configurar o Backup repositórios de conformidade do SQL Server que fornecerão bancos de dados de backup para o servidor de Chat persistente ou repositórios do SQL Server de conformidade do servidor de Chat persistente.
ms.openlocfilehash: 4e3a2bf034d5ab20c7352f2b6ef9c8a6a0c4befa
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="4b791-103">Adicionar Repositório de Servidor SQL de Backup de Conformidade de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="4b791-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="4b791-104">Configurar o Backup repositórios de conformidade do SQL Server que fornecerão bancos de dados de backup para o servidor de Chat persistente ou repositórios do SQL Server de conformidade do servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4b791-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="4b791-105">**O SQL Server store**: selecione um SQL Server existente e, opcionalmente, uma instância para o Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4b791-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="4b791-106">Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de backup de conformidade de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4b791-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="4b791-107">Marque a caixa de seleção **Habilitar o SQL Server store espelhamento** para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de backup de conformidade de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4b791-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="4b791-108">Selecione na lista **espelhando o SQL Server store** um SQL Server e uma instância opcional para agir como o espelho do SQL Server para o Chat persistente backup de conformidade do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4b791-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="4b791-109">Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento de Persistent Chat SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4b791-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="4b791-110">Na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático**, selecione um SQL Server que atuará como o servidor testemunha em cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="4b791-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="4b791-111">O servidor testemunha faz não os dados de espelho ou host para os servidores de Chat persistente, mas garante que apenas um SQL Server em uma configuração espelhada esteja ativo SQL Server a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="4b791-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="4b791-112">Clique em **novo** para definir uma nova testemunha de SQL Server e, opcionalmente, uma instância para o Chat persistente backup de conformidade testemunha de espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4b791-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="4b791-113">Clique em  **Voltar** para voltar à caixa de diálogo de definição de pool anterior.</span><span class="sxs-lookup"><span data-stu-id="4b791-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="4b791-114">Clique em **Avançar** depois de concluir a inserção das opções para configuração de repositório do SQL Server backup desse pool e para prosseguir com a definição do pool de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4b791-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="4b791-115">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="4b791-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="4b791-116">Clique em **Ajuda** para acessar a ajuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="4b791-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4b791-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4b791-117">See also</span></span>

#### 

[<span data-ttu-id="4b791-118">Planejar o servidor de Chat persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4b791-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="4b791-119">Requisitos de servidor do Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4b791-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="4b791-120">Requisitos de hardware e software para o servidor de Chat persistente no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4b791-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="4b791-121">Configurar o serviço de conformidade para o servidor de Chat persistente no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4b791-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="4b791-122">Configurar alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4b791-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

