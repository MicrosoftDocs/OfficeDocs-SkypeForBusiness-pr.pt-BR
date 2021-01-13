---
title: Expansor de Configurações de Repositório SQL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar as propriedades de um banco de dados do SQL Server, você deve alterar a instância do banco de dados do SQL Server. Não é possível usar a caixa de diálogo Editar Propriedades para executar tarefas como mover seu banco de dados do Servidor de Arquivamento de um computador para outro. Além disso, você não pode usar a caixa de diálogo Editar Propriedades para alterar a instância do SQL Server que hospeda o armazenamento de Gerenciamento Central.
ms.openlocfilehash: 96eeb4302bd904fe3622e7135d34d374f56766e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805511"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="3eb4c-105">Expansor de Configurações de Repositório SQL</span><span class="sxs-lookup"><span data-stu-id="3eb4c-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="3eb4c-106">Para editar as propriedades de um banco de dados do SQL Server, você deve alterar a instância do banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3eb4c-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="3eb4c-107">Não é possível usar a caixa de diálogo **Editar Propriedades** para executar tarefas como mover seu banco de dados do Servidor de Arquivamento de um computador para outro.</span><span class="sxs-lookup"><span data-stu-id="3eb4c-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="3eb4c-108">Além disso, você não pode usar a **caixa** de diálogo Editar Propriedades para alterar a instância do SQL Server que hospeda o armazenamento de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="3eb4c-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="3eb4c-109">Editando as propriedades de um banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3eb4c-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="3eb4c-110">Para alterar a instância do SQL Server usada por qualquer banco de dados diferente do armazenamento de Gerenciamento Central, conclua o seguinte procedimento no Construtor de Topologias:</span><span class="sxs-lookup"><span data-stu-id="3eb4c-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="3eb4c-111">Para modificar uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3eb4c-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="3eb4c-112">Selecione o banco de dados apropriado no nó **Repositórios do SQL** e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3eb4c-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="3eb4c-113">Na caixa de diálogo **Editar Propriedades**, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="3eb4c-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="3eb4c-114">Para usar a instância padrão do SQL Server, selecione **Instância Padrão** e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="3eb4c-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="3eb4c-115">Para usar uma instância de banco de dados nomeada, selecione **Instância nomeada**, insira o nome da instância na caixa de texto e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3eb4c-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="3eb4c-116">Você deve inserir apenas o nome da instância (por exemplo, ArchivingInstance) e não todo o caminho do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3eb4c-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="3eb4c-117">Quando você estiver  trabalhando na caixa de diálogo Editar Propriedades, o Construtor de Topologias não verificará se a instância do banco de dados inserida é uma instância válida.</span><span class="sxs-lookup"><span data-stu-id="3eb4c-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="3eb4c-118">Por exemplo, se você inadvertidamente typeArchivingInstanec como o nome da instância e clicar em **OK**, o Construtor de Topologia aceitará essa instância inválida.</span><span class="sxs-lookup"><span data-stu-id="3eb4c-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="3eb4c-119">Antes de publicar essa topologia, você deve corrigir esse erro: se uma instância do SQL Server não for encontrada, o Construtor de Topologias não criará essa instância para você.</span><span class="sxs-lookup"><span data-stu-id="3eb4c-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

