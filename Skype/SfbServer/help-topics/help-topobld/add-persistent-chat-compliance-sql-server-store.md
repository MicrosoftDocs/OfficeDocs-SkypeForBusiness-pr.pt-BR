---
title: Adicionar Repositório de Servidor SQL de Conformidade de Bate-papo Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Você configura os repositórios de conformidade do SQL Server que fornecerão bancos de dados para o servidor de chat persistente ou o recurso de conformidade do servidor de chat persistente.
ms.openlocfilehash: 748fe7a0798bc8e10d3d10832763d5c3e1f55648
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218682"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="7da9e-103">Adicionar Repositório de Servidor SQL de Conformidade de Bate-papo Persistente</span><span class="sxs-lookup"><span data-stu-id="7da9e-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="7da9e-104">Você configura os repositórios de conformidade do SQL Server que fornecerão bancos de dados para o servidor de chat persistente ou o recurso de conformidade do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7da9e-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="7da9e-105">**Repositório do SQL Server**: selecione um SQL Server existente e, opcionalmente, uma instância para o chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7da9e-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="7da9e-106">Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de conformidade do chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7da9e-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="7da9e-107">Marque a caixa de seleção **habilitar espelhamento do SQL Server Store** para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de conformidade do chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7da9e-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="7da9e-108">Selecione na lista **espelhamento do SQL Server Store** um SQL Server e uma instância opcional para atuar como o espelho do SQL Server para o SQL Server de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7da9e-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="7da9e-109">Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento do SQL Server do chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7da9e-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="7da9e-110">Selecione na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** um SQL Server que agirá como o servidor testemunha em cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="7da9e-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="7da9e-111">O servidor testemunha não espelha ou hospeda dados para os servidores de chat persistente, mas garante que apenas um SQL Server em uma configuração espelhada seja o SQL Server ativo a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="7da9e-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="7da9e-112">Clique em **novo** para definir uma nova testemunha do SQL Server, opcionalmente, uma instância para a testemunha de espelhamento do SQL Server de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7da9e-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="7da9e-113">Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.</span><span class="sxs-lookup"><span data-stu-id="7da9e-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="7da9e-114">Clique em **Avançar** depois de inserir as opções para a configuração do SQL Server Store de backup desse pool e para prosseguir com a definição do pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7da9e-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="7da9e-115">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="7da9e-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="7da9e-116">Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.</span><span class="sxs-lookup"><span data-stu-id="7da9e-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7da9e-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="7da9e-117">See also</span></span>

[<span data-ttu-id="7da9e-118">Planejar o servidor de chat persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7da9e-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="7da9e-119">Requisitos de servidor para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7da9e-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="7da9e-120">Requisitos de hardware e software para o servidor de chat persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7da9e-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="7da9e-121">Configurar o serviço de conformidade para o servidor de chat persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7da9e-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
