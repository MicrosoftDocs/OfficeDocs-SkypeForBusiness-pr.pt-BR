---
title: Adicionar Repositório de Arquivo de Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou especificar um novo compartilhamento de arquivos. Basta especificar o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deverá ser localizado, assim como o nome de sua pasta.
ms.openlocfilehash: d78058f862d916228f5be723c7edca6e45a1bb61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886800"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="ec599-104">Adicionar Repositório de Arquivo de Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="ec599-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="ec599-p102">Para habilitar o arquivamento de conteúdo de mensagens instantâneas e webconferências (reuniões), especifique um compartilhamento de arquivos a ser usado como repositório de arquivos para cópias de todo o conteúdo de webconferências. Você pode usar um compartilhamento de arquivos existente como repositório de arquivos de arquivamento ou especificar um novo compartilhamento de arquivos. Basta especificar o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos em que o novo compartilhamento deverá ser localizado, assim como o nome de sua pasta.</span><span class="sxs-lookup"><span data-stu-id="ec599-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec599-107">Você pode definir um compartilhamento de arquivos no Construtor de Topologia antes de criar o compartilhamento de arquivos, mas você deve criar um compartilhamento de arquivos no local definido antes de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="ec599-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="ec599-108">gt _ quando você adiciona um servidor de arquivamento à sua topologia, construtor de topologia deve ser capaz de instalar o repositório de arquivos de arquivamento e configurar listas de controle de acesso discricionário (DACLs) no compartilhamento de arquivos a serem usados para o repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ec599-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="ec599-109">Isso exige que, quando executar o Construtor de Topologias para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) sobre o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ec599-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="ec599-p104">Para obter detalhes sobre o suporte ao armazenamento para compartilhamentos de arquivo, consulte [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) na documentação Sistemas de suporte e [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação Implantação. Para obter detalhes sobre colocação do compartilhamento de arquivo, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação Sistemas de suporte.</span><span class="sxs-lookup"><span data-stu-id="ec599-p104">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation. For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


