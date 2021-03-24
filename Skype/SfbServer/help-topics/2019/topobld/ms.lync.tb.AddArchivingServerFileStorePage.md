---
title: Adicionar Repositório de Arquivo de Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou pode especificar um compartilhamento de arquivos novo, especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deve estar localizado e um nome de pasta para ele.
ms.openlocfilehash: 2e8c4ac23ce68eab111bbb7775eec23aba2f12d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100227"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="215f6-104">Adicionar Repositório de Arquivo do Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="215f6-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="215f6-p102">Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou pode especificar um compartilhamento de arquivos novo, especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deve estar localizado e um nome de pasta para ele.</span><span class="sxs-lookup"><span data-stu-id="215f6-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="215f6-107">Você pode definir um compartilhamento de arquivos no Construtor de Topologia antes de criar o compartilhamento de arquivos, mas você deve criar um compartilhamento de arquivos no local definido antes de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="215f6-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="215f6-108">> Quando você adiciona um Servidor de Arquivamento à sua topologia, o Construtor de Topologias deve ser capaz de configurar o armazenamento de arquivos de arquivamento e configurar listas de controle de acesso discricionário (DACLs) no compartilhamento de arquivos a ser usado para o armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="215f6-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="215f6-109">Isso exige que, quando executar o Construtor de Topologia para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) para o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="215f6-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="215f6-110">Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) na documentação de Suporte e SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) na documentação de Implantação.</span><span class="sxs-lookup"><span data-stu-id="215f6-110">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="215f6-111">Para obter detalhes sobre colocação do compartilhamento de arquivo, consulte [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) na documentação de Suporte.</span><span class="sxs-lookup"><span data-stu-id="215f6-111">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span>