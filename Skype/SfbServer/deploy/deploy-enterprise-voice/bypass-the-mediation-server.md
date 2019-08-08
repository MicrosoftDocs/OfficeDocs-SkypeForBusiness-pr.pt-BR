---
title: Configurar o bypass de mídia no Skype for Business Server para sempre ignorar o servidor de mediação
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilite o bypass de mídia para sempre ignorar o servidor de mediação no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: dfffda1130fc1fb119e6cbf5d9b12af766b9c038
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233834"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="e6bb9-103">Configurar o bypass de mídia no Skype for Business Server para sempre ignorar o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="e6bb9-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="e6bb9-104">Habilite o bypass de mídia para sempre ignorar o servidor de mediação no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="e6bb9-105">Se você usar as etapas neste tópico para definir configurações globais para bypass de mídia, pressupõe-se que você tenha uma boa conectividade entre pontos de extremidade do Skype for Business e qualquer ponto para o qual você configurou a mídia ignorada na conexão do tronco.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="e6bb9-106">Se você não tiver uma boa conectividade entre os pontos de extremidade do Skype for Business e todos os pares do servidor de mediação cujas conexões de tronco foram habilitadas para bypass de mídia, você deve configurar as definições de bypass de mídia global para usar as informações do site e da região ao empregar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="e6bb9-107">Isso permite que você tenha mais controle ao determinar quando a mídia ignora o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="e6bb9-108">Para fazer isso, use as etapas em [configurar as configurações globais do bypass de mídia no Skype for Business Server para usar as informações de site e região](use-site-and-region-information.md) e [associar uma sub-rede a um site de rede](deploy-network.md#BKMK_AssociateSubnets) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="e6bb9-109">Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="e6bb9-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="e6bb9-110">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="e6bb9-111">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="e6bb9-112">Clique duas vezes na configuração **Global** na lista.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="e6bb9-113">Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="e6bb9-114">Clique em **Sempre desviar**.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="e6bb9-115">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e6bb9-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="e6bb9-116">See also</span></span>

[<span data-ttu-id="e6bb9-117">Planejar a bypass de mídia no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e6bb9-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="e6bb9-118">Implantar bypass de mídia no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e6bb9-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

