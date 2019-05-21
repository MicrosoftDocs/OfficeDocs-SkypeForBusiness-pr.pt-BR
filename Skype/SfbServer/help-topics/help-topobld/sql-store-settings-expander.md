---
title: Expansor de Configurações de Repositório SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Para editar as propriedades de um banco de dados SQL Server, você deve alterar a instância do banco de dados do SQL Server. Não é possível usar a caixa de diálogo Editar propriedades para executar tarefas, como mover seu banco de dados do servidor de arquivamento de um computador para outro. Além disso, você não pode usar a caixa de diálogo Editar propriedades para alterar a instância do SQL Server que hospeda o repositório de gerenciamento central.
ms.openlocfilehash: 5119159c782e4d27b47d9759ff7b75323b9992fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291204"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="5c49a-105">Expansor de Configurações de Repositório SQL</span><span class="sxs-lookup"><span data-stu-id="5c49a-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="5c49a-106">Para editar as propriedades de um banco de dados SQL Server, você deve alterar a instância do banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5c49a-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="5c49a-107">Não é possível usar a caixa de diálogo **Editar propriedades** para executar tarefas, como mover seu banco de dados do servidor de arquivamento de um computador para outro.</span><span class="sxs-lookup"><span data-stu-id="5c49a-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="5c49a-108">Além disso, você não pode usar a caixa de diálogo **Editar propriedades** para alterar a instância do SQL Server que hospeda o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="5c49a-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="5c49a-109">Editando as propriedades de um banco de dados SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c49a-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="5c49a-110">Para alterar a instância do SQL Server que é usada por qualquer banco de dados diferente do repositório de gerenciamento central, conclua o seguinte procedimento no construtor de topologias:</span><span class="sxs-lookup"><span data-stu-id="5c49a-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="5c49a-111">Para modificar uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c49a-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="5c49a-112">Selecione o banco de dados apropriado no nó **repositórios SQL** e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5c49a-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="5c49a-113">Na caixa de diálogo **Editar propriedades** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5c49a-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="5c49a-114">Para usar a instância padrão do SQL Server, selecione **instância padrão** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c49a-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="5c49a-115">Para usar uma instância de banco de dados nomeado, selecione **instância nomeada**, insira o nome da instância na caixa de texto e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c49a-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="5c49a-116">Você deve inserir apenas o nome da instância (por exemplo, ArchivingInstance), e não todo o caminho do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5c49a-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="5c49a-117">Quando você estiver trabalhando na caixa de diálogo **Editar propriedades** , o construtor de topologias não verificará se a instância do banco de dados que você inseriu é uma instância válida.</span><span class="sxs-lookup"><span data-stu-id="5c49a-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="5c49a-118">Por exemplo, se você inadvertidamente typeArchivingInstanec como o nome da instância e, em seguida, clique em **OK**, o construtor de topologias aceitará essa instância inválida.</span><span class="sxs-lookup"><span data-stu-id="5c49a-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="5c49a-119">Antes de poder publicar esta topologia, você deve corrigir esse erro: se uma instância do SQL Server não puder ser encontrada, o construtor de topologias não criará essa instância para você.</span><span class="sxs-lookup"><span data-stu-id="5c49a-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

