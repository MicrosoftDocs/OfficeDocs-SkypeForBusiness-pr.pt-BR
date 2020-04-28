---
title: Configurar o bypass de mídia com Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar o bypass de mídia com o roteamento direto do sistema telefônico ao alternar todos os usuários de uma só vez ou implementar uma abordagem em fases (recomendado).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2d6bb25296b7a98e6fea7a59a5dd9406622dbd96
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904833"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="fdb5a-103">Configurar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="fdb5a-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="fdb5a-104">Antes de configurar o bypass de mídia com roteamento direto, certifique-se de ter lido [plano de bypass de mídia com roteamento direto](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="fdb5a-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="fdb5a-105">Para ativar o bypass de mídia, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="fdb5a-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="fdb5a-106">Verifique se o seu fornecedor de Border Border Controller (SBC) de escolha oferece suporte a bypass de mídia e fornece instruções sobre como configurar bypass no SBC.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="fdb5a-107">Consulte a página de certificação para saber mais sobre SBCs, quais são compatíveis com o bypass de mídia e para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="fdb5a-108">Você precisa ativar o bypass de mídia no tronco usando o seguinte comando: **set-CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="fdb5a-109">Verifique se as portas necessárias estão abertas.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="fdb5a-110">Migrar de troncos não ignorados para troncos compatíveis com bypass</span><span class="sxs-lookup"><span data-stu-id="fdb5a-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="fdb5a-111">Você pode alternar todos os usuários de uma só vez ou pode implementar uma abordagem em fases (recomendado).</span><span class="sxs-lookup"><span data-stu-id="fdb5a-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="fdb5a-112">**Alternar todos os usuários de uma só vez.**</span><span class="sxs-lookup"><span data-stu-id="fdb5a-112">**Switch all users at once.**</span></span> <span data-ttu-id="fdb5a-113">Se todas as condições forem atendidas, você poderá ativar o modo de bypass.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="fdb5a-114">No entanto, todos os usuários de produção serão trocados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="fdb5a-115">Como você pode ter alguns problemas inicialmente ao configurar troncos e portas, a experiência do usuário de produção pode ser afetada.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="fdb5a-116">**Abordagem em fases. (Recomendado)**.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="fdb5a-117">Crie um novo tronco para o mesmo SBC (com uma porta diferente), teste-o e altere a política de roteamento de voz online para que os usuários apontem para o novo tronco.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="fdb5a-118">Essa é a abordagem recomendada porque permite uma transição mais suave e uma experiência do usuário ininterrupta.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="fdb5a-119">Essa abordagem requer a configuração do SBC, um novo nome FQDN e a configuração do firewall.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="fdb5a-120">Observação Você precisará verificar se o seu certificado dá suporte a ambos troncos.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="fdb5a-121">Na SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.</span><span class="sxs-lookup"><span data-stu-id="fdb5a-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migrar de troncos não ignorados para troncos compatíveis com bypass)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="fdb5a-123">Para obter instruções sobre como configurar os troncos e executar a migração, consulte a documentação do seu fornecedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="fdb5a-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="fdb5a-124">Documentação de implantação do AudioCodes</span><span class="sxs-lookup"><span data-stu-id="fdb5a-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="fdb5a-125">Documentação de implantação do Oracle</span><span class="sxs-lookup"><span data-stu-id="fdb5a-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="fdb5a-126">Documentação da implantação de comunicações da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="fdb5a-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="fdb5a-127">Documentação de implantação do anynode (File-Systems)</span><span class="sxs-lookup"><span data-stu-id="fdb5a-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="fdb5a-128">Para obter uma lista de controladores de borda de sessão (SBCs) certificados para roteamento direto, consulte [lista de controladores de bordas de sessão certificados para roteamento direto](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="fdb5a-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="fdb5a-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fdb5a-129">Related topics</span></span>

[<span data-ttu-id="fdb5a-130">Ignorar a mídia de plano com roteamento direto</span><span class="sxs-lookup"><span data-stu-id="fdb5a-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



