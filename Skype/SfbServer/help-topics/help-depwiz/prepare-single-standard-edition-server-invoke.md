---
title: Preparar Servidor Standard Edition Único (Invocar)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Na página executando comandos, as tarefas de instalação do SQL Server Express e configurando para agir como o repositório de gerenciamento Central podem ser exibidas no painel de tarefas. Por padrão, uma instância de um banco de dados baseado em SQL Server denominada RTC é criada. Regras de firewall também são criadas para permitir o acesso de entrada e saído para servidores e clientes para se comunicar com o banco de dados e a instância. Quando a tarefa for concluída, você pode selecionar o arquivo de log da lista suspensa. O arquivo de log é chamado de Bootstrap máquina local. Depois de selecionar o arquivo de log, clique em Exibir Log. Revise o arquivo de log para quaisquer erros e avisos. Quando você estiver pronto para prosseguir, clique em Concluir. Agora você deve definir sua topologia com o construtor de topologias, se você ainda não tiver feito isso.
ms.openlocfilehash: fad1a7e4ab611ccf8ee152bf24c1eb1898d9cd51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910718"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="59c22-111">Preparar Servidor Standard Edition Único (Invocar)</span><span class="sxs-lookup"><span data-stu-id="59c22-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="59c22-112">Na página **executando comandos** , as tarefas de instalação do SQL Server Express e configurando para agir como o repositório de gerenciamento Central podem ser exibidas no painel de tarefas.</span><span class="sxs-lookup"><span data-stu-id="59c22-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="59c22-113">Por padrão, uma instância de um banco de dados baseado em SQL Server denominada RTC é criada.</span><span class="sxs-lookup"><span data-stu-id="59c22-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="59c22-114">Regras de firewall também são criadas para permitir o acesso de entrada e saído para servidores e clientes para se comunicar com o banco de dados e a instância.</span><span class="sxs-lookup"><span data-stu-id="59c22-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="59c22-115">Quando a tarefa for concluída, você pode selecionar o arquivo de log da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="59c22-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="59c22-116">O arquivo de log é chamado de **Bootstrap máquina local**.</span><span class="sxs-lookup"><span data-stu-id="59c22-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="59c22-117">Depois de selecionar o arquivo de log, clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="59c22-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="59c22-118">Revise o arquivo de log para quaisquer erros e avisos.</span><span class="sxs-lookup"><span data-stu-id="59c22-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="59c22-119">Quando você estiver pronto para prosseguir, clique em **término.**</span><span class="sxs-lookup"><span data-stu-id="59c22-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="59c22-120">Agora você deve definir sua topologia com o construtor de topologias, se você ainda não tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="59c22-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="59c22-121">A instalação do SQL Server Express pode levar algum tempo para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="59c22-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="59c22-122">Durante a instalação, não há nenhum progresso visível na tela ou o painel de tarefas.</span><span class="sxs-lookup"><span data-stu-id="59c22-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="59c22-123">Para monitorar a instalação, você deve usar o Gerenciador de tarefas do Windows e procure os processos de MSIExec e os arquivos de instalação para o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59c22-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="59c22-124">Dessa forma, você pode exibir o status da instalação e certifique-se de que a instalação está prosseguindo.</span><span class="sxs-lookup"><span data-stu-id="59c22-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="59c22-125">Dependendo de fatores além do escopo deste tópico de Ajuda, ele pode demorar até 15 minutos ou mais para a instalar o SQL Server de instância para concluir.</span><span class="sxs-lookup"><span data-stu-id="59c22-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

