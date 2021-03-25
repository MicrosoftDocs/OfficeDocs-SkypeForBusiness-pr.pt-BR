---
title: Adicionar Repositório de Arquivo do Front End
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivo existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivo especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivo será localizado e um nome de pasta para o novo compartilhamento de arquivo.
ms.openlocfilehash: e1dc0c94880bd161fae41be811847e1b0da3dbb5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118690"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="f5c08-104">Adicionar Repositório de Arquivo de Front-end</span><span class="sxs-lookup"><span data-stu-id="f5c08-104">Add Front End File Store</span></span>

<span data-ttu-id="f5c08-p102">É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivo existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivo especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivo será localizado e um nome de pasta para o novo compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f5c08-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5c08-107">O compartilhamento de arquivos não pode estar localizado no Servidor Front-End enterprise edition, mas pode estar localizado em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f5c08-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5c08-108">É possível definir o compartilhamento de arquivo no Construtor de Topologia antes de criar o compartilhamento de arquivo, mas é necessário criar o compartilhamento de arquivo no local definido antes de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="f5c08-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5c08-p103">Ao adicionar um pool de Front-Ends Enterprise ou servidor Standard Edition à sua topologia, o Construtor de Topologia precisa ser capaz de configurar o repositório de arquivos e configurar as listas de controle de acesso condicional (DACLs) no compartilhamento de arquivo a ser usado para o repositório de arquivos. Isso exige que, quando você executa o Construtor de Topologia para publicar a nova topologia, você é conectado com uma conta que tem permissões de controle total (leitura/gravação/modificação) para o compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f5c08-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="f5c08-111">Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) na documentação de Suporte e SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) na documentação de Implantação.</span><span class="sxs-lookup"><span data-stu-id="f5c08-111">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="f5c08-112">Para maiores detalhes sobre a colocação do compartilhamento de arquivos, consulte  [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) na documentação de Suporte.</span><span class="sxs-lookup"><span data-stu-id="f5c08-112">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span> <span data-ttu-id="f5c08-113">Para obter detalhes sobre como projetar a topologia para um pool Front-Ends Enterprise Edition, consulte [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) na documentação Implantação.</span><span class="sxs-lookup"><span data-stu-id="f5c08-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in the Deployment documentation.</span></span>