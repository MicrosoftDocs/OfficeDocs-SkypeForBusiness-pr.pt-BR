---
title: Adicionar Repositório de Servidor SQL para Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: O servidor de arquivamento requer uma edição de 64 bits do software de banco de dados do SQL Server compatível para armazenar os dados de arquivo morto. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para arquivar ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server residirá e a instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: cda788a83b67b94f4064ca2f967878b88527b0c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304937"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="33bad-104">Adicionar Repositório de Servidor SQL para Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="33bad-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="33bad-105">O servidor de arquivamento requer uma edição de 64 bits do software de banco de dados do SQL Server compatível para armazenar os dados de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="33bad-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="33bad-106">Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para arquivar ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server residirá e a instância do SQL Server que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).</span><span class="sxs-lookup"><span data-stu-id="33bad-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="33bad-107">Se a conta que é usada para publicar a topologia tiver os direitos de usuário e permissões apropriados, você poderá criar o banco de dados de arquivamento (LcsLog) quando publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="33bad-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="33bad-108">Você também pode criar o banco de dados posteriormente, como parte do procedimento de instalação ou de outra forma.</span><span class="sxs-lookup"><span data-stu-id="33bad-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="33bad-109">Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para arquivamento, você deve ser membro do grupo Administradores do SQL Server para o servidor baseado em SQL Server no qual está instalando os arquivos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="33bad-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="33bad-110">Se você não for membro do grupo Administradores do SQL Server, será necessário solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados.</span><span class="sxs-lookup"><span data-stu-id="33bad-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="33bad-111">Se você não puder se tornar membro do grupo sysadmins, você deve fornecer o administrador do banco de dados do SQL Server com o script para configurar e implantar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="33bad-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="33bad-112">Para obter detalhes sobre os direitos e permissões de usuário que você precisa para executar os procedimentos, consulte [permissões de implantação do SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="33bad-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


