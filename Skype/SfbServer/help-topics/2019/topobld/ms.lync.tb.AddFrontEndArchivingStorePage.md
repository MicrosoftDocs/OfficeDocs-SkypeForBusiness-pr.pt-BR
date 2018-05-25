---
title: Adicionar repositório de arquivamento Front-End
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: O arquivamento requer uma edição de 64 bits com suporte do software de banco de dados Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados do SQL Server definido anteriormente a ser usado para arquivamento, ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual o banco de dados do SQL Server residir, além da instância do SQL Se servidor & que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: 528c8062b07593a4c7e4cc00f3d1d2566c05f77e
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="4a7d0-104">Adicionar repositório de arquivamento Front-End</span><span class="sxs-lookup"><span data-stu-id="4a7d0-104">Add Front End Archiving Store</span></span>
 
<span data-ttu-id="4a7d0-105">O arquivamento requer uma edição de 64 bits com suporte do software de banco de dados Microsoft SQL Server para armazenar os dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="4a7d0-106">Você pode selecionar um banco de dados do SQL Server definido anteriormente a ser usado para arquivamento, ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual o banco de dados do SQL Server residir, além da instância do SQL Se servidor & que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).</span><span class="sxs-lookup"><span data-stu-id="4a7d0-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a7d0-107">Se a conta usada para publicar a topologia tem as permissões e direitos de usuário apropriados, você pode criar o banco de dados de monitoramento ao publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="4a7d0-108">Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-108">You can also create the database later, included as part of the installation procedure.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4a7d0-109">Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para monitoramento, você deve ser membro do grupo de sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="4a7d0-110">Se você não for um membro do grupo sysadmin do SQL Server, você deverá solicitar que você ser adicionado ao grupo até que os arquivos de banco de dados são implantados.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="4a7d0-111">Se você não pode se tornar um membro do grupo Administradores do sistema, você deve fornecer o seu administrador de banco de dados do SQL Server com o script para configurar e implantar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="4a7d0-112">Para obter detalhes sobre os direitos e permissões necessárias para realizar os procedimentos, consulte [Permissões de implantação para o SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  

