---
title: Preparar Servidor Standard Edition Único (Invocar)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: Na página comandos em execução, as tarefas de instalação do SQL Server Express e da configuração para atuar como o repositório de gerenciamento central podem ser visualizadas no painel de tarefas. Por padrão, uma instância de um banco de dados baseado em SQL Server chamado RTC é criada. As regras de firewall também são criadas para permitir acesso de entrada e saída para servidores e clientes para se comunicar com o banco de dados e a instância. Após a conclusão da tarefa, você pode selecionar o arquivo de registro na lista suspensa. O arquivo de log é chamado máquina local de inicialização. Depois de selecionar o arquivo de registro, clique em Exibir log. Examine o arquivo de log para ver se há erros e avisos. Quando estiver pronto para continuar, clique em concluir. Agora, você deve definir sua topologia com o construtor de topologias se ainda não tiver feito isso.
ms.openlocfilehash: 59118511ef8631e06214c9262e64c95125182963
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275706"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="86846-111">Preparar Servidor Standard Edition Único (Invocar)</span><span class="sxs-lookup"><span data-stu-id="86846-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="86846-112">Na página **comandos em execução** , as tarefas de instalação do SQL Server Express e da configuração para atuar como o repositório de gerenciamento central podem ser visualizadas no painel de tarefas.</span><span class="sxs-lookup"><span data-stu-id="86846-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="86846-113">Por padrão, uma instância de um banco de dados baseado em SQL Server chamado RTC é criada.</span><span class="sxs-lookup"><span data-stu-id="86846-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="86846-114">As regras de firewall também são criadas para permitir acesso de entrada e saída para servidores e clientes para se comunicar com o banco de dados e a instância.</span><span class="sxs-lookup"><span data-stu-id="86846-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="86846-115">Após a conclusão da tarefa, você pode selecionar o arquivo de registro na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="86846-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="86846-116">O arquivo de log é chamado **máquina local de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="86846-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="86846-117">Depois de selecionar o arquivo de registro, clique em **Exibir log**.</span><span class="sxs-lookup"><span data-stu-id="86846-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="86846-118">Examine o arquivo de log para ver se há erros e avisos.</span><span class="sxs-lookup"><span data-stu-id="86846-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="86846-119">Quando estiver pronto para continuar, clique em **concluir.**</span><span class="sxs-lookup"><span data-stu-id="86846-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="86846-120">Agora, você deve definir sua topologia com o construtor de topologias se ainda não tiver feito isso.</span><span class="sxs-lookup"><span data-stu-id="86846-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86846-121">A instalação do SQL Server Express pode levar algum tempo para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="86846-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="86846-122">Durante a instalação, não há progresso visível na tela ou no painel de tarefas.</span><span class="sxs-lookup"><span data-stu-id="86846-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="86846-123">Para monitorar a instalação, você deve usar o Gerenciador de tarefas do Windows e procurar os processos MSIExec e os arquivos de instalação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="86846-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="86846-124">Dessa forma, você pode ver o status da instalação e ter certeza de que a instalação está continuando.</span><span class="sxs-lookup"><span data-stu-id="86846-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="86846-125">Dependendo dos fatores além do escopo deste tópico da ajuda, pode levar até 15 minutos ou mais para instalar a instância do SQL Server para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="86846-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

