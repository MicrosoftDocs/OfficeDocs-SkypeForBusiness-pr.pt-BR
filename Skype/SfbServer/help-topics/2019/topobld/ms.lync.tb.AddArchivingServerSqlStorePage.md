---
title: Adicionar repositório de servidor SQL de servidor de arquivamento
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: Servidor de arquivamento requer uma edição de 64 bits com suporte de software de banco de dados do SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados do SQL Server previamente definido para ser usado para arquivamento ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual residirá o banco de dados do SQL Server e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: 25987e72efc7906af49e30cc839d495e374d29ec
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21067698"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="1fd98-104">Adicionar repositório de servidor SQL de servidor de arquivamento</span><span class="sxs-lookup"><span data-stu-id="1fd98-104">Add Archiving Server SQL Server Store</span></span>
 
<span data-ttu-id="1fd98-105">Servidor de arquivamento requer uma edição de 64 bits com suporte de software de banco de dados do SQL Server para armazenar os dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="1fd98-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="1fd98-106">Você pode selecionar um banco de dados do SQL Server previamente definido para ser usado para arquivamento ou definir um novo banco de dados do SQL Server, especificando um nome de domínio totalmente qualificado (FQDN) do servidor no qual residirá o banco de dados do SQL Server e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).</span><span class="sxs-lookup"><span data-stu-id="1fd98-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fd98-107">Se a conta que é usada para publicar a topologia tem as permissões e direitos de usuário apropriados, você pode criar o banco de dados de arquivamento (LcsLog) quando você publica sua topologia.</span><span class="sxs-lookup"><span data-stu-id="1fd98-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="1fd98-108">Também é possível criar o banco de dados mais tarde, como parte do procedimento de instalação, ou outra forma.</span><span class="sxs-lookup"><span data-stu-id="1fd98-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1fd98-109">Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para arquivamento, você deve ser membro do grupo de sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1fd98-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="1fd98-110">Se você não é um membro do grupo de sysadmins do SQL Server, você deverá solicitar a ser adicionado ao grupo até que os arquivos de banco de dados são implantados.</span><span class="sxs-lookup"><span data-stu-id="1fd98-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="1fd98-111">Se você não pode se tornar um membro do grupo Administradores do sistema, você deve fornecer o seu administrador de banco de dados do SQL Server com o script para configurar e implantar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="1fd98-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="1fd98-112">Para obter detalhes sobre os direitos e permissões necessárias para realizar os procedimentos, consulte [Permissões de implantação para o SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="1fd98-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  

