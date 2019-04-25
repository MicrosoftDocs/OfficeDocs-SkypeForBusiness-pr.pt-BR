---
title: Configurar o bypass de mídia com Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Leia este tópico para saber como configurar o bypass de mídia com roteamento direto de sistema do telefone.
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232687"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="bef54-103">Configurar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="bef54-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="bef54-104">Antes de o bypass de mídia configurando com o roteamento direto, certifique-se de que você leu [Plan for media bypass com o roteamento direto](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="bef54-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="bef54-105">Para ativar o desvio de mídia, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="bef54-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="bef54-106">Certifique-se de que o seu fornecedor de controlador de borda de sessão (SBC) de escolha suporta bypass de mídia e fornece instruções sobre como configurar o desvio no SBC.</span><span class="sxs-lookup"><span data-stu-id="bef54-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="bef54-107">Consulte a página de certificação para saber mais sobre SBCs, bypass de mídia de suporte que aquelas, e para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="bef54-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="bef54-108">Você precisa ativar o bypass de mídia no tronco usando o seguinte comando: **Set-CSOnlinePSTNGateway-Identity <sbc_FQDN> - MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="bef54-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="bef54-109">Certifique-se de que as portas necessárias sejam abertas.</span><span class="sxs-lookup"><span data-stu-id="bef54-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="bef54-110">Migrar do troncos não desviada para troncos desvio habilitado</span><span class="sxs-lookup"><span data-stu-id="bef54-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="bef54-111">Você pode alternar todos os usuários ao mesmo tempo ou você pode implementar fases abordadas (recomendado).</span><span class="sxs-lookup"><span data-stu-id="bef54-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="bef54-112">**Alterne a todos os usuários ao mesmo tempo.**</span><span class="sxs-lookup"><span data-stu-id="bef54-112">**Switch all users at once.**</span></span> <span data-ttu-id="bef54-113">Se todas as condições forem atendidas, você pode ativar o modo de desvio.</span><span class="sxs-lookup"><span data-stu-id="bef54-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="bef54-114">No entanto, todos os usuários de produção serão transferidos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="bef54-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="bef54-115">Porque você pode sofrer alguns problemas inicialmente quando você configura troncos e portas, sua experiência do usuário de produção pode ser afetada.</span><span class="sxs-lookup"><span data-stu-id="bef54-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="bef54-116">Abordagem **Phased. (Recomendado)**.</span><span class="sxs-lookup"><span data-stu-id="bef54-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="bef54-117">Criar um novo tronco para o mesmo SBC (com uma porta diferente), testá-lo e alterar a política de roteamento de voz online para os usuários apontar para o novo tronco.</span><span class="sxs-lookup"><span data-stu-id="bef54-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="bef54-118">Esta é a abordagem recomendada porque ela permite para uma transição mais suave e a experiência do usuário ininterrupto.</span><span class="sxs-lookup"><span data-stu-id="bef54-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="bef54-119">Essa abordagem exige a configuração do SBC, um novo nome FQDN e a configuração do firewall.</span><span class="sxs-lookup"><span data-stu-id="bef54-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="bef54-120">Observe que você precisará certificar-se de que seu certificado suporta ambos os troncos.</span><span class="sxs-lookup"><span data-stu-id="bef54-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="bef54-121">Em SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.</span><span class="sxs-lookup"><span data-stu-id="bef54-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migrar do troncos não desviada para o desvio habilitado troncos)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="bef54-123">Para obter instruções sobre como configurar os troncos e realizar a migração, consulte a documentação do seu fornecedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="bef54-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- <span data-ttu-id="bef54-124">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="bef54-124">AudioCodes</span></span>
- <span data-ttu-id="bef54-125">Faixa de opções</span><span class="sxs-lookup"><span data-stu-id="bef54-125">Ribbon</span></span>
- <span data-ttu-id="bef54-126">TE-Systems (AnyNode)</span><span class="sxs-lookup"><span data-stu-id="bef54-126">TE-Systems (AnyNode)</span></span>    

<span data-ttu-id="bef54-127">Para obter uma lista de controladores de borda de sessão (SBCs) certificados para o roteamento direta, consulte a [lista de controladores de Broder sessão certified para roteamento direto](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="bef54-127">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="bef54-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="bef54-128">See also</span></span>

[<span data-ttu-id="bef54-129">Planejar o bypass de mídia com o roteamento direto</span><span class="sxs-lookup"><span data-stu-id="bef54-129">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



