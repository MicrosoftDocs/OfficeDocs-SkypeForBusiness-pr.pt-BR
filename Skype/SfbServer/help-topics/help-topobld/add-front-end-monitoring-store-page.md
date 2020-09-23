---
title: Adicionar Página de Repositório de Monitoramento do Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Defina o monitoramento do SQL Server Store configurando as seguintes propriedades:'
ms.openlocfilehash: 85b8518bb533de68423dea93f259fc7b927ed9ba
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218872"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="4fd8d-103">Adicionar Página de Repositório de Monitoramento do Front End</span><span class="sxs-lookup"><span data-stu-id="4fd8d-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="4fd8d-104">**Defina o monitoramento do SQL Server Store** configurando as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="4fd8d-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="4fd8d-105">**Monitoramento do SQL Server Store**: selecione um nome de domínio totalmente qualificado do SQL Server (e, opcionalmente, uma instância) na lista.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="4fd8d-106">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório do servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="4fd8d-107">Marque a caixa de seleção **habilitar espelhamento do repositório do SQL Server** se quiser adicionar o espelhamento de banco de dados para o servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="4fd8d-108">Selecione um **espelhamento de repositório do SQL Server de monitoramento** existente na lista.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="4fd8d-109">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório de espelho.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="4fd8d-110">Se você selecionou **habilitar espelhamento de repositório do SQL Server**, selecione, opcionalmente, **usar testemunha de espelhamento do SQL Server para habilitar o failover automático** para selecionar um repositório de testemunha de espelhamento do SQL Server na lista.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="4fd8d-111">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório de testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="4fd8d-112">Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="4fd8d-113">Clique em **Avançar** depois de concluir a inserção das opções para essa caixa de diálogo para prosseguir com a configuração.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="4fd8d-114">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="4fd8d-115">Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.</span><span class="sxs-lookup"><span data-stu-id="4fd8d-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4fd8d-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="4fd8d-116">See also</span></span>

[<span data-ttu-id="4fd8d-117">Associar um repositório de monitoramento a um pool de front-ends no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4fd8d-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
