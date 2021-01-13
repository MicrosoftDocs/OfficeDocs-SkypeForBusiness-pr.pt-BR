---
title: Criar Administradores do Painel de Controle do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para conceder acesso ao Skype for Business Server, faça o seguinte:'
ms.openlocfilehash: cb1449aa4fcca534e01b4d8a47a7ac9c39cd64c7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824961"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="63edc-103">Criar Administradores do Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="63edc-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="63edc-104">Para conceder acesso ao Skype for Business Server, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="63edc-104">To grant access to the Skype for Business Server, do the following:</span></span>
  
1. <span data-ttu-id="63edc-105">Faça logon como membro do grupo Admins. de Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="63edc-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="63edc-106">Abra **Usuários e Computadores do Active Directory**, expanda seu domínio, clique com o botão direito do mouse no recipiente **Usuários** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="63edc-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="63edc-107">Em **Propriedades de CSAdministrator**, clique na guia **Membros**.</span><span class="sxs-lookup"><span data-stu-id="63edc-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="63edc-p101">Na guia Membros, clique em **Adicionar**. Em **Selecionar Usuários, Contatos, Computadores, Contas de Serviço ou Grupos**, localize **Insira os nomes de objeto para seleção**. Digite os nomes de usuário ou nomes de grupo para adicionar ao grupo CSAdministrators. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="63edc-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="63edc-p102">Na guia Membros, confirme se os usuários ou grupos selecionados estão presentes. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="63edc-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="63edc-114">O Painel de Controle do Skype for Business Server é uma ferramenta de controle de acesso baseada em função.</span><span class="sxs-lookup"><span data-stu-id="63edc-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="63edc-115">A associação ao grupo CsAdministrator oferece a um usuário que está usando o Painel de Controle do Skype for Business Server controle total para todas as funções de configuração disponíveis.</span><span class="sxs-lookup"><span data-stu-id="63edc-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="63edc-116">Há outras funções disponíveis que foram projetadas para funções específicas.</span><span class="sxs-lookup"><span data-stu-id="63edc-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="63edc-117">Os usuários não devem estar habilitados para o Skype for Business Server para se serem membros dos grupos de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="63edc-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="63edc-118">Outras funções incluem:</span><span class="sxs-lookup"><span data-stu-id="63edc-118">Other roles include:</span></span>
  
- <span data-ttu-id="63edc-119">**CsArchiving:** Os membros desse grupo podem executar todas as funções de arquivamento, como configurar e gerenciar a função de Servidor de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="63edc-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="63edc-p104">**CsHelpDesk:** Membros desse grupo podem exibir a configuração e implantação, incluindo propriedades e políticas de usuário. Os membros também podem executar tarefas de solução de problema específicas.</span><span class="sxs-lookup"><span data-stu-id="63edc-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="63edc-p105">**CsLocationAdministrator:** Os membros têm o nível mais baixo de direitos de usuário associados ao gerenciamento do 9-1-1 Avançado (E9-1-1). Eles podem criar locais e identificadores de rede do E9-1-1 e associá-los à implantação.</span><span class="sxs-lookup"><span data-stu-id="63edc-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="63edc-124">**CsResponseGroupAdministrator:** Os membros podem gerenciar e configurar o serviço do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="63edc-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="63edc-125">**CsServerAdministrator:** Os membros podem gerenciar, monitorar e solucionar problemas de todos os servidores que executam o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="63edc-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="63edc-126">**CsUserAdministrator:** Os membros podem gerenciar, habilitar e desabilitar os usuários, e atribuir políticas existentes aos usuários.</span><span class="sxs-lookup"><span data-stu-id="63edc-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="63edc-127">**CsViewOnlyAdministrator:** Os membros podem exibir a implantação e a configuração das informações do servidor.</span><span class="sxs-lookup"><span data-stu-id="63edc-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="63edc-128">Essa associação permite que um membro monitore a saúde dos servidores que executam o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="63edc-128">This membership enables a member to monitor the health of the servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="63edc-129">**CsVoiceAdministrator:** Os membros podem criar, configurar e gerenciar configurações relacionadas à voz no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="63edc-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="63edc-130">Para ajudar a manter a segurança e a integridade do controle de acesso baseado em função, adicione usuários aos grupos que definem qual função o usuário desempenha no gerenciamento da implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="63edc-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

