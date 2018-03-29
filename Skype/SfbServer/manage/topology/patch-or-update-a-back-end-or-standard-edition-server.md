---
title: Corrigir ou atualizar um Servidor Back End ou um servidor Standard Edition no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumo: Saiba como instalar uma atualização ou patch em um servidor Back-End no Skype para Business Server.'
ms.openlocfilehash: 14acff1aea501bf47dff95053259187570d2f990
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a><span data-ttu-id="506c9-103">Corrigir ou atualizar um Servidor Back End ou um servidor Standard Edition no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="506c9-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="506c9-104">**Resumo:** Saiba como instalar uma atualização ou patch em um servidor Back-End no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="506c9-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="506c9-105">Este tópico explica como instalar uma atualização em um servidor do Enterprise Edition Back End ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="506c9-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="506c9-106">Se for um servidor Back-End para baixo pelo menos 30 minutos enquanto você estiver atualizando-la, os usuários, em seguida, podem entrar no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="506c9-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="506c9-107">Quando a atualização é concluída e os servidores Back-End conectou-se novamente com servidores Front-End do pool, os usuários são retornados para a funcionalidade total.</span><span class="sxs-lookup"><span data-stu-id="506c9-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="506c9-108">Se a atualização levar menos de 30 minutos, os usuários não serão afetados.</span><span class="sxs-lookup"><span data-stu-id="506c9-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="506c9-109">Para atualizar um servidor Back End ou um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="506c9-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="506c9-110">Faça logon no servidor que você estiver atualizando como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="506c9-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="506c9-111">Faça o download do pacote de atualizações e extraia os arquivos para um disco rígido local.</span><span class="sxs-lookup"><span data-stu-id="506c9-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="506c9-112">Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para negócios 2015**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de Business**..</span><span class="sxs-lookup"><span data-stu-id="506c9-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="506c9-113">Pare Skype para serviços de Business Server.</span><span class="sxs-lookup"><span data-stu-id="506c9-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="506c9-114">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="506c9-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="506c9-p103">Pare o serviço World Wide Web. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="506c9-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="506c9-117">Feche todas as Skype para windows Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="506c9-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="506c9-118">Atualize a atualização.</span><span class="sxs-lookup"><span data-stu-id="506c9-118">Install the update.</span></span>
    
8. <span data-ttu-id="506c9-119">Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para negócios 2015**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de Business**..</span><span class="sxs-lookup"><span data-stu-id="506c9-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
9. <span data-ttu-id="506c9-120">Pare Skype para serviços de Business Server novamente para capturar assemblies -d do Cache de Assembly Global (GAC).</span><span class="sxs-lookup"><span data-stu-id="506c9-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="506c9-121">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="506c9-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="506c9-p105">Reinicie o serviço World Wide Web. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="506c9-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="506c9-124">Aplique as alterações feitas nos bancos de dados SQL Server por meio de uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="506c9-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="506c9-125">Se este for um Enterprise Edition servidor Back-End e não existem bancos de dados colocados neste servidor, como o arquivamento ou bancos de dados de monitoramento, em seguida, digite o seguinte na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="506c9-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="506c9-126">Se este for um Enterprise Edition servidor Back-End e existem bancos de dados colocados neste servidor, digite o seguinte na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="506c9-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="506c9-127">Caso se trate de um servidor Standard Edition, digite o seguinte na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="506c9-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```


