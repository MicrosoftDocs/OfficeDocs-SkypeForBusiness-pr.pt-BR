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
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Defina o monitoramento do SQL Server Store configurando as seguintes propriedades:'
ms.openlocfilehash: 789083ad0743ed7baf94630c86e4647e218c336c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820853"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="f80b4-103">Adicionar Página de Repositório de Monitoramento do Front End</span><span class="sxs-lookup"><span data-stu-id="f80b4-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="f80b4-104">**Defina o monitoramento do SQL Server Store** configurando as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="f80b4-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="f80b4-105">**Monitorando a loja do SQL Server**: selecione um nome de domínio totalmente qualificado do SQL Server (e, opcionalmente, uma instância) na lista.</span><span class="sxs-lookup"><span data-stu-id="f80b4-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="f80b4-106">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para a loja do servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f80b4-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="f80b4-107">Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** se desejar adicionar o espelhamento de banco de dados para o servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f80b4-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="f80b4-108">Selecione um espelho existente do **SQL Server Store de monitoramento** na lista.</span><span class="sxs-lookup"><span data-stu-id="f80b4-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="f80b4-109">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o armazenamento de espelho.</span><span class="sxs-lookup"><span data-stu-id="f80b4-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="f80b4-110">Se você selecionou **habilitar o espelhamento da loja do SQL Server**, selecione **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** para selecionar um repositório de testemunha de espelhamento do SQL Server na lista.</span><span class="sxs-lookup"><span data-stu-id="f80b4-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="f80b4-111">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o armazenamento de testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="f80b4-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="f80b4-112">Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.</span><span class="sxs-lookup"><span data-stu-id="f80b4-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="f80b4-113">Clique em **Avançar** depois de concluir a inserção das opções para esta caixa de diálogo para continuar com a configuração.</span><span class="sxs-lookup"><span data-stu-id="f80b4-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="f80b4-114">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente.</span><span class="sxs-lookup"><span data-stu-id="f80b4-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="f80b4-115">Clique em **Ajuda** para acessar a ajuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="f80b4-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f80b4-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="f80b4-116">See also</span></span>

[<span data-ttu-id="f80b4-117">Associar um repositório de monitoramento com um Pool de Front-Ends no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f80b4-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
