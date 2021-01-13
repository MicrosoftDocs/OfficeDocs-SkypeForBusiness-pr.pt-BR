---
title: Gerenciar bancos de dados com um Grupo de Disponibilidade AlwaysOn no Skype for Business Server
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
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumo: saiba como adicionar mais bancos de dados do Skype for Business Server a um Grupo de Disponibilidade AlwaysOn existente e saiba mais sobre as etapas adicionais necessárias após corrigir ou atualizar um Servidor Back End que faz parte de um Grupo de Disponibilidade AlwaysOn no Skype for Business Server.'
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826361"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="71553-103">Gerenciar bancos de dados com um Grupo de Disponibilidade AlwaysOn no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="71553-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="71553-104">Use as etapas deste artigo para adicionar mais bancos de dados do Skype for Business Server a um Grupo de Disponibilidade AlwaysOn existente no Skype for Business Server e saiba mais sobre as etapas adicionais necessárias depois de corrigir ou atualizar um Servidor Back End que faz parte de um Grupo de Disponibilidade AlwaysOn no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="71553-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="71553-105">Adicionar bancos de dados a um Grupo de Disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="71553-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="71553-106">Abra o SQL Server Management Studio e navegue até o Grupo de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="71553-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="71553-107">Fail over it over to the primary replica.</span><span class="sxs-lookup"><span data-stu-id="71553-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="71553-108">No Construtor de Topologias, de definir o FQDN do SQL Server do Grupo de Disponibilidade AlwaysOn como o FQDN do nó principal desse grupo.</span><span class="sxs-lookup"><span data-stu-id="71553-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="71553-109">Abra o Construtor de Topologias, **selecione Baixar topologia da implantação existente** e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="71553-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="71553-110">Expanda o Skype for Business Server, expanda sua topologia e expanda os **Armazenamentos do SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="71553-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="71553-111">Clique com o botão direito do mouse no armazenamento SQL do novo Grupo de Disponibilidade AlwaysOn e clique em **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="71553-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="71553-112">Na parte inferior da página, na caixa **FQDN** do SQL Server, digite o FQDN do nó principal do Grupo de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="71553-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="71553-113">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="71553-113">Publish the topology.</span></span> <span data-ttu-id="71553-114">No menu **Ação,** clique **em Topologia** e **publique.**</span><span class="sxs-lookup"><span data-stu-id="71553-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="71553-115">Em seguida, na página de confirmação, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="71553-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="71553-116">Use o SQL Server Management Studio para adicionar o novo banco de dados ao Grupo de Disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="71553-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="71553-117">Corrigir ou atualizar um SQL Server em um grupo de disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="71553-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="71553-118">Depois de corrigir um Servidor Back End que faz parte de um Grupo de Disponibilidade AlwaysOn, você deve republicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="71553-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="71553-119">Instale a atualização no servidor ou servidores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="71553-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="71553-120">Execute o seguinte comando do PowerShell no Shell de Gerenciamento do Skype for Business (conectado com uma conta com permissão adequada para aplicar alterações aos bancos de dados SQL AlwaysOn) da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="71553-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="71553-121">Onde [sqlpool.contoso.com] é substituído pelo nome de domínio totalmente qualificado (FQDN) do seu grupo de disponibilidade AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="71553-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
