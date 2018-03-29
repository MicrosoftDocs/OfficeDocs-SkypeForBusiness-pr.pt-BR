---
title: Adicionar bancos de dados a um grupo de disponibilidade do AlwaysOn no Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumo: Saiba como adicionar mais Skype para bancos de dados do Business Server a um grupo de disponibilidade do AlwaysOn existente no Skype para Business Server 2015.'
ms.openlocfilehash: 31678d6cc374ecdbe40d2fdf3039905176c0178d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server-2015"></a><span data-ttu-id="2a7ec-103">Adicionar bancos de dados a um grupo de disponibilidade do AlwaysOn no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2a7ec-103">Add databases to an AlwaysOn Availability Group in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2a7ec-104">**Resumo:** Saiba como adicionar mais Skype para bancos de dados do Business Server a um grupo de disponibilidade do AlwaysOn existente no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2a7ec-104">**Summary:** Learn how to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server 2015.</span></span>
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="2a7ec-105">Adicionar bancos de dados para um grupo de disponibilidade do AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="2a7ec-105">Adding databases to an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="2a7ec-106">Abra o SQL Server Management Studio e navegue até o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2a7ec-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2a7ec-107">Failover para a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="2a7ec-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="2a7ec-108">No construtor de topologia, defina o FQDN do grupo de disponibilidade do AlwaysOn do SQL Server para o FQDN do nó principal desse grupo.</span><span class="sxs-lookup"><span data-stu-id="2a7ec-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
  - <span data-ttu-id="2a7ec-109">Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="2a7ec-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
  - <span data-ttu-id="2a7ec-110">Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2a7ec-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="2a7ec-111">Clique com o botão o repositório SQL do novo grupo de disponibilidade do AlwaysOn e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2a7ec-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
  - <span data-ttu-id="2a7ec-112">Na parte inferior da página, na caixa **FQDN do SQL Server** , digite o FQDN do nó principal do grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2a7ec-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="2a7ec-p103">Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, em **Publicar**. Na página de confirmação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2a7ec-p103">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="2a7ec-116">Use o SQL Server Management Studio para adicionar o novo banco de dados para o grupo de disponibilidade do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="2a7ec-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    

