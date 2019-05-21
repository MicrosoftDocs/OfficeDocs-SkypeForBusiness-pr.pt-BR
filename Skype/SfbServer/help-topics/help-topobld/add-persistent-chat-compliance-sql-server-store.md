---
title: Adicionar Repositório do SQL Server de Conformidade de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Você configura as lojas de conformidade do SQL Server que fornecerão bancos de dados para o servidor de chat persistente ou o recurso de conformidade do servidor de chat persistente.
ms.openlocfilehash: 79d7351563f049c7d05a0d592ecb3d65dba3eebb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281757"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="f6ba7-103">Adicionar Repositório do SQL Server de Conformidade de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="f6ba7-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="f6ba7-104">Você configura as lojas de conformidade do SQL Server que fornecerão bancos de dados para o servidor de chat persistente ou o recurso de conformidade do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="f6ba7-105">**Repositório do SQL Server**: selecione um SQL Server existente e, opcionalmente, uma instância para o chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="f6ba7-106">Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="f6ba7-107">Marque a caixa de seleção Habilitar o espelhamento da **loja do SQL Server** para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de conformidade do chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="f6ba7-108">Selecione na lista espelhamento do **SQL Server Store** uma instância do SQL Server e opcional para atuar como o espelho do SQL Server do SQL Server compatível com o chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="f6ba7-109">Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento de chat persistente do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="f6ba7-110">Na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático**, selecione um SQL Server que atuará como o servidor testemunha em cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="f6ba7-111">O servidor testemunha não espelha ou hospeda dados para os servidores de chat persistentes, mas garante que apenas um SQL Server em uma configuração espelhada seja o SQL Server ativo a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="f6ba7-112">Clique em **novo** para definir um novo SQL Server testemunha opcionalmente uma instância para a testemunha de espelhamento do SQL Server compatível com o chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="f6ba7-113">Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="f6ba7-114">Clique em **Avançar** depois de terminar de inserir as opções para a configuração do SQL Server Store de backup do pool e para continuar com a definição do pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="f6ba7-115">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="f6ba7-116">Clique em **Ajuda** para acessar a ajuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="f6ba7-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f6ba7-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="f6ba7-117">See also</span></span>

[<span data-ttu-id="f6ba7-118">Planejar Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6ba7-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="f6ba7-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6ba7-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="f6ba7-120">Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6ba7-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="f6ba7-121">Configurar o serviço de Conformidade para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6ba7-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
