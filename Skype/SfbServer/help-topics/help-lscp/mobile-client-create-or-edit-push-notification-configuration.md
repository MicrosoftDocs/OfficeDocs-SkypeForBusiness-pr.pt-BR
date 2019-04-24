---
title: Cliente móvel criar ou Editar configuração de notificação por Push
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: Notificação por Push e Push Notification Clearing House (PNCH) são duas partes importantes do recurso de mobilidade. Notificação por Push é o processo no qual uma mensagem é enviada ao PNCH. A mensagem é mantida aqui até que possa ser entregue ao cliente móvel ou até esgotar o tempo limite.
ms.openlocfilehash: d9c3ae19255e58c9de5874d745107654a93f7a28
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200783"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="6f4e4-105">Cliente móvel: Crie ou edite a Configuração de Notificação por Push</span><span class="sxs-lookup"><span data-stu-id="6f4e4-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="6f4e4-p102">Notificação por Push e Push Notification Clearing House (PNCH) são duas partes importantes do recurso de mobilidade. Notificação por Push é o processo no qual uma mensagem é enviada ao PNCH. A mensagem é mantida aqui até que possa ser entregue ao cliente móvel ou até esgotar o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="6f4e4-p102">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature. Push notification is the process where a message is sent to the PNCH. The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6f4e4-109">O período é definido na Push Notification Clearing House e não pode ser configurado pelo usuário ou pelo administrador de sua implantação.</span><span class="sxs-lookup"><span data-stu-id="6f4e4-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="6f4e4-110">Para habilitar a Notificação por Push, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f4e4-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="6f4e4-p103">**Escopo:** observe o escopo dessa política. Pode ser **Global**, que se aplica a todos os usuários nessa implantação, ou **Site**, que são apenas usuários atribuídos a servidores domésticos no site especificado.</span><span class="sxs-lookup"><span data-stu-id="6f4e4-p103">**Scope:** Note the scope for this policy. It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6f4e4-p104">As definições de política que são aplicadas em determinado nível de política podem substituir definições que são aplicadas em outro nível. A precedência de política é: política de Usuário (maior influência) substitui uma política de Site e esta substitui uma política Global (menor influência). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="6f4e4-p104">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="6f4e4-116">Selecione quais serviços de notificação por push você deseja habilitar clicando na caixa de seleção para:</span><span class="sxs-lookup"><span data-stu-id="6f4e4-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="6f4e4-117">**Notificação de push da Microsoft permitem** habilitará a notificação por push para a nuvem PNCH para Windows Phone com o Skype para o aplicativo de negócios</span><span class="sxs-lookup"><span data-stu-id="6f4e4-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="6f4e4-118">**Notificação de push habilitar Apple** habilitará a notificação por push para o PNCH da Apple para dispositivos executando o iOS da Apple (por exemplo, iPhone, iPad) e usando o Skype para o aplicativo de negócios</span><span class="sxs-lookup"><span data-stu-id="6f4e4-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="6f4e4-p105">Após concluir as edições da política, clique em  **Confirmar** para salvar suas alterações. Se for necessário excluir as alterações feitas, selecione **Cancelar**. Nenhuma alteração será salva na política.</span><span class="sxs-lookup"><span data-stu-id="6f4e4-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

