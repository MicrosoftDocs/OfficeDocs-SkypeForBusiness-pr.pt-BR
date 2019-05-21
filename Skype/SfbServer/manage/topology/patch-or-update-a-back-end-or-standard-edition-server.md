---
title: Patch ou atualização de um servidor back-end do servidor ou da edição Standard no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumo: saiba como instalar uma atualização ou um patch em um servidor back-end no Skype for Business Server.'
ms.openlocfilehash: b8a0280577147e37c52ab11aa3061541bae27610
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275119"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="6784a-103">Patch ou atualização de um servidor back-end do servidor ou da edição Standard no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6784a-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="6784a-104">**Resumo:** Saiba como instalar uma atualização ou patch em um servidor back-end no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6784a-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="6784a-105">Este tópico explica como instalar uma atualização em um servidor back-end da edição Enterprise ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6784a-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="6784a-106">Se um servidor back-end estiver inoperante durante pelo menos 30 minutos enquanto você estiver atualizando, os usuários poderão entrar no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="6784a-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="6784a-107">Quando a atualização estiver concluída e os servidores back-end novamente conectados com os servidores de front-end do pool, os usuários retornarão à funcionalidade completa.</span><span class="sxs-lookup"><span data-stu-id="6784a-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="6784a-108">Se a atualização levar menos de 30 minutos, os usuários não serão afetados.</span><span class="sxs-lookup"><span data-stu-id="6784a-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="6784a-109">Para atualizar um servidor Back End ou um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6784a-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="6784a-110">Faça logon no servidor que você estiver atualizando como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6784a-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="6784a-111">Faça o download do pacote de atualizações e extraia os arquivos para um disco rígido local.</span><span class="sxs-lookup"><span data-stu-id="6784a-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="6784a-112">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**...</span><span class="sxs-lookup"><span data-stu-id="6784a-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="6784a-113">Interrompa os serviços do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6784a-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="6784a-114">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="6784a-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="6784a-115">Pare o serviço World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="6784a-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="6784a-116">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="6784a-116">At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="6784a-117">Feche todas as janelas do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6784a-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="6784a-118">Atualize a atualização.</span><span class="sxs-lookup"><span data-stu-id="6784a-118">Install the update.</span></span>
    
8. <span data-ttu-id="6784a-119">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="6784a-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="6784a-120">Pare os serviços do Skype for Business Server novamente para capturar assemblies global assembly cache (GAC)-d.</span><span class="sxs-lookup"><span data-stu-id="6784a-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="6784a-121">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="6784a-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="6784a-p105">Reinicie o serviço World Wide Web. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="6784a-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="6784a-124">Aplique as alterações feitas nos bancos de dados SQL Server por meio de uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="6784a-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="6784a-125">Se este for um servidor back-end da edição Enterprise e não houver bancos de dados posicionados neste servidor, como arquivar ou monitorar bancos de dados, digite o seguinte na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6784a-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="6784a-126">Se este for um servidor back-end do Enterprise Edition e houver bancos de dados posicionados neste servidor, digite o seguinte em uma linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6784a-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="6784a-127">Se esse for um servidor Standard Edition, digite o seguinte em uma linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6784a-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
