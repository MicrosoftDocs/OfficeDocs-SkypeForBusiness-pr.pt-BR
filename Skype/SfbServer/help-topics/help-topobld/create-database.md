---
title: Criar Banco de Dados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Construtor de topologia fornece uma maneira para instalar bancos de dados em um repositório do SQL Server. Quando você instala os bancos de dados usando o construtor de topologia, o aplicativo lê as informações de topologia e em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou cluster do SQL Server. Este é o único tipo de instalação de banco de dados disponível se for usar o Construtor de Topologias. Se você precisa instalar um banco de dados específico em um computador específico, ou se você deve instalar um banco de dados colocado, você deve usar o cmdlet Install-CsDatabase e interface de linha de comando do Windows PowerShell.
ms.openlocfilehash: 9b9d3e3678fe0015281a75aa04b2a2a88daf5d2f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226968"
---
# <a name="create-database"></a><span data-ttu-id="b0e0e-106">Criar Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="b0e0e-106">Create Database</span></span>
 
<span data-ttu-id="b0e0e-107">Construtor de topologia fornece uma maneira para instalar bancos de dados em um repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="b0e0e-108">Quando você instala os bancos de dados usando o construtor de topologia, o aplicativo lê as informações de topologia e em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou cluster do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="b0e0e-109">Este é o único tipo de instalação de banco de dados disponível se for usar o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="b0e0e-110">Se você precisa instalar um banco de dados específico em um computador específico, ou se você deve instalar um banco de dados colocado, você deve usar o cmdlet [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) e interface de linha de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="b0e0e-111">Criando um banco de dados</span><span class="sxs-lookup"><span data-stu-id="b0e0e-111">Creating a Database</span></span>

1. <span data-ttu-id="b0e0e-112">Clique no Skype para Business Server 2015 nó e clique em **Instalar banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="b0e0e-113">Na caixa de diálogo **Instalar banco de dados** , na página **Criar banco de dados** , selecione o nome de domínio totalmente qualificado (FQDN) do repositório do SQL Server onde os novos bancos de dados devem ser criados.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="b0e0e-p103">Clique em **Avançado**. Na caixa de diálogo **Selecionar Local do Arquivo de Banco de Dados**, selecione uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="b0e0e-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="b0e0e-p104">**Determinar o local do arquivo de banco de dados automaticamente**. Caso selecione essa opção, o Construtor de Topologias utiliza um algoritmo interno para escolher o local de armazenamento para os logs de banco de dados e arquivos de dados.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="b0e0e-118">**Use o SQL Server instância padrões**.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="b0e0e-119">Se você selecionar essa opção, o algoritmo incorporado não é usado para escolher os locais de armazenamento para o banco de dados de logs e arquivos de dados.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="b0e0e-120">Em vez disso, os arquivos de log e de dados são armazenados nos locais especificados pelo caminho padrões do SQL Server (esses caminhos devem estar configurados no advanced por um administrador do SQL Server).</span><span class="sxs-lookup"><span data-stu-id="b0e0e-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="b0e0e-121">Arquivos de dados serão armazenados no local do arquivo de dados padrão do SQL Server enquanto os arquivos de log serão armazenados no local do arquivo de log padrão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="b0e0e-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="b0e0e-123">Na página **Criar banco de dados**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="b0e0e-124">Na página  **Criação de banco de dados concluída**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b0e0e-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

