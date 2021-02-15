---
title: Configuração de notificação por push do cliente móvel
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Para configurar as Notificações por push da Microsoft e asNotificações por push da Apple, é necessário criar uma política para definir quais tipos de notificação por push você precisa.
ms.openlocfilehash: 693b954fffbbce56a2d95ce29128482937b6fa05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836671"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="75c04-103">Cliente Móvel: Configuração de Notificação por Push</span><span class="sxs-lookup"><span data-stu-id="75c04-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="75c04-104">Para configurar as **Notificações por push da Microsoft** e as **Notificações por push da Apple**, é necessário criar uma política para definir quais tipos de notificação por push você precisa.</span><span class="sxs-lookup"><span data-stu-id="75c04-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="75c04-p101">Na tela de configuração principal, é possível clicar em **Atualizar** para atualizar e preencher novamente a lista de políticas. Uma caixa de pesquisa é fornecida para reduzir a lista de políticas exibidas. À medida que você digita o nome que está procurando, a lista de políticas é reduzida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="75c04-p101">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies. A search box is provided for narrowing the list of displayed policies. As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="75c04-108">As configurações de política aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="75c04-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="75c04-109">A precedência da política é: a política de usuário (mais influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (menos influência).</span><span class="sxs-lookup"><span data-stu-id="75c04-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="75c04-110">Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="75c04-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="75c04-111">Há duas seleções disponíveis para criação e edição de política:</span><span class="sxs-lookup"><span data-stu-id="75c04-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="75c04-p103">**Novo**: clique para criar uma nova política. É necessário fornecer um site ao qual aplicar a política. Em seguida, você define as configurações para a notificação por push. Para **Configuração da Notificação por Push**, é possível apenas criar políticas para Sites que você já criou.</span><span class="sxs-lookup"><span data-stu-id="75c04-p103">**New**: Click to create a new policy. You must provide a site for the policy to apply to. You then configure the settings for the push notification. For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="75c04-p104">**Editar**: selecione uma política e clique em Editar para selecionar uma ação de um menu suspenso. Você pode apenas editar sites que já criou ou editar a Política Global:</span><span class="sxs-lookup"><span data-stu-id="75c04-p104">**Edit**: Select a policy and click Edit to select an action from a drop-down. You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="75c04-p105">**Mostrar detalhes…**: exibe informações sobre a política atualmente selecionada. Você poderá fazer alterações na política existente.</span><span class="sxs-lookup"><span data-stu-id="75c04-p105">**Show details…**: Displays information about the currently selected policy. You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="75c04-120">**Selecionar tudo**: se você tiver algumas políticas e precisar selecionar todas elas, clique em Selecionar tudo</span><span class="sxs-lookup"><span data-stu-id="75c04-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="75c04-p106">**Excluir**: removerá a política selecionada. Usar **Selecionar tudo** e **Excluir** removerá todas as políticas</span><span class="sxs-lookup"><span data-stu-id="75c04-p106">**Delete**: Will remove the selected policy. Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="75c04-p107">Não é possível excluir a política **Global** padrão. Se você tentar exclui-la, receberá uma notificação de que a política Global retomou seus valores padrão (ou seja, todas as configurações foram desmarcadas), mas a política não pode ser removida.</span><span class="sxs-lookup"><span data-stu-id="75c04-p107">You cannot delete the default **Global** policy. If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="75c04-125">A criação de uma nova política ou edição de uma política existente está associada a duas ações:</span><span class="sxs-lookup"><span data-stu-id="75c04-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="75c04-126">**Commit** A ação de confirmação cria ou atualiza a política e salva as alterações</span><span class="sxs-lookup"><span data-stu-id="75c04-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="75c04-127">**Cancelar** A ação cancela todas as alterações feitas desde a última ação de confirmação.</span><span class="sxs-lookup"><span data-stu-id="75c04-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="75c04-128">Se você cancelar, quaisquer alterações feitas serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="75c04-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="75c04-p109">Duas configurações são possíveis para a **Configuração de Notificação por Push**. As configurações são associadas aos serviços de notificação por push da Microsoft e da Apple. Habilite a notificação por push para qualquer um desses serviços marcando a caixa de seleção ao lado do nome do serviço. É possível desmarcar a caixa de seleção clicando nela. Depois de fazer suas seleções, confirme ou cancele. Clicar em confirmar salvará as alterações na política.</span><span class="sxs-lookup"><span data-stu-id="75c04-p109">Two settings are possible for **Push Notification Configuration**. The settings are associated with the push notification services for Microsoft and for Apple. You enable push notification for either service by selecting the check box next to the name of the service. You can clear the check box by selecting it to clear it. Once you have made your selections, you either commit or cancel. Clicking commit will save the changes to the policy.</span></span>
  

