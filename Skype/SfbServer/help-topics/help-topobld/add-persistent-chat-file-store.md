---
title: Adicionar Repositório de Arquivo de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos ou definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
ms.openlocfilehash: df8fd066961f872245ca0f5111726856180646cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897405"
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="1aa52-104">Adicionar Repositório de Arquivo de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="1aa52-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="1aa52-p102">Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos ou definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1aa52-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1aa52-107">O compartilhamento de arquivo para Skype para Business Server não pode ser localizado no servidor Enterprise Edition Front End, mas pode estar localizado em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1aa52-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1aa52-108">Você pode definir o compartilhamento de arquivos no Construtor de Topologias antes de criar o repositório de arquivos, mas deve criar o repositório de arquivos no local definido por você antes de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="1aa52-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1aa52-109">Quando você adicionar um servidor de Chat persistente ou servidor de Chat persistente pool a sua topologia, construtor de topologia deve ser capaz de configurar o arquivo armazenar e configurar o controle de acesso discricionário DACLs (listas) no compartilhamento de arquivos a serem usados para o repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1aa52-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="1aa52-110">Isso exige que, quando executar o Construtor de Topologias para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) para o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1aa52-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1aa52-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="1aa52-111">See also</span></span>

[<span data-ttu-id="1aa52-112">Planejar Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1aa52-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="1aa52-113">Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015</span><span class="sxs-lookup"><span data-stu-id="1aa52-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="1aa52-114">Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1aa52-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="1aa52-115">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1aa52-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="1aa52-116">Noções básicas de topologia para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1aa52-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
