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
description: Saiba como configurar o bypass de mídia com o Roteamento Direto do Sistema de Telefone para o Microsoft Teams, alternando todos os usuários de uma só vez ou implementando um ajuste de fases (recomendado).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416891"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="2feb5-103">Configurar o bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="2feb5-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="2feb5-104">Antes de configurar o bypass de mídia com Roteamento Direto, certifique-se de que você leu o Plano de bypass de [mídia com Roteamento Direto.](direct-routing-plan-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="2feb5-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="2feb5-105">Para ativar o bypass de mídia, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="2feb5-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="2feb5-106">Certifique-se de que o fornecedor de controle de borda de sessão (SBC) de preferência seja compatível com bypass de mídia e fornece instruções sobre como configurar o bypass no SBC.</span><span class="sxs-lookup"><span data-stu-id="2feb5-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="2feb5-107">Consulte a página de certificação para saber mais sobre SBCs, quais são suportados pelo bypass de mídia e para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="2feb5-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="2feb5-108">Você precisa ativar o bypass de mídia no tronco usando o seguinte comando: **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**</span><span class="sxs-lookup"><span data-stu-id="2feb5-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="2feb5-109">Certifique-se de que as portas necessárias sejam abertas.</span><span class="sxs-lookup"><span data-stu-id="2feb5-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="2feb5-110">Migrar de troncos não ignorados para troncos habilitados para bypass</span><span class="sxs-lookup"><span data-stu-id="2feb5-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="2feb5-111">Você pode alternar todos os usuários de uma só vez ou implementar uma fase (recomendada).</span><span class="sxs-lookup"><span data-stu-id="2feb5-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="2feb5-112">**Alternar todos os usuários de uma só vez.**</span><span class="sxs-lookup"><span data-stu-id="2feb5-112">**Switch all users at once.**</span></span> <span data-ttu-id="2feb5-113">Se todas as condições são atendidas, você pode ativar o modo de bypass.</span><span class="sxs-lookup"><span data-stu-id="2feb5-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="2feb5-114">No entanto, todos os seus usuários de produção serão mudados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="2feb5-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="2feb5-115">Como você pode ter alguns problemas inicialmente ao configurar troncos e portas, sua experiência de usuário de produção pode ser afetada.</span><span class="sxs-lookup"><span data-stu-id="2feb5-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="2feb5-116">**Abordagem em fases. (Recomendado)**.</span><span class="sxs-lookup"><span data-stu-id="2feb5-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="2feb5-117">Crie um novo tronco para o mesmo SBC (com uma porta diferente), teste-o e altere a política de roteamento de voz online para que os usuários apontem para o novo tronco.</span><span class="sxs-lookup"><span data-stu-id="2feb5-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="2feb5-118">Essa é a abordagem recomendada porque permite uma transição mais tranquila e uma experiência de usuário ininterrupta.</span><span class="sxs-lookup"><span data-stu-id="2feb5-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="2feb5-119">Essa abordagem requer configuração do SBC, um novo nome FQDN e configuração do firewall.</span><span class="sxs-lookup"><span data-stu-id="2feb5-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="2feb5-120">Observe que você precisará garantir que seu certificado seja compatível com ambos os troncos.</span><span class="sxs-lookup"><span data-stu-id="2feb5-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="2feb5-121">Em SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.</span><span class="sxs-lookup"><span data-stu-id="2feb5-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migrar de troncos não ignorados para troncos habilitados para bypass)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="2feb5-123">Para obter instruções sobre como configurar os troncos e executar a migração, consulte a documentação do seu fornecedor SBC:</span><span class="sxs-lookup"><span data-stu-id="2feb5-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="2feb5-124">Documentação de implantação de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="2feb5-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="2feb5-125">Documentação de implantação oracle</span><span class="sxs-lookup"><span data-stu-id="2feb5-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="2feb5-126">Documentação de implantação de Comunicações da Faixa de Opções</span><span class="sxs-lookup"><span data-stu-id="2feb5-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="2feb5-127">Documentação de implantação do TE-Systems (qualquernode)</span><span class="sxs-lookup"><span data-stu-id="2feb5-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="2feb5-128">Para ver uma lista de SBCs (Controladores de Borda de Sessão) certificados para Roteamento Direto, consulte Lista de Controladores de Rota de Sessão [certificados para Roteamento Direto.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="2feb5-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="2feb5-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2feb5-129">Related topics</span></span>

[<span data-ttu-id="2feb5-130">Planejar bypass de mídia com Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="2feb5-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



