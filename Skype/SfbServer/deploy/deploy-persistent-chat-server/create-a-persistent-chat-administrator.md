---
title: Criar um administrador de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumo: Leia este tópico para saber como criar uma função de administrador de servidor de chat persistente para habilitar a configuração e o gerenciamento iniciais de serviços de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 3692169a65d73c3951ce58e77b132a4f118c54e9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239762"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="6296f-103">Criar um administrador de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6296f-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6296f-104">**Resumo:** Leia este tópico para saber como criar uma função de administrador de servidor de chat persistente para habilitar a configuração e o gerenciamento iniciais de serviços de chat persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6296f-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6296f-105">No Skype for Business Server, os usuários que executam tarefas específicas devem ser atribuídos como membros de um ou mais grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="6296f-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="6296f-106">O controle de acesso baseado em função (RBAC) é usado para conceder privilégios atribuindo usuários a funções administrativas predefinidas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6296f-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="6296f-107">Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6296f-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="6296f-108">Os membros do grupo de segurança de administrador de chat persistente, CsPersistentChatAdministrator, recebem acesso aos cmdlets do servidor de chat persistente, que podem ser executados usando o Shell de gerenciamento do Skype for Business Server ou o Skype for Business Painel de controle do servidor.</span><span class="sxs-lookup"><span data-stu-id="6296f-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="6296f-109">Antes de configurar e administrar o Servidor de Chat Persistente, certifique-se de que as permissões e os direitos do usuário adequados estejam em vigor e que os usuários designados como administradores do Chat Persistente serão adicionados ao grupo de segurança Administradores do Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="6296f-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="6296f-110">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6296f-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6296f-111">A mesma funcionalidade está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6296f-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="6296f-112">Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="6296f-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="6296f-113">Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6296f-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="6296f-114">Criar um administrador de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="6296f-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="6296f-115">Para adicionar um usuário ao grupo de segurança de administrador de chat persistente, CsPersistentChatAdministrator, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6296f-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="6296f-116">Usando uma conta que tenha permissão para modificar a associação a um grupo do Active Directory, faça logon em um computador em que os usuários e computadores do Active Directory tenham sido instalados.</span><span class="sxs-lookup"><span data-stu-id="6296f-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="6296f-117">Clique em Iniciar, clique em Todos os Programas, clique em Ferramentas Administrativas e, em seguida, clique em Usuários e Computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6296f-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="6296f-118">Em Usuários e Computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner de Usuários.</span><span class="sxs-lookup"><span data-stu-id="6296f-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="6296f-119">Clique com o botão direito no grupo de segurança CsPersistentChatAdministrator e clique em Propriedades.</span><span class="sxs-lookup"><span data-stu-id="6296f-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="6296f-120">Na caixa de diálogo Propriedades, na guia Membros, clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="6296f-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="6296f-121">Na caixa de diálogo Selecionar Usuários, Computadores, Contatos ou Grupos, digite o nome de usuário ou nome de exibição do usuário a ser adicionado ao grupo (por exemplo, Ken Myer) na caixa Inserir os nomes de objeto a ser selecionados e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6296f-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="6296f-122">Na caixa de diálogo Propriedades, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6296f-122">In the Properties dialog box, click OK.</span></span>
    

