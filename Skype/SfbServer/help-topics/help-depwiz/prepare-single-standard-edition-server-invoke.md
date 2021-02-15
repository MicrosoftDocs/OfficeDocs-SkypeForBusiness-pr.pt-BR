---
title: Preparar Servidor Standard Edition Único (Invocar)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Na página Executando comandos, as tarefas de instalação do SQL Server Express e configuração para atuar como o armazenamento de Gerenciamento Central podem ser visualizadas no painel de tarefas. Por padrão, uma instância de um banco de dados baseado em SQL Server chamado RTC é criada. Regras de firewall também são criadas para permitir acesso de entrada e saída aos servidores e clientes para comunicação com o banco de dados e a instância. Após a conclusão da tarefa, será possível selecionar o arquivo de log na lista suspensa. O arquivo de log é chamado de  Máquina local de inicialização . Após selecionar o arquivo de log, clique em  Exibir Log . Verifique se há erros e avisos no arquivo de log. Quando estiver pronto para prosseguir, clique em  Concluir . Agora você deve definir sua topologia com o Construtor de Topologias, caso ainda não tenha feito isso.
ms.openlocfilehash: adf980ec2576eb4e23983fcd99befb1fc6bfb6ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829741"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="35aca-111">Preparar Servidor Standard Edition Único (Invocar)</span><span class="sxs-lookup"><span data-stu-id="35aca-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="35aca-112">Na página **Executando comandos,** as tarefas de instalação do SQL Server Express e configuração para atuar como o armazenamento de Gerenciamento Central podem ser visualizadas no painel de tarefas.</span><span class="sxs-lookup"><span data-stu-id="35aca-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="35aca-113">Por padrão, uma instância de um banco de dados baseado em SQL Server chamado RTC é criada.</span><span class="sxs-lookup"><span data-stu-id="35aca-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="35aca-114">Regras de firewall também são criadas para permitir acesso de entrada e saída aos servidores e clientes para comunicação com o banco de dados e a instância.</span><span class="sxs-lookup"><span data-stu-id="35aca-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="35aca-115">Após a conclusão da tarefa, será possível selecionar o arquivo de log na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="35aca-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="35aca-116">O arquivo de log é chamado de  **Máquina local de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="35aca-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="35aca-117">Após selecionar o arquivo de log, clique em  **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="35aca-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="35aca-118">Verifique se há erros e avisos no arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="35aca-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="35aca-119">Quando estiver pronto para prosseguir, clique em  **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="35aca-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="35aca-120">Agora você deve definir sua topologia com o Construtor de Topologias, caso ainda não tenha feito isso.</span><span class="sxs-lookup"><span data-stu-id="35aca-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="35aca-121">A instalação do SQL Server Express pode levar algum tempo para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="35aca-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="35aca-122">Não existe um progresso visível na tela ou painel de tarefas durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="35aca-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="35aca-123">Para monitorar a instalação, você deve usar o Gerenciador de Tarefas do Windows e procurar os processos MSIExec e os arquivos de Instalação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35aca-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="35aca-124">Você pode, dessa maneira, visualizar o status da instalação e certificar-se de que a instalação está prosseguindo.</span><span class="sxs-lookup"><span data-stu-id="35aca-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="35aca-125">Dependendo de fatores além do escopo deste tópico de ajuda, pode levar até 15 minutos ou mais para que a instalação da instância do SQL Server seja concluída.</span><span class="sxs-lookup"><span data-stu-id="35aca-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

