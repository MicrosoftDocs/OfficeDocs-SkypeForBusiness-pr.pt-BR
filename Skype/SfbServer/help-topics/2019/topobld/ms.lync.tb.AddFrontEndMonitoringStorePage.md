---
title: Adicionar Página de Repositório de Monitoramento do Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Você definir o repositório de monitoramento do SQL Server, definindo as seguintes propriedades:'
ms.openlocfilehash: d77f32f189423f82fba088427b49b7bbb5e67ba1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906852"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="972e2-103">Adicionar Página de Repositório de Monitoramento do Front End</span><span class="sxs-lookup"><span data-stu-id="972e2-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="972e2-104">Você **definir o SQL Server store de monitoramento** Configurando as propriedades a seguintes:</span><span class="sxs-lookup"><span data-stu-id="972e2-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="972e2-105">**Monitorando o SQL Server store**: selecione um nome de domínio totalmente qualificado do SQL Server (e, opcionalmente, uma instância) na lista.</span><span class="sxs-lookup"><span data-stu-id="972e2-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="972e2-106">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório do Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="972e2-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="972e2-107">Se você deseja adicionar o espelhamento de banco de dados para o Monitoring Server, marque a caixa de seleção **Habilitar o SQL Server store de espelhamento** .</span><span class="sxs-lookup"><span data-stu-id="972e2-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="972e2-108">Selecione um **espelho de repositório de monitoramento do SQL Server** de existente na lista.</span><span class="sxs-lookup"><span data-stu-id="972e2-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="972e2-109">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório de espelho.</span><span class="sxs-lookup"><span data-stu-id="972e2-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="972e2-110">Se você selecionou o **espelhamento do repositório de habilitar o SQL Server**, selecione, opcionalmente, **Use o SQL Server espelhamento testemunha para habilitar o failover automático** para selecionar um repositório de testemunha da lista de espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="972e2-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="972e2-111">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório de testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="972e2-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="972e2-112">Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.</span><span class="sxs-lookup"><span data-stu-id="972e2-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="972e2-113">Clique em **Avançar** depois de concluir a inserção das opções para essa caixa de diálogo prosseguir com a configuração.</span><span class="sxs-lookup"><span data-stu-id="972e2-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="972e2-114">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente.</span><span class="sxs-lookup"><span data-stu-id="972e2-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="972e2-115">Clique em **Ajuda** para acessar a ajuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="972e2-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="972e2-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="972e2-116">See also</span></span>

[<span data-ttu-id="972e2-117">Associar um repositório de monitoramento um pool de Front-End no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="972e2-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
