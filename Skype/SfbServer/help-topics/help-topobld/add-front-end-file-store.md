---
title: Adicionar Repositório de Arquivo do Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivo existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivo especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivo será localizado e um nome de pasta para o novo compartilhamento de arquivo.
ms.openlocfilehash: 4e2c732e0003f23cf183374880592ccd24fbe9bb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218342"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="22a35-104">Adicionar Repositório de Arquivo do Front End</span><span class="sxs-lookup"><span data-stu-id="22a35-104">Add Front End File Store</span></span>

<span data-ttu-id="22a35-p102">É necessário especificar um compartilhamento de arquivo a ser usado como o repositório de arquivo para o servidor Standard Edition ou pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivo existente para o repositório de arquivos, ou é possível especificar um novo compartilhamento de arquivo especificando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos no qual o compartilhamento de arquivo será localizado e um nome de pasta para o novo compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="22a35-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22a35-107">O compartilhamento de arquivos não pode ser localizado no servidor de front-ends Enterprise Edition, mas pode estar localizado em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="22a35-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22a35-108">É possível definir o compartilhamento de arquivo no Construtor de Topologia antes de criar o compartilhamento de arquivo, mas é necessário criar o compartilhamento de arquivo no local definido antes de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="22a35-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22a35-p103">Ao adicionar um pool de Front-Ends Enterprise ou servidor Standard Edition à sua topologia, o Construtor de Topologia precisa ser capaz de configurar o repositório de arquivos e configurar as listas de controle de acesso condicional (DACLs) no compartilhamento de arquivo a ser usado para o repositório de arquivos. Isso exige que, quando você executa o Construtor de Topologia para publicar a nova topologia, você é conectado com uma conta que tem permissões de controle total (leitura/gravação/modificação) para o compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="22a35-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="22a35-111">Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [File Storage support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) na documentação de suporte e [dados do SQL Server e posicionamento de arquivos de log](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="22a35-111">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="22a35-112">Para maiores detalhes sobre a colocação do compartilhamento de arquivos, consulte  [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação de Suporte.</span><span class="sxs-lookup"><span data-stu-id="22a35-112">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="22a35-113">Para obter detalhes sobre como projetar a topologia para um pool Front-Ends Enterprise Edition, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) na documentação Implantação.</span><span class="sxs-lookup"><span data-stu-id="22a35-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>


