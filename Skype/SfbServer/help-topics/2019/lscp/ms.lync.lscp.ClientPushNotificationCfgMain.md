---
title: Configuração de notificação de Push do cliente móvel
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Para configurar as notificações de push da Microsoft e notificações de push do Apple, você deve criar uma política para definir quais tipos de notificação por push você exige.
ms.openlocfilehash: 4fbe14981bef31808426cc618bb1b26a803d7dc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891667"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="d703e-103">Cliente Móvel: Configuração de Notificação por Push</span><span class="sxs-lookup"><span data-stu-id="d703e-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="d703e-104">Para configurar as **notificações de push da Microsoft** e **notificações de push do Apple**, você deve criar uma política para definir quais tipos de notificação de push você requer.</span><span class="sxs-lookup"><span data-stu-id="d703e-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="d703e-105">Na tela Configuração principal, você pode clicar **Refresh** para atualizar e popular novamente a lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="d703e-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="d703e-106">Uma caixa de pesquisa é fornecida para restringir a lista de diretivas exibidas.</span><span class="sxs-lookup"><span data-stu-id="d703e-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="d703e-107">Conforme você digita o nome que você está procurando, lista de políticas estreita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d703e-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d703e-p102">As definições de política que são aplicadas em determinado nível de política podem substituir definições que são aplicadas em outro nível. A precedência de política é: política de Usuário (maior influência) substitui uma política de Site e esta substitui uma política Global (menor influência). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="d703e-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="d703e-111">Há duas seleções estão disponíveis para criação de políticas e edição:</span><span class="sxs-lookup"><span data-stu-id="d703e-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="d703e-112">**New**: clique para criar uma nova política.</span><span class="sxs-lookup"><span data-stu-id="d703e-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="d703e-113">Você deve fornecer um site para a política seja aplicada a.</span><span class="sxs-lookup"><span data-stu-id="d703e-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="d703e-114">Em seguida, você definir as configurações da notificação de push.</span><span class="sxs-lookup"><span data-stu-id="d703e-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="d703e-115">Para **Configuração de notificação por Push**, você só pode criar políticas para Sites que você criou.</span><span class="sxs-lookup"><span data-stu-id="d703e-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="d703e-116">**Editar**: selecione uma política e clique em Editar para selecionar uma ação na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="d703e-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="d703e-117">Você só pode editar os sites que você já criou ou editar a política Global:</span><span class="sxs-lookup"><span data-stu-id="d703e-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="d703e-118">**Mostrar detalhes …**: exibe informações sobre a política selecionada no momento.</span><span class="sxs-lookup"><span data-stu-id="d703e-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="d703e-119">Você poderá fazer alterações à diretiva existente.</span><span class="sxs-lookup"><span data-stu-id="d703e-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="d703e-120">**Selecionar tudo**: se você tiver algumas políticas e precisa selecionar todas elas, clique em Selecionar tudo</span><span class="sxs-lookup"><span data-stu-id="d703e-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="d703e-121">**Excluir**: removerá a política selecionada.</span><span class="sxs-lookup"><span data-stu-id="d703e-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="d703e-122">O uso de **Selecionar tudo** e **Excluir** removerá todas as diretivas</span><span class="sxs-lookup"><span data-stu-id="d703e-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="d703e-123">Você não pode excluir a política **Global** de padrão.</span><span class="sxs-lookup"><span data-stu-id="d703e-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="d703e-124">Se você tentar excluí-lo, você será notificado se a política Global foi retornada para os valores padrão (ou seja, todas as configurações estão desmarcadas), mas a política não pode ser removida.</span><span class="sxs-lookup"><span data-stu-id="d703e-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="d703e-125">Criando uma nova política ou editar uma política existente está associado a duas ações:</span><span class="sxs-lookup"><span data-stu-id="d703e-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="d703e-126">**Confirmar** A ação de confirmação cria ou atualiza a política e salva as alterações</span><span class="sxs-lookup"><span data-stu-id="d703e-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="d703e-127">**Cancelar** A ação Cancelar descarta quaisquer alterações que tenham sido feitas desde a última ação de confirmação.</span><span class="sxs-lookup"><span data-stu-id="d703e-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="d703e-128">Se você cancelar, quaisquer alterações feitas serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="d703e-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="d703e-129">Duas configurações são possíveis para a **Configuração de notificação por Push**.</span><span class="sxs-lookup"><span data-stu-id="d703e-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="d703e-130">As configurações estão associadas com os serviços de notificação por push para Microsoft e Apple.</span><span class="sxs-lookup"><span data-stu-id="d703e-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="d703e-131">Você pode habilitar notificação de envio para qualquer serviço marcando a caixa de seleção ao lado do nome do serviço.</span><span class="sxs-lookup"><span data-stu-id="d703e-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="d703e-132">Você pode desmarcar a caixa de seleção, selecionando-o para desmarcá-la.</span><span class="sxs-lookup"><span data-stu-id="d703e-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="d703e-133">Depois de fazer suas seleções, você confirmar ou Cancelar.</span><span class="sxs-lookup"><span data-stu-id="d703e-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="d703e-134">Quando você clica em Confirmar salvará as alterações à política.</span><span class="sxs-lookup"><span data-stu-id="d703e-134">Clicking commit will save the changes to the policy.</span></span>
  

