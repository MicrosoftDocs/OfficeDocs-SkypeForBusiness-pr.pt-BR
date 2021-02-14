---
title: Adicionar Repositório de Servidor SQL Front End
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Uma implantação de servidor Standard Edition instala automaticamente o software de banco de dados microsoft SQL Server Express necessário e o banco de dados do SQL Server. Portanto, todas as opções são pré-populadas e você não pode fazer alterações na configuração padrão.
ms.openlocfilehash: d1a3fd6a27ab6229f84e8b74259be6a2da7652f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811621"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="20e4c-104">Adicionar Front-end do Repositório do SQL Server</span><span class="sxs-lookup"><span data-stu-id="20e4c-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="20e4c-105">Uma implantação de servidor Standard Edition instala automaticamente o software de banco de dados microsoft SQL Server Express necessário e o banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20e4c-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="20e4c-106">Portanto, todas as opções são pré-populadas e você não pode fazer alterações na configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="20e4c-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="20e4c-107">O pool #A0 de uma implantação de servidor Enterprise Edition requer uma edição de 64 bits suportada do software de banco de dados do SQL Server para o banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="20e4c-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="20e4c-108">Você pode selecionar um banco de dados sql Server definido anteriormente a ser usado para o banco de dados back-end ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server deve residir e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).</span><span class="sxs-lookup"><span data-stu-id="20e4c-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="20e4c-109">Também é possível escolher habilitar o espelhamento no SQL Server store e especificar uma testemunha de espelhamento para failover automático.</span><span class="sxs-lookup"><span data-stu-id="20e4c-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="20e4c-110">Para obter detalhes sobre o suporte ao SQL Server, consulte [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) na documentação de Suporte.</span><span class="sxs-lookup"><span data-stu-id="20e4c-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="20e4c-111">Para obter detalhes sobre como configurar o SQL Server para o banco de dados back-end, consulte [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="20e4c-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="20e4c-p105">Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados back-end (comunicação em tempo real (RTC)) ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, incluído como parte do procedimento de instalação.</span><span class="sxs-lookup"><span data-stu-id="20e4c-p105">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology. You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="20e4c-114">Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para uma implantação Enterprise Edition, você deve ser membro do grupo sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="20e4c-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="20e4c-115">Se você não for membro do grupo sysadmins do SQL Server, deverá solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados.</span><span class="sxs-lookup"><span data-stu-id="20e4c-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="20e4c-116">Se você não puder ser membro do grupo sysadmins, forneça ao administrador do banco de dados do SQL Server o script para configurar e implantar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="20e4c-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="20e4c-117">Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span><span class="sxs-lookup"><span data-stu-id="20e4c-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


