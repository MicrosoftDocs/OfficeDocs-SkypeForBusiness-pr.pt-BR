---
title: Adicionar Repositório de Arquivo Diretor
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para Diretores. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
ms.openlocfilehash: 2c7ad609ea3e58f0368f8c1e3d8716223aa68700
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824281"
---
# <a name="add-director-file-store"></a><span data-ttu-id="e2d69-104">Adicionar Repositório de Arquivo Diretor</span><span class="sxs-lookup"><span data-stu-id="e2d69-104">Add Director File Store</span></span>

<span data-ttu-id="e2d69-p102">Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para Diretores. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e2d69-p102">You must specify a file share to be used as the file store for Directors. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2d69-p103">Quando você adiciona Diretores a uma topologia, a publicação da topologia necessita de acesso apropriado para configurar o repositório de arquivos e as listas de controle de acesso condicional (DACLs) no compartilhamento de arquivo a ser usado para repositório de arquivos. Isso exige que você esteja conectado com uma conta que tenha permissões totais de controle (ler/gravar/modificar) para o compartilhamento de arquivos, quando executar o Construtor de Topologia e publicar a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="e2d69-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="e2d69-109">Para obter detalhes sobre o suporte de armazenamento para compartilhamentos de arquivos, consulte [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and SQL Server Data and Log File [Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="e2d69-109">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="e2d69-110">Para maiores detalhes sobre a colocação do compartilhamento de arquivos, consulte  [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) na documentação de Suporte.</span><span class="sxs-lookup"><span data-stu-id="e2d69-110">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="e2d69-111">Para maiores detalhes sobre como projetar a topologia para Diretores, consulte [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) na documentação de Implantação.</span><span class="sxs-lookup"><span data-stu-id="e2d69-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>


