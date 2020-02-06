---
title: Adicionar Repositório de Arquivamento Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: O arquivamento requer uma edição de 64 bits com suporte do software de banco de dados do Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server está para ficar, além da instância do SQL se rver que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).
ms.openlocfilehash: 234d0a2d4ef14aa969b8ef8c7445558e53ca2fee
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794900"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="0e2b3-104">Adicionar Repositório de Arquivamento Front End</span><span class="sxs-lookup"><span data-stu-id="0e2b3-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="0e2b3-105">O arquivamento requer uma edição de 64 bits com suporte do software de banco de dados do Microsoft SQL Server para armazenar os dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0e2b3-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="0e2b3-106">Você pode selecionar um banco de dados do SQL Server definido anteriormente para ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server está para ficar, além da instância do SQL se rver que você deseja usar para o novo banco de dados SQL Server (que pode ser a instância padrão ou uma instância nomeada que você especificar).</span><span class="sxs-lookup"><span data-stu-id="0e2b3-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="0e2b3-107">Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriados, você poderá criar o banco de dados de monitoramento quando publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="0e2b3-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="0e2b3-108">Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação.</span><span class="sxs-lookup"><span data-stu-id="0e2b3-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="0e2b3-109">Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para monitoramento, você deve ser um membro do grupo Administradores do SQL Server para o servidor baseado no SQL Server no qual está instalando os arquivos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0e2b3-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="0e2b3-110">Se você não for membro do grupo sysadmin do SQL Server, será necessário solicitar que você seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados.</span><span class="sxs-lookup"><span data-stu-id="0e2b3-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="0e2b3-111">Se você não puder se tornar membro do grupo sysadmins, você deve fornecer o administrador do banco de dados do SQL Server com o script para configurar e implantar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="0e2b3-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="0e2b3-112">Para obter detalhes sobre os direitos e permissões de usuário que você precisa para executar os procedimentos, consulte [permissões de implantação do SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="0e2b3-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


