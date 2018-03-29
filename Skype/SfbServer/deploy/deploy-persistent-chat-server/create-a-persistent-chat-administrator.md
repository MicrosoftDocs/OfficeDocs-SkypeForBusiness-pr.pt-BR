---
title: Criar um administrador de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumo: Leia este tópico para saber como criar uma função de administrador de servidor de Chat persistente para habilitar a configuração inicial e o gerenciamento de serviços de Chat persistente no Skype para Business Server 2015.'
ms.openlocfilehash: 4efe5dff2821784a24f51712b8a19dad83e47c3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="112a8-103">Criar um administrador de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="112a8-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="112a8-104">**Resumo:** Leia este tópico para saber como criar uma função de administrador de servidor de Chat persistente para habilitar a configuração inicial e o gerenciamento de serviços de Chat persistente no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="112a8-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="112a8-105">No Skype para Business Server, os usuários que executam tarefas específicas devem ser atribuídos como membros de um ou mais grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="112a8-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="112a8-106">Controle de acesso baseado em função (RBAC) é usado para conceder privilégios atribuindo usuários a Skype predefinido para funções administrativas do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="112a8-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="112a8-107">Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="112a8-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="112a8-108">Membros do grupo de segurança Persistent Chat Administrator, função CsPersistentChatAdministrator, recebem acesso para os cmdlets do servidor de Chat persistente, que podem ser executados usando o Skype para Business Server Management Shell ou o Skype para negócios Painel de controle do servidor.</span><span class="sxs-lookup"><span data-stu-id="112a8-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="112a8-109">Antes de configurar e administrar o Servidor de Chat Persistente, certifique-se de que as permissões e os direitos do usuário adequados estejam em vigor e que os usuários designados como administradores do Chat Persistente serão adicionados ao grupo de segurança Administradores do Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="112a8-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="112a8-110">Criar um administrador de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="112a8-110">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="112a8-111">Para adicionar um usuário ao grupo de segurança Persistent Chat Administrator, função CsPersistentChatAdministrator, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="112a8-111">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="112a8-112">Usando uma conta que tenha permissão para modificar a associação a um grupo do Active Directory, faça logon em um computador em que os usuários e computadores do Active Directory tenham sido instalados.</span><span class="sxs-lookup"><span data-stu-id="112a8-112">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="112a8-113">Clique em Iniciar, clique em Todos os Programas, clique em Ferramentas Administrativas e, em seguida, clique em Usuários e Computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="112a8-113">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="112a8-114">Em Usuários e Computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner de Usuários.</span><span class="sxs-lookup"><span data-stu-id="112a8-114">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="112a8-115">Clique com o botão direito no grupo de segurança CsPersistentChatAdministrator e clique em Propriedades.</span><span class="sxs-lookup"><span data-stu-id="112a8-115">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="112a8-116">Na caixa de diálogo Propriedades, na guia Membros, clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="112a8-116">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="112a8-117">Na caixa de diálogo Selecionar Usuários, Computadores, Contatos ou Grupos, digite o nome de usuário ou nome de exibição do usuário a ser adicionado ao grupo (por exemplo, Ken Myer) na caixa Inserir os nomes de objeto a ser selecionados e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="112a8-117">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="112a8-118">Na caixa de diálogo Propriedades, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="112a8-118">In the Properties dialog box, click OK.</span></span>
    

