---
title: Preparar Domínio Atual
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para preparar um domínio para hospedar servidores que executam usuários do Skype for Business Server ou do Skype for Business Server, você deve concluir a Etapa 5: Preparar o Domínio Atual, conforme descrito no tópico Using Setup to Run Domain Preparation. Para concluir a etapa, você deve estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores corporativos da floresta à que o domínio pertence. Para preparar o domínio:'
ms.openlocfilehash: a71e50b0f3d55709c3c22709177b41e541f7075f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097333"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="f4a6e-105">Preparar Domínio Atual</span><span class="sxs-lookup"><span data-stu-id="f4a6e-105">Prepare Current Domain</span></span>

<span data-ttu-id="f4a6e-106">Para preparar um domínio para hospedar servidores executando usuários do Skype for Business Server ou do Skype for Business Server, você deve concluir a Etapa **5:** Preparar o Domínio Atual , conforme descrito no tópico [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span><span class="sxs-lookup"><span data-stu-id="f4a6e-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span></span> <span data-ttu-id="f4a6e-107">Para concluir a etapa, você deve estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores corporativos da floresta à que o domínio pertence.</span><span class="sxs-lookup"><span data-stu-id="f4a6e-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="f4a6e-108">Para preparar o domínio:</span><span class="sxs-lookup"><span data-stu-id="f4a6e-108">To prepare the domain:</span></span>

1. <span data-ttu-id="f4a6e-109">Na pasta ou mídia de instalação do Skype for Business Server, execute Setup.exe para iniciar o Assistente de Implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f4a6e-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="f4a6e-110">Clique em **Preparar Active Directory** e aguarde o estado de implantação ser determinado.</span><span class="sxs-lookup"><span data-stu-id="f4a6e-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="f4a6e-111">Na **Etapa 5: Preparar o Domínio Atual**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f4a6e-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="f4a6e-112">Na página **Executando Comandos**, procure por **Status da tarefa: concluída** e clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="f4a6e-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="f4a6e-113">Na coluna **Ação,** expanda **Preparação** de Domínio , procure um Resultado de Execução no final de cada tarefa para verificar se a preparação do domínio foi concluída com êxito, feche o log e clique em **\<Success\>** **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f4a6e-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="f4a6e-114">Se você precisar revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, poderá encontrá-los no computador onde o Assistente de Implantação foi executado no diretório Usuários do usuário dos Serviços de Domínio do Active Directory que executaram a etapa.</span><span class="sxs-lookup"><span data-stu-id="f4a6e-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="f4a6e-115">Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="f4a6e-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>