---
title: Expansor de Configurações de Repositório SQL
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Para editar as propriedades de um banco de dados do SQL Server, você deve alterar a instância de banco de dados do SQL Server. Você não pode usar a caixa de diálogo Editar propriedades para executar tarefas como mover o banco de dados do servidor de arquivamento de um computador para outro. Além disso, você não pode usar a caixa de diálogo Editar propriedades para alterar a instância do SQL Server que hospeda o repositório de gerenciamento Central.
ms.openlocfilehash: aab2797ccd0e96c01be33742faf7e00debbd76a8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880704"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="91db3-105">Expansor de Configurações de Repositório SQL</span><span class="sxs-lookup"><span data-stu-id="91db3-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="91db3-106">Para editar as propriedades de um banco de dados do SQL Server, você deve alterar a instância de banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91db3-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="91db3-107">Você não pode usar a caixa de diálogo **Editar propriedades** para executar tarefas como mover o banco de dados do servidor de arquivamento de um computador para outro.</span><span class="sxs-lookup"><span data-stu-id="91db3-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="91db3-108">Além disso, você não pode usar a caixa de diálogo **Editar propriedades** para alterar a instância do SQL Server que hospeda o repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="91db3-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="91db3-109">Editando as propriedades de um banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="91db3-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="91db3-110">Para alterar a instância do SQL Server que é usado por qualquer banco de dados que não seja o repositório de gerenciamento Central, complete o procedimento a seguir no construtor de topologia:</span><span class="sxs-lookup"><span data-stu-id="91db3-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="91db3-111">Para modificar uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="91db3-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="91db3-112">Selecione o banco de dados apropriado sob o nó **SQL armazena** e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="91db3-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="91db3-113">Na caixa de diálogo **Editar propriedades** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="91db3-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="91db3-114">Para usar a instância do SQL Server padrão, selecione a **Instância padrão** e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="91db3-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="91db3-115">Para usar uma instância nomeada do banco de dados, selecione a **Instância nomeada**, insira o nome da instância na caixa de texto e, em seguida, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="91db3-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="91db3-116">Você deve inserir apenas o nome da instância (por exemplo, ArchivingInstance) e não o caminho inteiro do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91db3-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="91db3-117">Quando você estiver trabalhando na caixa de diálogo **Editar propriedades** , construtor de topologia não verificará se a instância do banco de dados que você digitou é uma instância válida.</span><span class="sxs-lookup"><span data-stu-id="91db3-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="91db3-118">Por exemplo, se você inadvertidamente typeArchivingInstanec como o nome da instância e, em seguida, clique em **Okey**, construtor de topologia aceitará essa instância inválida.</span><span class="sxs-lookup"><span data-stu-id="91db3-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="91db3-119">Antes de publicar essa topologia, você deve corrigir este erro: se não for encontrada uma instância do SQL Server, construtor de topologia não criará essa instância para você.</span><span class="sxs-lookup"><span data-stu-id="91db3-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

