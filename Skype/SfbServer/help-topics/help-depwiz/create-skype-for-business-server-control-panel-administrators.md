---
title: Criar Administradores de Painel de Controle do Skype for Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Para conceder acesso para o Skype para Business Server 2015, faça o seguinte:'
ms.openlocfilehash: 5d01066da5be34ba53f4eca37d35a3913d07142a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898863"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="36599-103">Criar Administradores de Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="36599-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="36599-104">Para conceder acesso para o Skype para Business Server 2015, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="36599-104">To grant access to the Skype for Business Server 2015, do the following:</span></span>
  
1. <span data-ttu-id="36599-105">Faça logon como membro do grupo Admins. de Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="36599-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="36599-106">Abra **Usuários e Computadores do Active Directory**, expanda seu domínio, clique com o botão direito do mouse no contêiner **Usuários** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="36599-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="36599-107">Em **Propriedades de CSAdministrator**, clique na guia **Membros**.</span><span class="sxs-lookup"><span data-stu-id="36599-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="36599-p101">Na guia Membros, clique em **Adicionar**. Em **Selecionar Usuários, Contatos, Computadores, Contas de Serviço ou Grupos**, localize **Insira os nomes de objeto para seleção**. Digite os nomes de usuário ou nomes de grupo para adicionar ao grupo CSAdministrators. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="36599-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="36599-p102">Na guia Membros, confirme se os usuários ou grupos selecionados estão presentes. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="36599-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="36599-114">O Skype para painel de controle do Business Server é uma ferramenta de controle de acesso baseado em função.</span><span class="sxs-lookup"><span data-stu-id="36599-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="36599-115">A associação ao grupo CsAdministrator oferece um usuário que você está usando o Skype para controle total do painel de controle do servidor de negócios para todas as funções de configuração disponíveis.</span><span class="sxs-lookup"><span data-stu-id="36599-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="36599-116">Há outras funções disponíveis que foram projetadas para funções específicas.</span><span class="sxs-lookup"><span data-stu-id="36599-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="36599-117">Os usuários não precisam estar habilitado para Skype para Business Server para se tornar membros dos grupos de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="36599-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="36599-118">Outras funções incluem:</span><span class="sxs-lookup"><span data-stu-id="36599-118">Other roles include:</span></span>
  
- <span data-ttu-id="36599-119">**CsArchiving:** Membros desse grupo podem executar todas as funções de arquivamento, como configurar e gerenciar a função de servidor de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="36599-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="36599-p104">**CsHelpDesk:** Membros desse grupo podem exibir a configuração e implantação, incluindo propriedades e políticas de usuário. Os membros também podem executar tarefas específicas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="36599-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="36599-p105">**CsLocationAdministrator:** Os membros têm o nível mais baixo de direitos de usuário associados ao gerenciamento do 9-1-1 Avançado (E9-1-1). Eles podem criar locais e identificadores de rede do E9-1-1 e associá-los à implantação.</span><span class="sxs-lookup"><span data-stu-id="36599-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="36599-124">**CsResponseGroupAdministrator:** Os membros podem gerenciar e configurar o serviço do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="36599-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="36599-125">**CsServerAdministrator:** Membros podem gerenciar, monitorar e solucionar problemas de todos os servidores que executam o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="36599-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="36599-126">**CsUserAdministrator:** Os membros podem gerenciar, habilitar e desabilitar os usuários, e atribuir políticas existentes aos usuários.</span><span class="sxs-lookup"><span data-stu-id="36599-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="36599-127">**CsViewOnlyAdministrator:** Os membros podem exibir a implantação e a configuração das informações do servidor.</span><span class="sxs-lookup"><span data-stu-id="36599-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="36599-128">Essa associação permite que o membro para monitorar a integridade dos servidores que executam o Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="36599-128">This membership enables a member to monitor the health of the servers running Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="36599-129">**CsVoiceAdministrator:** Os membros podem criar, configurar e gerenciar configurações relacionadas à voz no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="36599-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="36599-130">Para ajudar a manter a segurança e a integridade do controle de acesso baseado em função, adicione usuários aos grupos que definem qual função o usuário executa no gerenciamento do Skype para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="36599-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

