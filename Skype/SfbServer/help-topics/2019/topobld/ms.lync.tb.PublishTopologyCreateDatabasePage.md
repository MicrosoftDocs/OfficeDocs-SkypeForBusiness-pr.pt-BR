---
title: Criar Banco de Dados
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: O Construtor de Topologias fornece uma maneira de instalar bancos de dados em um SQL Server store. Quando você instala bancos de dados usando o Construtor de Topologias, o aplicativo lê informações da topologia e instala os bancos de dados necessários no computador SQL Server ou no cluster SQL Server. Este é o único tipo de instalação de banco de dados disponível com o uso do Construtor de Topologia. Se você precisar instalar um banco de dados específico em um computador específico ou se precisar instalar um banco de dados alocado, deverá usar uma interface de linha de comando Windows PowerShell e o cmdlet Install-CsDatabase.
ms.openlocfilehash: 92e0c8c0221fbd697ce59587ff4543d6cf7e119d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101827"
---
# <a name="create-database"></a><span data-ttu-id="d2c03-106">Criar banco de dados</span><span class="sxs-lookup"><span data-stu-id="d2c03-106">Create Database</span></span>
 
<span data-ttu-id="d2c03-107">O Construtor de Topologias fornece uma maneira de instalar bancos de dados em um SQL Server store.</span><span class="sxs-lookup"><span data-stu-id="d2c03-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="d2c03-108">Quando você instala bancos de dados usando o Construtor de Topologias, o aplicativo lê informações da topologia e instala os bancos de dados necessários no computador SQL Server ou no cluster SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d2c03-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="d2c03-109">Este é o único tipo de instalação de banco de dados disponível com o uso do Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="d2c03-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="d2c03-110">Se você precisar instalar um banco de dados específico em um computador específico ou se precisar instalar um banco de dados alocado, deverá usar uma interface de linha de comando Windows PowerShell e o cmdlet [Install-CsDatabase.](/powershell/module/skype/install-csdatabase?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d2c03-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="d2c03-111">Criando um Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="d2c03-111">Creating a Database</span></span>

1. <span data-ttu-id="d2c03-112">Clique no nó Skype for Business Server e clique em **Instalar Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="d2c03-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="d2c03-113">Na  caixa de diálogo Instalar  Bancos de Dados, na página Criar Banco de Dados, selecione o nome de domínio totalmente qualificado (FQDN) do armazenamento SQL Server onde os novos bancos de dados devem ser criados.</span><span class="sxs-lookup"><span data-stu-id="d2c03-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="d2c03-p103">Clique em **Avançado**. Na caixa de diálogo **Selecionar Local do Arquivo de Banco de Dados**, selecione uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="d2c03-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="d2c03-p104">**Determinar o local do arquivo de banco de dados automaticamente**. Caso selecione esta opção, o Construtor de Topologia utiliza um algoritmo interno para escolher o local de armazenamento para os logs de banco de dados e arquivos de dados.</span><span class="sxs-lookup"><span data-stu-id="d2c03-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="d2c03-118">**Use SQL Server de instância.**</span><span class="sxs-lookup"><span data-stu-id="d2c03-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="d2c03-119">Se você selecionar essa opção, o algoritmo interno não será usado para escolher os locais de armazenamento para os logs de banco de dados e os arquivos de dados.</span><span class="sxs-lookup"><span data-stu-id="d2c03-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="d2c03-120">Em vez disso, o registro e os arquivos de dados serão armazenados nos locais especificados pelo caminho padrão do SQL Server (esses caminhos devem ser configurados antecipadamente por um administrador do SQL Server).</span><span class="sxs-lookup"><span data-stu-id="d2c03-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="d2c03-121">Os arquivos de dados devem ser armazenados no local padrão para os arquivos de dados do SQL, enquanto os arquivos de registro são armazenados no local padrão para os arquivos de registro do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d2c03-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="d2c03-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2c03-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="d2c03-123">Na página **Criar Banco de Dados**, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="d2c03-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="d2c03-124">Na página **Criação de Banco de Dados Concluída**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="d2c03-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
