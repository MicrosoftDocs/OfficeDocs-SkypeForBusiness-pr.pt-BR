---
title: Adicionar Backup do Chat Persistente do Repositório do SQL Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Configure os armazenamentos do SQL Server de backup que fornecerão bancos de dados de backup para o Servidor de Chat Persistente ou pool de Servidor de Chat Persistente.
ms.openlocfilehash: c21cd099372bb49b621447697320df2785a0c9dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818731"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="00098-103">Adicionar Backup do Chat Persistente do Repositório do SQL Server</span><span class="sxs-lookup"><span data-stu-id="00098-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="00098-104">Configure os armazenamentos do SQL Server de backup que fornecerão bancos de dados de backup para o Servidor de Chat Persistente ou pool de Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="00098-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="00098-105">**Sql Server store:** selecione um SQL Server existente e, opcionalmente, uma instância para Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="00098-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="00098-106">Clique **em Novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de backup de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="00098-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="00098-107">Marque a **caixa de** seleção Habilitar espelhamento do sql Server para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de backup de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="00098-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="00098-108">Selecione na lista **Espelhando o SQL Server,** armazene um SQL Server e uma instância opcional para atuar como o espelho do SQL Server para o SQL Server de backup de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="00098-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="00098-109">Clique **em Novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento do SQL Server de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="00098-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="00098-110">Selecione na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** um SQL Server que agirá como o servidor testemunha em cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="00098-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="00098-111">O servidor testemunha não espelha ou hospeda dados para os servidores de Chat Persistente, mas garante que apenas um SQL Server em uma configuração espelhada seja o SQL Server ativo a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="00098-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="00098-112">Clique **em Novo** para definir uma nova testemunha do SQL Server, opcionalmente, uma instância para a testemunha de espelhamento do SQL Server de backup de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="00098-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="00098-113">Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.</span><span class="sxs-lookup"><span data-stu-id="00098-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="00098-114">Clique **em Avançar** depois de terminar de inserir as opções para a configuração do sql Server store de backup desse pool e para prosseguir com a definição do pool do Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="00098-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="00098-115">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="00098-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="00098-116">Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.</span><span class="sxs-lookup"><span data-stu-id="00098-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00098-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="00098-117">See also</span></span>

[<span data-ttu-id="00098-118">Plano para Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="00098-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="00098-119">Requisitos de servidor para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="00098-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="00098-120">Requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="00098-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="00098-121">Configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="00098-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
