---
title: Mobile Client Create or Edit Push Notification Configuration
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: A Notificação por Push e o Push Notification Clearing House (PNCH) são duas partes importantes do recurso de mobilidade. Notificação por push é o processo em que uma mensagem é enviada para o PNCH. A mensagem é mantida aqui até que possa ser entregue ao cliente móvel ou o período de tempo de expiração.
ms.openlocfilehash: 3c72c5b123a906d74cfeb0a1fef5c1e765fe030c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808741"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="e7454-105">Cliente Móvel: Crie ou Edite a Configuração de Notificação por Push</span><span class="sxs-lookup"><span data-stu-id="e7454-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="e7454-106">A Notificação por Push e o Push Notification Clearing House (PNCH) são duas partes importantes do recurso de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="e7454-106">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature.</span></span> <span data-ttu-id="e7454-107">Notificação por push é o processo em que uma mensagem é enviada para o PNCH.</span><span class="sxs-lookup"><span data-stu-id="e7454-107">Push notification is the process where a message is sent to the PNCH.</span></span> <span data-ttu-id="e7454-108">A mensagem é mantida aqui até que possa ser entregue ao cliente móvel ou o período de tempo de expiração.</span><span class="sxs-lookup"><span data-stu-id="e7454-108">The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e7454-109">O período de tempo é definido na Push Notification Clearing House e não é configurável pelo usuário ou pelo administrador da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="e7454-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="e7454-110">Para habilitar a Notificação por Push, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e7454-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="e7454-111">**Escopo:** Observe o escopo dessa política.</span><span class="sxs-lookup"><span data-stu-id="e7454-111">**Scope:** Note the scope for this policy.</span></span> <span data-ttu-id="e7454-112">Pode ser **Global**, que se aplica a todos os usuários nesta implantação, ou **Site**, que é apenas os usuários atribuídos aos servidores home no site especificado.</span><span class="sxs-lookup"><span data-stu-id="e7454-112">It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7454-113">As configurações de política aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="e7454-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="e7454-114">A precedência da política é: a política de usuário (mais influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (menos influência).</span><span class="sxs-lookup"><span data-stu-id="e7454-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="e7454-115">Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="e7454-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="e7454-116">Selecione quais serviços de notificação por push você deseja habilitar clicando na caixa de seleção para:</span><span class="sxs-lookup"><span data-stu-id="e7454-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="e7454-117">**Habilitar a notificação por push** da Microsoft habilita a notificação por push para o PNCH baseado em nuvem para Windows Phone com o aplicativo Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e7454-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="e7454-118">**Habilitar** a notificação por push da Apple habilita a notificação por push para o Apple PNCH para dispositivos que executam o iOS da Apple (por exemplo, iPhone, iPad) e usando o aplicativo Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e7454-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="e7454-119">Depois de concluir as edições da política, clique em **Confirmação** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="e7454-119">When you have completed the edits of the policy, click **Commit** to save your changes.</span></span> <span data-ttu-id="e7454-120">Se você precisar excluir as alterações feitas, selecione **Cancelar.**</span><span class="sxs-lookup"><span data-stu-id="e7454-120">If you need to delete the changes you have made, select **Cancel**.</span></span> <span data-ttu-id="e7454-121">Nenhuma alteração será salva na política.</span><span class="sxs-lookup"><span data-stu-id="e7454-121">No changes will be saved to the policy.</span></span>
    

