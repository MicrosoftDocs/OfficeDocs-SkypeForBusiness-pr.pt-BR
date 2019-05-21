---
title: Preparar Domínio Atual
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Para preparar um domínio para servidores host que executam os usuários do Skype for Business Server 2015 ou do Skype for Business Server, você deve concluir a etapa 5: preparar o domínio atual, conforme descrito no tópico usando a configuração para executar a preparação do domínio. Para completar a etapa, é necessário estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores de Empresa da floresta a qual o domínio pertence. Para preparar o domínio:'
ms.openlocfilehash: 93fef28bdcaa720f1adcf893ec634dbe8f373780
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283875"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="a6554-105">Preparar Domínio Atual</span><span class="sxs-lookup"><span data-stu-id="a6554-105">Prepare Current Domain</span></span>

<span data-ttu-id="a6554-106">Para preparar um domínio para servidores host que executam os usuários do Skype for Business Server 2015 ou do Skype for Business Server, você deve concluir a **etapa 5: preparar o domínio atual**, conforme descrito no tópico [usando a configuração para executar a preparação do domínio](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span><span class="sxs-lookup"><span data-stu-id="a6554-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="a6554-107">Para completar a etapa, é necessário estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores de Empresa da floresta a qual o domínio pertence.</span><span class="sxs-lookup"><span data-stu-id="a6554-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="a6554-108">Para preparar o domínio:</span><span class="sxs-lookup"><span data-stu-id="a6554-108">To prepare the domain:</span></span>

1. <span data-ttu-id="a6554-109">Na pasta de instalação ou mídia do Skype for Business Server 2015, execute Setup. exe para iniciar o assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a6554-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="a6554-110">Clique em **Preparar o Active Directory** e espere que o estado da implantação seja determinado.</span><span class="sxs-lookup"><span data-stu-id="a6554-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="a6554-111">Na **Etapa 5: preparar o domínio atual**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a6554-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="a6554-112">Na página **Executando Comandos**, procure **Status da tarefa: Concluída** e clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="a6554-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="a6554-113">Na coluna **ação** , expanda o **domínio Prep**, procure um \*\* \<resultado\> \*\* de execução de sucesso no final de cada tarefa para verificar se a preparação do domínio foi concluída com êxito, feche o log e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="a6554-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="a6554-114">Se precisar examinar os arquivos de log criados pelo assistente de implantação do Skype for Business Server, você poderá encontrá-los no computador em que o assistente de implantação foi executado no diretório de usuários do usuário dos serviços de domínio Active Directory que executou a etapa.</span><span class="sxs-lookup"><span data-stu-id="a6554-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="a6554-115">Por exemplo, se o usuário tiver entrado como administrador do domínio no domínio Contoso.net, os arquivos de log serão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="a6554-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


