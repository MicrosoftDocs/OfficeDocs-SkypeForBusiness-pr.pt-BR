---
title: Adicionar Repositório de SQL Server de Backup de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Configure os repositórios de Backup do SQL Server que fornecerão bancos de dados de backup para o servidor de Chat persistente ou o pool de servidor de Chat persistente.
ms.openlocfilehash: 2d9a583ad13fe2cba6d39ff737d8071fb5027297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897776"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="25632-103">Adicionar Repositório de SQL Server de Backup de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="25632-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="25632-104">Configure os repositórios de Backup do SQL Server que fornecerão bancos de dados de backup para o servidor de Chat persistente ou o pool de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="25632-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="25632-105">**O SQL Server store**: selecione um SQL Server existente e, opcionalmente, uma instância para o Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="25632-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="25632-106">Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de backup de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="25632-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="25632-107">Marque a caixa de seleção de **espelhamento do repositório de habilitar o SQL Server** para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de backup de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="25632-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="25632-108">Selecione na lista **espelhando o SQL Server store** um SQL Server e uma instância opcional para agir como o espelho do SQL Server para o SQL Server de backup Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="25632-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="25632-109">Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento de Persistent Chat SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25632-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="25632-110">Na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático**, selecione um SQL Server que atuará como o servidor testemunha em cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="25632-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="25632-111">O servidor testemunha faz não os dados de espelho ou host para os servidores de Chat persistente, mas garante que apenas um SQL Server em uma configuração espelhada esteja ativo SQL Server a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="25632-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="25632-112">Clique em **novo** para definir uma nova testemunha de SQL Server e, opcionalmente, uma instância do Chat persistente backup SQL Server testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="25632-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="25632-113">Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.</span><span class="sxs-lookup"><span data-stu-id="25632-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="25632-114">Clique em **Avançar** depois de concluir a inserção das opções para configuração de repositório do SQL Server backup desse pool e para prosseguir com a definição do pool de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="25632-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="25632-115">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="25632-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="25632-116">Clique em **Ajuda** para acessar a ajuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="25632-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="25632-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="25632-117">See also</span></span>

[<span data-ttu-id="25632-118">Planejar Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="25632-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="25632-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="25632-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="25632-120">Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="25632-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="25632-121">Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="25632-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
