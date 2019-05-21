---
title: Criar Banco de Dados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: O construtor de topologias fornece uma maneira de instalar bancos de dados em uma loja do SQL Server. Ao instalar bancos de dados usando o construtor de topologias, o aplicativo lê as informações da topologia e, em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou no cluster do SQL Server. Este é o único tipo de instalação de banco de dados disponível se for usar o Construtor de Topologias. Se você precisar instalar um banco de dados específico em um computador específico ou se for necessário instalar um banco de dados posicionado, você deve usar a interface de linha de comando do Windows PowerShell e o cmdlet Install-CsDatabase.
ms.openlocfilehash: a4248827b7eba83534b0fdc2dc82dcaa3487e2d0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305959"
---
# <a name="create-database"></a><span data-ttu-id="24e4f-106">Criar Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="24e4f-106">Create Database</span></span>
 
<span data-ttu-id="24e4f-107">O construtor de topologias fornece uma maneira de instalar bancos de dados em uma loja do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="24e4f-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="24e4f-108">Ao instalar bancos de dados usando o construtor de topologias, o aplicativo lê as informações da topologia e, em seguida, instala os bancos de dados necessários no computador SQL Server especificado ou no cluster do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="24e4f-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="24e4f-109">Este é o único tipo de instalação de banco de dados disponível se for usar o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="24e4f-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="24e4f-110">Se você precisar instalar um banco de dados específico em um computador específico ou se for necessário instalar um banco de dados posicionado, você deve usar a interface de linha de comando do Windows PowerShell e o cmdlet [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="24e4f-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="24e4f-111">Criando um banco de dados</span><span class="sxs-lookup"><span data-stu-id="24e4f-111">Creating a Database</span></span>

1. <span data-ttu-id="24e4f-112">Clique no nó Skype for Business Server 2015 e, em seguida, clique em **instalar banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="24e4f-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="24e4f-113">Na caixa de diálogo **instalar bancos** de dados, na página **criar banco de dados** , selecione o nome de domínio totalmente qualificado (FQDN) da loja do SQL Server em que os novos bancos de dados devem ser criados.</span><span class="sxs-lookup"><span data-stu-id="24e4f-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="24e4f-p103">Clique em **Avançado**. Na caixa de diálogo **Selecionar Local do Arquivo de Banco de Dados**, selecione uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="24e4f-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="24e4f-p104">**Determinar o local do arquivo de banco de dados automaticamente**. Caso selecione essa opção, o Construtor de Topologias utiliza um algoritmo interno para escolher o local de armazenamento para os logs de banco de dados e arquivos de dados.</span><span class="sxs-lookup"><span data-stu-id="24e4f-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="24e4f-118">**Usar padrões de instância do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="24e4f-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="24e4f-119">Se você selecionar essa opção, o algoritmo interno não será usado para escolher os locais de armazenamento dos logs e dos arquivos de dados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="24e4f-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="24e4f-120">Em vez disso, os arquivos de log e dados são armazenados nos locais especificados pelo caminho de padrões do SQL Server (esses caminhos devem ser configurados em avançado por um administrador do SQL Server).</span><span class="sxs-lookup"><span data-stu-id="24e4f-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="24e4f-121">Os arquivos de dados serão armazenados no local padrão do arquivo de dados do SQL Server enquanto os arquivos de log serão armazenados no local padrão do arquivo de log do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="24e4f-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="24e4f-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="24e4f-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="24e4f-123">Na página **Criar banco de dados**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="24e4f-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="24e4f-124">Na página  **Criação de banco de dados concluída**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="24e4f-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

