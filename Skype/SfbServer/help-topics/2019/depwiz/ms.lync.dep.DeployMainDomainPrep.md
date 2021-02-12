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
description: 'Para preparar um domínio para hospedar servidores executando os usuários do Skype for Business Server ou do Skype for Business Server, você deve concluir a Etapa 5: Preparar o Domínio Atual, conforme descrito no tópico Using Setup to Run Domain Preparation. Para concluir a etapa, você deve estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores de Empresa da floresta à que o domínio pertence. Para preparar o domínio:'
ms.openlocfilehash: d6e2efb774d7cad653c0a95e0e2863b97efe55ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824931"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="13586-105">Preparar Domínio Atual</span><span class="sxs-lookup"><span data-stu-id="13586-105">Prepare Current Domain</span></span>

<span data-ttu-id="13586-106">Para preparar um domínio para hospedar servidores que executam os usuários do Skype for Business Server ou do Skype for Business Server, você deve concluir a Etapa **5:** Preparar o Domínio Atual, conforme descrito no tópico Using [Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span><span class="sxs-lookup"><span data-stu-id="13586-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="13586-107">Para concluir a etapa, você deve estar conectado como membro do grupo Administradores de Domínio no domínio que você está preparando ou como membro do grupo Administradores de Empresa da floresta à que o domínio pertence.</span><span class="sxs-lookup"><span data-stu-id="13586-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="13586-108">Para preparar o domínio:</span><span class="sxs-lookup"><span data-stu-id="13586-108">To prepare the domain:</span></span>

1. <span data-ttu-id="13586-109">Na pasta ou mídia de instalação do Skype for Business Server, execute o Setup.exe para iniciar o Assistente de Implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="13586-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="13586-110">Clique em **Preparar Active Directory** e aguarde o estado de implantação ser determinado.</span><span class="sxs-lookup"><span data-stu-id="13586-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="13586-111">Na **Etapa 5: Preparar o Domínio Atual**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="13586-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="13586-112">Na página **Executando Comandos**, procure por **Status da tarefa: concluída** e clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="13586-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="13586-113">Na coluna **Ação,** expanda **o Domain Prep**, procure um Resultado de Execução no final de cada tarefa para verificar se a preparação do domínio foi concluída com êxito, feche o log e clique em **\<Success\>** **Concluir.**</span><span class="sxs-lookup"><span data-stu-id="13586-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="13586-114">Se precisar revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, você poderá encontrá-los no computador onde o Assistente de Implantação foi executado no diretório Usuários do usuário dos Serviços de Domínio Active Directory que executaram a etapa.</span><span class="sxs-lookup"><span data-stu-id="13586-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="13586-115">Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="13586-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


