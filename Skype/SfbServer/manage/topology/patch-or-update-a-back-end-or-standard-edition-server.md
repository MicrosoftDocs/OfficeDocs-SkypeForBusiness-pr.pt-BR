---
title: Corrigir ou atualizar um servidor back-end ou servidor Standard Edition no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumo: Saiba como instalar uma atualização ou um patch em um Servidor Back End no Skype for Business Server.'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826301"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="109a6-103">Corrigir ou atualizar um servidor back-end ou servidor Standard Edition no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="109a6-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="109a6-104">**Resumo:** Saiba como instalar uma atualização ou um patch em um servidor back-end no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="109a6-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="109a6-105">Este tópico explica como instalar uma atualização em um servidor Back End Enterprise Edition ou em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="109a6-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="109a6-p101">Se o servidor Back End estiver inoperante por ao menos 30 minutos enquanto você o estiver atualizando, os usuários podem entrar em modo de resiliência. Quando a atualização for concluída e os servidores Back End tiver novamente se conectado aos servidores Front End no pool, os usuários são retornados à funcionalidade total. Se a atualização levar menos de 30 minutos, os usuários não serão afetados.</span><span class="sxs-lookup"><span data-stu-id="109a6-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="109a6-109">Para atualizar um servidor back-end ou um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="109a6-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="109a6-110">Faça logon no servidor que você estiver atualizando como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="109a6-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="109a6-111">Faça o download do pacote de atualizações e extraia os arquivos para um disco rígido local.</span><span class="sxs-lookup"><span data-stu-id="109a6-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="109a6-112">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business** e, em seguida, clique em Shell de Gerenciamento do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="109a6-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="109a6-113">Pare os serviços do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="109a6-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="109a6-114">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="109a6-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="109a6-115">Pare o serviço World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="109a6-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="109a6-116">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="109a6-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="109a6-117">Feche todas as janelas do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="109a6-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="109a6-118">Instale a atualização.</span><span class="sxs-lookup"><span data-stu-id="109a6-118">Install the update.</span></span>
    
8. <span data-ttu-id="109a6-119">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business** e no Shell de Gerenciamento do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="109a6-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="109a6-120">Pare os serviços do Skype for Business Server novamente para capturar assemblies GAC (Cache de Assembly Global) -d.</span><span class="sxs-lookup"><span data-stu-id="109a6-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="109a6-121">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="109a6-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="109a6-122">Reinicie o serviço World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="109a6-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="109a6-123">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="109a6-123">At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="109a6-124">Aplique as alterações feitas nos bancos de dados do SQL Server fazendo um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="109a6-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="109a6-125">Se for um Servidor de Back End Enterprise Edition e não houver bancos de dados alocados neste servidor, como os bancos de dados de Arquivamento ou monitoramento, digite o seguinte na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="109a6-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="109a6-126">Se for um Servidor de Back End Enterprise Edition e houver bancos de dados alocados neste servidor, digite o seguinte na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="109a6-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="109a6-127">Se for um servidor Standard Edition, digite o seguinte na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="109a6-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
