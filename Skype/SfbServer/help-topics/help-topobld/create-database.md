---
title: Criar Banco de Dados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: O construtor de topologias oferece uma maneira de instalar bancos de dados em um repositório do SQL Server. Quando você instala os bancos de dados usando o construtor de topologias, o aplicativo lê as informações da topologia e, em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou no cluster do SQL Server. Este é o único tipo de instalação de banco de dados disponível com o uso do Construtor de Topologia. Se for necessário instalar um banco de dados específico em um computador específico ou se for necessário instalar um banco de dados colocado, você deverá usar a interface de linha de comando do Windows PowerShell e o cmdlet Install-CsDatabase.
ms.openlocfilehash: ea7daab44c6075e40e3f8a1b900fe43b84048ed5
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219502"
---
# <a name="create-database"></a><span data-ttu-id="91893-106">Criar banco de dados</span><span class="sxs-lookup"><span data-stu-id="91893-106">Create Database</span></span>
 
<span data-ttu-id="91893-107">O construtor de topologias oferece uma maneira de instalar bancos de dados em um repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91893-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="91893-108">Quando você instala os bancos de dados usando o construtor de topologias, o aplicativo lê as informações da topologia e, em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou no cluster do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91893-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="91893-109">Este é o único tipo de instalação de banco de dados disponível com o uso do Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="91893-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="91893-110">Se for necessário instalar um banco de dados específico em um computador específico ou se for necessário instalar um banco de dados colocado, você deverá usar a interface de linha de comando do Windows PowerShell e o cmdlet [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="91893-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="91893-111">Criando um Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="91893-111">Creating a Database</span></span>

1. <span data-ttu-id="91893-112">Clique no nó do Skype for Business Server 2015 e, em seguida, clique em **instalar banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="91893-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="91893-113">Na caixa de diálogo **instalar bancos** de dados, na página **criar banco de dados** , selecione o FQDN (nome de domínio totalmente qualificado) do repositório do SQL Server onde os novos bancos de dados serão criados.</span><span class="sxs-lookup"><span data-stu-id="91893-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="91893-p103">Clique em **Avançado**. Na caixa de diálogo **Selecionar Local do Arquivo de Banco de Dados**, selecione uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="91893-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="91893-p104">**Determinar o local do arquivo de banco de dados automaticamente**. Caso selecione esta opção, o Construtor de Topologia utiliza um algoritmo interno para escolher o local de armazenamento para os logs de banco de dados e arquivos de dados.</span><span class="sxs-lookup"><span data-stu-id="91893-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="91893-118">**Usar padrões de instância do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="91893-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="91893-119">Se você selecionar essa opção, o algoritmo interno não será usado para escolher os locais de armazenamento dos logs e dos arquivos de dados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="91893-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="91893-120">Em vez disso, o registro e os arquivos de dados serão armazenados nos locais especificados pelo caminho padrão do SQL Server (esses caminhos devem ser configurados antecipadamente por um administrador do SQL Server).</span><span class="sxs-lookup"><span data-stu-id="91893-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="91893-121">Os arquivos de dados devem ser armazenados no local padrão para os arquivos de dados do SQL, enquanto os arquivos de registro são armazenados no local padrão para os arquivos de registro do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91893-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="91893-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="91893-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="91893-123">Na página **Criar Banco de Dados**, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="91893-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="91893-124">Na página**Criação de Banco de Dados Concluída**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="91893-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

