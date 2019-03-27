---
title: Gerenciar bancos de dados com um grupo de disponibilidade do AlwaysOn no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumo: Saiba como adicionar mais Skype para bancos de dados do Business Server a um grupo de disponibilidade do AlwaysOn existente e saiba mais sobre as etapas adicionais necessárias após você patch ou atualização de um servidor Back-End que faz parte de um grupo de disponibilidade do AlwaysOn em Skype para Servidor de negócios.'
ms.openlocfilehash: 8d25e7d3aa1e840be7eb246e6aaa3065b65b7ff7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875408"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="38d30-103">Gerenciar bancos de dados com um grupo de disponibilidade do AlwaysOn no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="38d30-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="38d30-104">Use as etapas neste artigo para adicionar mais Skype para bancos de dados do Business Server a um grupo de disponibilidade do AlwaysOn existente no Skype para Business Server e saiba mais sobre as etapas adicionais necessárias depois de patch ou atualização de um servidor Back-End que faz parte de um AlwaysOn Grupo de disponibilidade no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="38d30-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="38d30-105">Adicionar bancos de dados para um grupo de disponibilidade do AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="38d30-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="38d30-106">Abra o SQL Server Management Studio e navegue até o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="38d30-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="38d30-107">Failover para a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="38d30-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="38d30-108">No construtor de topologia, defina o FQDN do grupo de disponibilidade do AlwaysOn do SQL Server para o FQDN do nó principal desse grupo.</span><span class="sxs-lookup"><span data-stu-id="38d30-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="38d30-109">Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="38d30-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="38d30-110">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="38d30-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="38d30-111">Clique com o botão o repositório SQL do novo grupo de disponibilidade do AlwaysOn e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="38d30-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="38d30-112">Na parte inferior da página, na caixa **FQDN do SQL Server** , digite o FQDN do nó principal do grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="38d30-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="38d30-113">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="38d30-113">Publish the topology.</span></span> <span data-ttu-id="38d30-114">No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="38d30-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="38d30-115">Na página de confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="38d30-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="38d30-116">Use o SQL Server Management Studio para adicionar o novo banco de dados para o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="38d30-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="38d30-117">Aplicar patch ou atualizar o SQL Server em um grupo de disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="38d30-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="38d30-118">Depois de aplicar o patch de um servidor Back-End que faz parte de um grupo de disponibilidade do AlwaysOn, você deve republicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="38d30-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="38d30-119">Instale a atualização em um ou vários servidores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="38d30-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="38d30-120">Execute o seguinte comando do PowerShell no Skype for Business Management Shell (acessado com uma conta que tenha a devida permissão para aplicar alterações nos bancos de dados do SQL AlwaysOn) conforme segue:</span><span class="sxs-lookup"><span data-stu-id="38d30-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="38d30-121">Quando o [sqlpool.contoso.com] é substituído pelo FQDN (Nome do domínio totalmente qualificado) do seu grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="38d30-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
