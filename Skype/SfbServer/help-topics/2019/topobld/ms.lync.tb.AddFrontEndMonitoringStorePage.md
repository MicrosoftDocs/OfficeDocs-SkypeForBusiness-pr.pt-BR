---
title: Adicionar Página de Repositório de Monitoramento de Front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Defina o armazenamento do SQL Server de monitoramento configurando as seguintes propriedades:'
ms.openlocfilehash: e867ec998e1380e70125d0ad743f83b06737758e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811661"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="0ebcc-103">Adicionar Página de Repositório de Monitoramento de Front-end</span><span class="sxs-lookup"><span data-stu-id="0ebcc-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="0ebcc-104">Defina **o armazenamento do SQL Server de monitoramento** configurando as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="0ebcc-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="0ebcc-105">**Monitoramento do armazenamento do SQL Server:** selecione um nome de domínio totalmente qualificado do SQL Server (e, opcionalmente, uma instância) na lista.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="0ebcc-106">Clique **em** Novo para criar uma nova definição FQDN do SQL Server e, opcionalmente, um nome de instância para o armazenamento do Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="0ebcc-107">Marque a **caixa de seleção Habilitar** espelhamento do armazenamento do SQL Server se quiser adicionar espelhamento de banco de dados para o Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="0ebcc-108">Selecione um espelho existente **do armazenamento do SQL Server de monitoramento** na lista.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="0ebcc-109">Clique **em Novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o armazenamento espelho.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="0ebcc-110">Se você selecionou Habilitar espelhamento do armazenamento do **SQL Server,** selecione Usar testemunha de espelhamento do SQL Server para habilitar o **failover** automático para selecionar um armazenamento testemunha de espelhamento do SQL Server na lista.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="0ebcc-111">Clique **em Novo** para criar uma nova definição FQDN do SQL Server e, opcionalmente, um nome de instância para o armazenamento de testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="0ebcc-112">Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="0ebcc-113">Clique **em Avançar** depois de terminar de inserir as opções dessa caixa de diálogo para prosseguir com a configuração.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="0ebcc-114">Clique **em Cancelar** para descartar todas as alterações e encerrar o assistente.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="0ebcc-115">Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.</span><span class="sxs-lookup"><span data-stu-id="0ebcc-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0ebcc-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="0ebcc-116">See also</span></span>

[<span data-ttu-id="0ebcc-117">Associar um armazenamento de monitoramento a um pool de Front-End no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0ebcc-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
