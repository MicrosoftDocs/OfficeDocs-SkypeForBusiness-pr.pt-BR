---
title: Adicionar monitoramento de diretor
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
description: 'Você pode definir o SQL Server store de monitoramento Configurando as propriedades a seguintes:'
ms.openlocfilehash: cb246ab0fb6413e5bc47ac2d18a9f568d0571f9d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973868"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="63494-103">Adicionar monitoramento de diretor</span><span class="sxs-lookup"><span data-stu-id="63494-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="63494-104">Você pode **definir o SQL Server store de monitoramento** Configurando as propriedades a seguintes:</span><span class="sxs-lookup"><span data-stu-id="63494-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="63494-105">**Monitorando o SQL Server store**: selecione um nome de domínio totalmente qualificado do SQL Server (FQDN) (e, opcionalmente, uma instância nomeada do SQL Server) na lista.</span><span class="sxs-lookup"><span data-stu-id="63494-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="63494-106">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório do Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="63494-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="63494-107">Se você deseja adicionar o espelhamento de banco de dados para o Monitoring Server, marque a caixa de seleção **Habilitar o SQL Server store de espelhamento** .</span><span class="sxs-lookup"><span data-stu-id="63494-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="63494-108">Selecione um **espelho de repositório de monitoramento do SQL Server** de existente na lista.</span><span class="sxs-lookup"><span data-stu-id="63494-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="63494-109">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório de espelho.</span><span class="sxs-lookup"><span data-stu-id="63494-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="63494-110">Se você selecionou o **espelhamento do repositório de habilitar o SQL Server**, selecione, opcionalmente, **Use o SQL Server espelhamento testemunha para habilitar o failover automático** para selecionar um repositório de testemunha da lista de espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63494-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="63494-111">Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório de testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="63494-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="63494-112">Clique em  **Voltar** para voltar à caixa de diálogo de definição de pool anterior.</span><span class="sxs-lookup"><span data-stu-id="63494-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="63494-113">Clique em **Avançar** depois de concluir a inserção das opções para essa caixa de diálogo prosseguir com a configuração.</span><span class="sxs-lookup"><span data-stu-id="63494-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="63494-114">Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente.</span><span class="sxs-lookup"><span data-stu-id="63494-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="63494-115">Clique em **Ajuda** para acessar a Ajuda sensível ao contexto, como esta página.</span><span class="sxs-lookup"><span data-stu-id="63494-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

