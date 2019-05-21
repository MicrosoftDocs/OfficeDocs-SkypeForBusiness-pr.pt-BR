---
title: Gerenciar bancos de dados com um grupo de disponibilidade AlwaysOn no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumo: saiba como adicionar mais bancos de dados do Skype for Business Server a um grupo de disponibilidade AlwaysOn existente e saber mais sobre as etapas adicionais necessárias após o patch ou a atualização de um servidor back-end que faz parte de um grupo de disponibilidade AlwaysOn no Skype para Business Server.'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275182"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="30984-103">Gerenciar bancos de dados com um grupo de disponibilidade AlwaysOn no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="30984-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="30984-104">Use as etapas neste artigo para adicionar mais bancos de dados do Skype for Business Server a um grupo de disponibilidade AlwaysOn existente no Skype for Business Server e saber mais sobre as etapas adicionais necessárias após o patch ou a atualização de um servidor back-end que faz parte de um AlwaysOn Grupo de disponibilidade no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="30984-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="30984-105">Adicionar bancos de dados a um grupo de disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="30984-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="30984-106">Abra o SQL Server Management Studio e navegue até o grupo disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="30984-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="30984-107">Fazer failover para a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="30984-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="30984-108">Em Construtor de topologia, defina o FQDN do SQL Server do grupo de disponibilidade AlwaysOn para o FQDN do nó primário do grupo.</span><span class="sxs-lookup"><span data-stu-id="30984-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="30984-109">Abra o construtor de topologias, selecione **baixar topologia de implantação existente**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="30984-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="30984-110">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="30984-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="30984-111">Clique com o botão direito do mouse no repositório SQL do novo grupo de disponibilidade AlwaysOn e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="30984-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="30984-112">Na parte inferior da página, na caixa **FQDN do SQL Server** , digite o FQDN do nó primário do grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="30984-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="30984-113">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="30984-113">Publish the topology.</span></span> <span data-ttu-id="30984-114">No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="30984-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="30984-115">Na página de confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="30984-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="30984-116">Use o SQL Server Management Studio para adicionar o novo banco de dados ao grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="30984-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="30984-117">Aplicar patch ou atualizar o SQL Server em um grupo de disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="30984-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="30984-118">Depois de corrigir um servidor back-end que faz parte de um grupo de disponibilidade AlwaysOn, você deve republicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="30984-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="30984-119">Instale a atualização em um ou vários servidores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="30984-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="30984-120">Execute o seguinte comando do PowerShell no Skype for Business Management Shell (acessado com uma conta que tenha a devida permissão para aplicar alterações nos bancos de dados do SQL AlwaysOn) conforme segue:</span><span class="sxs-lookup"><span data-stu-id="30984-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="30984-121">Quando o [sqlpool.contoso.com] é substituído pelo FQDN (Nome do domínio totalmente qualificado) do seu grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="30984-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
