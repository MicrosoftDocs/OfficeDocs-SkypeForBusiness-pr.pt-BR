---
title: Configuração de notificação por push de cliente móvel
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Para configurar as notificações por push da Microsoft e as notificações por push da Apple, você deve criar uma política para definir quais tipos de notificação por push são necessárias.
ms.openlocfilehash: 0211b3a8306297bd68402ad47d3c243541adf2bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300326"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="7daad-103">Cliente Móvel: Configuração de Notificação por Push</span><span class="sxs-lookup"><span data-stu-id="7daad-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="7daad-104">Para configurar as notificações por push da **Microsoft** e as **notificações por push da Apple**, você deve criar uma política para definir quais tipos de notificação por push são necessárias.</span><span class="sxs-lookup"><span data-stu-id="7daad-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="7daad-105">Na tela principal de configuração, você pode clicar em **Atualizar** para atualizar e preencher novamente a lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="7daad-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="7daad-106">Uma caixa de pesquisa é fornecida para restringir a lista de políticas exibidas.</span><span class="sxs-lookup"><span data-stu-id="7daad-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="7daad-107">À medida que você digita o nome que está procurando, a lista de políticas é limitada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7daad-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7daad-p102">As definições de política que são aplicadas em determinado nível de política podem substituir definições que são aplicadas em outro nível. A precedência de política é: política de Usuário (maior influência) substitui uma política de Site e esta substitui uma política Global (menor influência). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="7daad-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="7daad-111">Duas seleções estão disponíveis para criação e edição de políticas:</span><span class="sxs-lookup"><span data-stu-id="7daad-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="7daad-112">**Novo**: clique para criar uma nova política.</span><span class="sxs-lookup"><span data-stu-id="7daad-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="7daad-113">Você deve fornecer um site ao qual a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="7daad-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="7daad-114">Em seguida, defina as configurações para a notificação por push.</span><span class="sxs-lookup"><span data-stu-id="7daad-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="7daad-115">Para a **configuração de notificação por push**, você só pode criar políticas para sites que já criou.</span><span class="sxs-lookup"><span data-stu-id="7daad-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="7daad-116">**Editar**: selecione uma política e clique em Editar para selecionar uma ação de uma lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="7daad-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="7daad-117">Você só pode editar sites que já criou ou editar a política global:</span><span class="sxs-lookup"><span data-stu-id="7daad-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="7daad-118">**Mostrar detalhes...**: exibe informações sobre a política selecionada no momento.</span><span class="sxs-lookup"><span data-stu-id="7daad-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="7daad-119">Você poderá fazer alterações na política existente.</span><span class="sxs-lookup"><span data-stu-id="7daad-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="7daad-120">**Selecionar tudo**: se você tiver uma quantidade de políticas e precisar selecionar todas as políticas, clique em selecionar tudo</span><span class="sxs-lookup"><span data-stu-id="7daad-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="7daad-121">**Excluir**: a política selecionada será removida.</span><span class="sxs-lookup"><span data-stu-id="7daad-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="7daad-122">Usar **selecionar tudo** e **excluir** irá remover todas as políticas</span><span class="sxs-lookup"><span data-stu-id="7daad-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="7daad-123">Não é possível excluir a política **global** padrão.</span><span class="sxs-lookup"><span data-stu-id="7daad-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="7daad-124">Se você tentar excluí-lo, você será notificado de que a política global foi retornada para os valores padrão (ou seja, todas as configurações são desmarcadas), mas a política não pode ser removida.</span><span class="sxs-lookup"><span data-stu-id="7daad-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="7daad-125">A criação de uma nova política ou edição de uma política existente é associada a duas ações:</span><span class="sxs-lookup"><span data-stu-id="7daad-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="7daad-126">**Confirmar** A ação confirmar cria ou atualiza a política e salva as alterações</span><span class="sxs-lookup"><span data-stu-id="7daad-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="7daad-127">**Cancelar** A ação cancelar descarta todas as alterações feitas desde a última ação de confirmação.</span><span class="sxs-lookup"><span data-stu-id="7daad-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="7daad-128">Se você cancelar, todas as alterações feitas serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="7daad-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="7daad-129">Duas configurações são possíveis para a **configuração de notificação por push**.</span><span class="sxs-lookup"><span data-stu-id="7daad-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="7daad-130">As configurações são associadas aos serviços de notificação por push para a Microsoft e para a Apple.</span><span class="sxs-lookup"><span data-stu-id="7daad-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="7daad-131">Para habilitar a notificação por push para qualquer um dos serviços, marque a caixa de seleção ao lado do nome do serviço.</span><span class="sxs-lookup"><span data-stu-id="7daad-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="7daad-132">Você pode desmarcar a caixa de seleção selecionando-a para desmarcá-la.</span><span class="sxs-lookup"><span data-stu-id="7daad-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="7daad-133">Depois de fazer suas seleções, você pode confirmar ou cancelar.</span><span class="sxs-lookup"><span data-stu-id="7daad-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="7daad-134">Clicar em confirmar irá salvar as alterações na política.</span><span class="sxs-lookup"><span data-stu-id="7daad-134">Clicking commit will save the changes to the policy.</span></span>
  

