---
title: Adicionar Arquivo de Chat Persistente do Repositório
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
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de Front-Ends Enterprise Edition. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
ms.openlocfilehash: c77087520e51fffcad8c8341fe33103327e17799
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818671"
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="dba47-104">Adicionar Arquivo de Chat Persistente do Repositório</span><span class="sxs-lookup"><span data-stu-id="dba47-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="dba47-p102">Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de Front-Ends Enterprise Edition. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="dba47-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dba47-107">O compartilhamento de arquivos do Skype for Business Server não pode estar localizado no Servidor de Front End Enterprise Edition, mas pode estar localizado em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="dba47-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dba47-108">Você pode definir o compartilhamento de arquivos no Construtor de Topologias antes de criar o repositório de arquivos, mas deve criar o repositório de arquivos no local definido por você antes de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="dba47-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dba47-109">Quando você adiciona um Servidor de Chat Persistente ou pool de Servidor de Chat Persistente à sua topologia, o Construtor de Topologias deve ser capaz de configurar o armazenamento de arquivos e configurar as listas de controle de acesso discricionário (DACLs) no compartilhamento de arquivos a ser usado para o armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="dba47-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="dba47-110">Isso exige que, quando executar o Construtor de Topologia para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) para o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="dba47-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dba47-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="dba47-111">See also</span></span>

[<span data-ttu-id="dba47-112">Plano para Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dba47-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="dba47-113">Adicionar Servidor de Chat Persistente à sua topologia do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dba47-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="dba47-114">Requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dba47-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="dba47-115">Requisitos de servidor para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dba47-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="dba47-116">Noções básicas de topologia do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dba47-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
