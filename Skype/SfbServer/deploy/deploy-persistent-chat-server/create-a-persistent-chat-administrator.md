---
title: Criar um administrador de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumo: Leia este tópico para saber como criar uma função de administrador de Servidor de Chat Persistente para habilitar a configuração inicial e o gerenciamento de serviços de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802091"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="a49cd-103">Criar um administrador de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a49cd-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a49cd-104">**Resumo:** Leia este tópico para saber como criar uma função de administrador de Servidor de Chat Persistente para habilitar a configuração inicial e o gerenciamento de serviços de Chat Persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a49cd-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a49cd-105">No Skype for Business Server, os usuários que executam tarefas específicas devem ser atribuídos como membros de um ou mais grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="a49cd-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="a49cd-106">Role-Based Controle de Acesso (RBAC) é usado para conceder privilégios atribuindo usuários a funções administrativas predefinidos do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a49cd-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="a49cd-107">Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio active Directory.</span><span class="sxs-lookup"><span data-stu-id="a49cd-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="a49cd-108">Os membros do grupo de segurança Administrador de Chat Persistente, CsPersistentChatAdministrator, têm acesso aos cmdlets do Servidor de Chat Persistente, que podem ser executados usando o Shell de Gerenciamento do Skype for Business Server ou o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a49cd-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="a49cd-109">Antes de configurar e administrar o Servidor de Chat Persistente, certifique-se de que os direitos e permissões de usuário apropriados estão em uso e que todos os usuários que atuarão como administradores de Chat Persistente sejam adicionados ao grupo de segurança Administrador de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="a49cd-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="a49cd-110">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a49cd-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a49cd-111">A mesma funcionalidade está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="a49cd-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="a49cd-112">Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="a49cd-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="a49cd-113">Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a49cd-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="a49cd-114">Criar um administrador de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="a49cd-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="a49cd-115">Para adicionar um usuário ao grupo de segurança Administrador de Chat Persistente, CsPersistentChatAdministrator, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a49cd-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="a49cd-116">Usando uma conta que tenha permissão para modificar a associação de um grupo do Active Directory, faça logoff em um computador em que os Usuários e Computadores do Active Directory tenham sido instalados.</span><span class="sxs-lookup"><span data-stu-id="a49cd-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="a49cd-117">Clique em Iniciar, clique em Todos os Programas, clique em Ferramentas Administrativas e, em seguida, clique em Usuários e Computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a49cd-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="a49cd-118">Em Usuários e Computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner de Usuários.</span><span class="sxs-lookup"><span data-stu-id="a49cd-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="a49cd-119">Clique com o botão direito do mouse no grupo de segurança CsPersistentChatAdministrator e clique em Propriedades.</span><span class="sxs-lookup"><span data-stu-id="a49cd-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="a49cd-120">Na caixa de diálogo Propriedades, na guia Membros, clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a49cd-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="a49cd-121">Na caixa de diálogo Selecionar Usuários, Computadores, Contatos ou Grupos, digite o nome de usuário ou nome de exibição do usuário a ser adicionado ao grupo na caixa Digite os nomes de objeto a serem selecionados e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a49cd-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="a49cd-122">Na caixa de diálogo Propriedades, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a49cd-122">In the Properties dialog box, click OK.</span></span>
    

