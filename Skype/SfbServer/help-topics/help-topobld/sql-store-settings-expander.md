---
title: Expansor de Configurações de Repositório SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Para editar as propriedades de um banco de dados do SQL Server, você deve alterar a instância do banco de dados do SQL Server. Não é possível usar a caixa de diálogo Editar Propriedades para executar tarefas como mover seu banco de dados do Servidor de Arquivamento de um computador para outro. Além disso, você não pode usar a caixa de diálogo Editar propriedades para alterar a instância do SQL Server que hospeda o repositório de gerenciamento central.
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219606"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="3ec49-105">Expansor de Configurações de Repositório SQL</span><span class="sxs-lookup"><span data-stu-id="3ec49-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="3ec49-106">Para editar as propriedades de um banco de dados do SQL Server, você deve alterar a instância do banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ec49-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="3ec49-107">Não é possível usar a caixa de diálogo **Editar Propriedades** para executar tarefas como mover seu banco de dados do Servidor de Arquivamento de um computador para outro.</span><span class="sxs-lookup"><span data-stu-id="3ec49-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="3ec49-108">Além disso, você não pode usar a caixa de diálogo **Editar propriedades** para alterar a instância do SQL Server que hospeda o repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="3ec49-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="3ec49-109">Editando as propriedades de um banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ec49-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="3ec49-110">Para alterar a instância do SQL Server usada por qualquer banco de dados diferente do repositório de gerenciamento central, conclua o procedimento a seguir no construtor de topologias:</span><span class="sxs-lookup"><span data-stu-id="3ec49-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="3ec49-111">Para modificar uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ec49-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="3ec49-112">Selecione o banco de dados apropriado no nó **Repositórios do SQL** e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3ec49-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="3ec49-113">Na caixa de diálogo **Editar Propriedades**, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="3ec49-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="3ec49-114">Para usar a instância padrão do SQL Server, selecione **instância padrão** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ec49-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="3ec49-115">Para usar uma instância de banco de dados nomeada, selecione **Instância nomeada**, insira o nome da instância na caixa de texto e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ec49-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="3ec49-116">Você deve inserir apenas o nome da instância (por exemplo, ArchivingInstance), e não todo o caminho do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ec49-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="3ec49-117">Quando você estiver trabalhando na caixa de diálogo **Editar propriedades** , o construtor de topologias não verificará se a instância do banco de dados que você inseriu é uma instância válida.</span><span class="sxs-lookup"><span data-stu-id="3ec49-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="3ec49-118">Por exemplo, se você inadvertidamente typeArchivingInstanec como o nome da instância e, em seguida, clique em **OK**, o construtor de topologias aceitará essa instância inválida.</span><span class="sxs-lookup"><span data-stu-id="3ec49-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="3ec49-119">Antes de publicar esta topologia, você deve corrigir esse erro: se não for possível encontrar uma instância do SQL Server, o construtor de topologias não criará essa instância para você.</span><span class="sxs-lookup"><span data-stu-id="3ec49-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

