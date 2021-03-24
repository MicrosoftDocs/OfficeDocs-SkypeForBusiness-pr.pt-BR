---
title: Preparar Floresta Atual
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Para preparar a floresta dos Serviços de Domínio do Active Directory, você deve estender com êxito o esquema, conforme descrito no tópico Running Schema Preparation, e certificar-se de que o esquema foi replicado.
ms.openlocfilehash: 94d41a993b2fe976ef7ede885d277c00417ff7dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103457"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="37821-103">Preparar Floresta Atual</span><span class="sxs-lookup"><span data-stu-id="37821-103">Prepare Current Forest</span></span>

<span data-ttu-id="37821-104">Para preparar a floresta dos Serviços de Domínio do Active Directory, você deve estender com êxito o esquema, conforme descrito no tópico [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema), e certificar-se de que o esquema foi replicado.</span><span class="sxs-lookup"><span data-stu-id="37821-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="37821-p101">Depois de atender a esses pré-requisitos, você pode começar a **Etapa 3: preparar a floresta atual**. Para preparar a floresta, faça logon em um computador na raiz da floresta como membro de Admins. do Domínio na raiz da floresta, ou como membro de Administradores de Empresa na floresta que você está preparando.</span><span class="sxs-lookup"><span data-stu-id="37821-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="37821-107">No Assistente de Implantação em **Etapa 3: preparar a floresta atual**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="37821-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="37821-108">Na página **Preparar Floresta**, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="37821-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="37821-109">A Preparação da Floresta permite que você escolha onde colocar os Grupos Universais do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="37821-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="37821-110">Escolha um local que atenda aos requisitos de sua organização.</span><span class="sxs-lookup"><span data-stu-id="37821-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="37821-p103">Na página **Executando Comandos**, procure por **Status da tarefa: concluída** e clique em **Exibir Log**. Certifique-se de que não haja erros. Revise os avisos a fim de determinar se são esperados e normais para sua infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="37821-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="37821-114">Na coluna **Ação** no log, expanda **Forest Prep**, procure um Resultado de Execução no final de cada tarefa para verificar se a preparação da floresta foi concluída com êxito, feche o log e clique em **\<Success\>** **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="37821-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="37821-115">Aguarde a conclusão da replicação dos Serviços de Domínio do **Active Directory** ou force a replicação a todos os controladores de domínio listados no snap-in Sites e Serviços do Active Directory para o controlador de domínio raiz da floresta, antes de executar a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="37821-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="37821-116">Force a replicação entre os controladores de domínio em todos os sites do Active Directory para que a replicação nos sites ocorra dentro de alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="37821-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="37821-117">Se você precisar revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, poderá encontrá-los no computador onde o Assistente de Implantação foi executado, no diretório Usuários do usuário dos Serviços de Domínio do Active Directory que executaram a etapa.</span><span class="sxs-lookup"><span data-stu-id="37821-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="37821-118">Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="37821-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>