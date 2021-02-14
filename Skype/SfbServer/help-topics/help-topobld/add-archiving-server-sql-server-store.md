---
title: Adicionar Repositório de Servidor SQL para Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: O Servidor de Arquivamento requer uma edição de 64 bits suportada do software de banco de dados do SQL Server para armazenar os dados de arquivo morto. Você pode selecionar um banco de dados do SQL Server definido anteriormente a ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server irá residir e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).
ms.openlocfilehash: 5200562ce8db04b741bfba7f62fbe42a2c8f47df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803681"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="60042-104">Adicionar Repositório do SQL Server para Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="60042-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="60042-105">O Servidor de Arquivamento requer uma edição de 64 bits suportada do software de banco de dados do SQL Server para armazenar os dados de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="60042-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="60042-106">Você pode selecionar um banco de dados do SQL Server definido anteriormente a ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server irá residir e a instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).</span><span class="sxs-lookup"><span data-stu-id="60042-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="60042-p103">Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados de arquivamento (LcsLog) ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, como parte do procedimento de instalação, ou de outra forma.</span><span class="sxs-lookup"><span data-stu-id="60042-p103">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology. You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="60042-109">Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para arquivamento, você deve ser membro do grupo sysadmins do SQL Server para o servidor baseado em SQL Server onde você está instalando os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="60042-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="60042-110">Se você não for membro do grupo sysadmins do SQL Server, deverá solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados.</span><span class="sxs-lookup"><span data-stu-id="60042-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="60042-111">Se você não puder ser membro do grupo sysadmins, forneça ao administrador do banco de dados do SQL Server o script para configurar e implantar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="60042-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="60042-112">Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação Implantação.</span><span class="sxs-lookup"><span data-stu-id="60042-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


