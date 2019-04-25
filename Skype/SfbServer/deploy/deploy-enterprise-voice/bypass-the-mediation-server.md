---
title: Configurar o bypass de mídia no Skype para Business Server para sempre ignorar o servidor de mediação
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilite bypass de mídia para sempre ignorar o servidor de mediação no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 31ecb80df342ac68ba6bb28b20248648bd5808c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223772"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="289e2-103">Configurar o bypass de mídia no Skype para Business Server para sempre ignorar o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="289e2-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="289e2-104">Habilite bypass de mídia para sempre ignorar o servidor de mediação no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="289e2-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="289e2-105">Se você usar as etapas deste tópico para definir as configurações globais para o media bypass, pressupõe-se que você tem boa conectividade entre Skype para pontos de extremidade de negócios e qualquer ponto para o qual você configurou o desvio de mídia na conexão do tronco.</span><span class="sxs-lookup"><span data-stu-id="289e2-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="289e2-106">Se você não tem boa conectividade entre Skype para pontos de extremidade de negócios e todos os pares para o servidor de mediação cujas conexões de tronco respectivos tiverem sido habilitados para bypass de mídia, você deve configurar as definições de desvio de mídia global para usar as informações do site e da região Quando desvio de mídia empregando.</span><span class="sxs-lookup"><span data-stu-id="289e2-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="289e2-107">Isso permite que mais controle na determinação quando a mídia ignora o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="289e2-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="289e2-108">Para fazer isso, use as etapas em [configurações globais no Skype para Business Server usem informações de site e a região de bypass de mídia de configurar](use-site-and-region-information.md) e [associar uma sub-rede a um site de rede](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="289e2-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="289e2-109">Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="289e2-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="289e2-110">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="289e2-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="289e2-111">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="289e2-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="289e2-112">Clique duas vezes na configuração **Global** na lista.</span><span class="sxs-lookup"><span data-stu-id="289e2-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="289e2-113">Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.</span><span class="sxs-lookup"><span data-stu-id="289e2-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="289e2-114">Clique em **Sempre desviar**.</span><span class="sxs-lookup"><span data-stu-id="289e2-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="289e2-115">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="289e2-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="289e2-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="289e2-116">See also</span></span>

[<span data-ttu-id="289e2-117">Planejar o bypass de mídia no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="289e2-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="289e2-118">Implantar o bypass de mídia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="289e2-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

