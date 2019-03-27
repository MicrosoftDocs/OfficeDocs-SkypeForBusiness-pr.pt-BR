---
title: Adicionar Repositório de Arquivos de Front-End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivos especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivos será localizado e um nome de pasta para o novo compartilhamento de arquivo.
ms.openlocfilehash: 086e818483ef56c31c16c49895eeff6f889c0f8e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889540"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="c965a-104">Adicionar Repositório de Arquivos de Front-End</span><span class="sxs-lookup"><span data-stu-id="c965a-104">Add Front End File Store</span></span>

<span data-ttu-id="c965a-p102">É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivos especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivos será localizado e um nome de pasta para o novo compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c965a-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c965a-107">O compartilhamento de arquivos não pôde ser localizado no Servidor de Front-Ends Enterprise Edition, mas foi localizado em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c965a-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c965a-108">Você pode definir o compartilhamento de arquivos no Construtor de Topologias antes de criar o repositório de arquivos, mas deverá criá-lo no local que você definiu antes de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="c965a-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c965a-p103">Ao adicionar um pool de Front-Ends Enterprise ou servidor Standard Edition à sua topologia, o Construtor de Topologias tem que instalar o repositório de arquivos e configurar as listas de controle de acesso condicional (DACL) no compartilhamento de arquivos a ser usado para o repositório de arquivos. Isso exige que você esteja conectado com uma conta que tenha permissões de controle total (leitura/gravação/modificação) sobre o compartilhamento de arquivos quando executar o Construtor de Topologias para publicar a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="c965a-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="c965a-p104">Para obter detalhes sobre o suporte ao armazenamento para compartilhamentos de arquivos,consulte [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) na documentação Sistema de Suporte e [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de Implantação. Para obter detalhes sobre a colocação do compartilhamento de arquivos, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação Sistema de Suporte. Para obter detalhes sobre como projetar a topologia para um pool Front-Ends Enterprise Edition, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) na documentação Implantação.</span><span class="sxs-lookup"><span data-stu-id="c965a-p104">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation. For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation. For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>


