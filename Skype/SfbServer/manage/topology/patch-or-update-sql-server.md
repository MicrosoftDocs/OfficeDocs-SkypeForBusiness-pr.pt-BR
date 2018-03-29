---
title: Aplicar patch ou atualizar o SQL Server em um grupo de disponibilidade AlwaysOn no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Resumo: Saiba mais sobre as etapas adicionais necessárias após você patch ou atualização de um servidor Back-End que faz parte de um grupo de disponibilidade do AlwaysOn em Skype para Business Server.'
ms.openlocfilehash: 8f5c9131e59ccedd7f590f696fe53aa6c18c7d22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server-2015"></a><span data-ttu-id="43441-103">Aplicar patch ou atualizar o SQL Server em um grupo de disponibilidade AlwaysOn no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="43441-103">Patch or update a SQL Server in an AlwaysOn Availability Group in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="43441-104">**Resumo:** Saiba mais sobre as etapas adicionais necessárias depois de patch ou atualização de um servidor Back-End que faz parte de um grupo de disponibilidade do AlwaysOn em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="43441-104">**Summary:** Find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
<span data-ttu-id="43441-105">Depois de aplicar o patch de um servidor Back-End que faz parte de um grupo de disponibilidade do AlwaysOn, você deve republicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="43441-105">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a><span data-ttu-id="43441-106">Aplicar patch ou atualizar um SQL Server que faz parte de um grupo de disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="43441-106">Patching or updating a SQL Server that is part of an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="43441-107">Instale a atualização em um ou vários servidores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="43441-107">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="43441-108">Execute o seguinte comando do PowerShell no Skype for Business Management Shell (acessado com uma conta que tenha a devida permissão para aplicar alterações nos bancos de dados do SQL AlwaysOn) conforme segue:</span><span class="sxs-lookup"><span data-stu-id="43441-108">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="43441-109">Quando o [sqlpool.contoso.com] é substituído pelo FQDN (Nome do domínio totalmente qualificado) do seu grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="43441-109">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
    

