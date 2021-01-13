---
title: Adicionar Repositório de Arquivamento Front End
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: O arquivamento requer uma edição de 64 bits suportada do software de banco de dados do Microsoft SQL Server para armazenar os dados de arquivamento. Você pode selecionar um banco de dados sql Server definido anteriormente a ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server deve residir, além da instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).
ms.openlocfilehash: 9e094bacca87e6b70a7caa1db9c43a5c98c0edbd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824211"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="f8ade-104">Adicionar Repositório de Arquivamento Front-end</span><span class="sxs-lookup"><span data-stu-id="f8ade-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="f8ade-105">O arquivamento requer uma edição de 64 bits suportada do software de banco de dados do Microsoft SQL Server para armazenar os dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="f8ade-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="f8ade-106">Você pode selecionar um banco de dados sql Server definido anteriormente a ser usado para arquivamento ou definir um novo banco de dados do SQL Server especificando um FQDN (nome de domínio totalmente qualificado) do servidor no qual o banco de dados do SQL Server deve residir, além da instância do SQL Server que você deseja usar para o novo banco de dados do SQL Server (que pode ser a instância padrão ou uma instância nomeada especificada por você).</span><span class="sxs-lookup"><span data-stu-id="f8ade-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="f8ade-p103">Se a conta usada para publicar a topologia tiver os direitos de usuário e permissões apropriadas, será possível criar o banco de dados de monitoramento ao publicar sua topologia. Também é possível criar o banco de dados posteriormente, incluído como parte do procedimento de instalação.</span><span class="sxs-lookup"><span data-stu-id="f8ade-p103">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology. You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="f8ade-109">Para instalar e implantar os bancos de dados no servidor baseado em SQL Server para monitoramento, você deve ser membro do grupo sysadmins do SQL Server para o servidor baseado em SQL Server no qual você está instalando os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f8ade-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="f8ade-110">Se você não for membro do grupo sysadmin do SQL Server, deverá solicitar que seja adicionado ao grupo até que os arquivos de banco de dados sejam implantados.</span><span class="sxs-lookup"><span data-stu-id="f8ade-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="f8ade-111">Se você não puder ser membro do grupo sysadmins, forneça ao administrador do banco de dados do SQL Server o script para configurar e implantar os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="f8ade-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="f8ade-112">Para obter detalhes sobre os direitos e permissões de usuário necessários para realizar os procedimentos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) na documentação Implantação.</span><span class="sxs-lookup"><span data-stu-id="f8ade-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


