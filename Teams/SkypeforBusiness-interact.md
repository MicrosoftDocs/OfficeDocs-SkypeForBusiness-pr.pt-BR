---
title: Como o Skype for Business e o Microsoft Teams interagem | Suporte da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: Saiba como o Skype for Business e o Microsoft Teams interagem, de bate-papos a chamadas.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 02d11632a0a6b8f78504ab20ae3415a942e6c91f
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a><span data-ttu-id="ad841-103">Como o Skype for Business e o Microsoft Teams interagem</span><span class="sxs-lookup"><span data-stu-id="ad841-103">How Skype for Business and Microsoft Teams interact</span></span>
===================================================

<span data-ttu-id="ad841-104">Se a sua empresa usa o Skype for Business hoje, é importante entender como Skype for Business e o Microsoft Teams vão interagir.</span><span class="sxs-lookup"><span data-stu-id="ad841-104">If your organization uses Skype for Business today, it is important to understand how Skype for Business and Microsoft Teams will interact.</span></span>

<span data-ttu-id="ad841-105">Na disponibilidade geral do Microsoft Teams, a interoperabilidade básica entre o Microsoft Teams e o Skype for Business on-line ou híbrida está disponível apenas para mensagens instantâneas ponto a ponto (P2P).</span><span class="sxs-lookup"><span data-stu-id="ad841-105">At general availability of Microsoft Teams, basic interoperability between Microsoft Teams and Skype for Business Online or Hybrid is available peer to peer (P2P) instant messaging only.</span></span>

<span data-ttu-id="ad841-106">O comportamento padrão é que o cliente Microsoft Teams acessará os serviços de back-end do Microsoft Teams e os serviços do Skype for Business (uma abordagem de pilha dupla).</span><span class="sxs-lookup"><span data-stu-id="ad841-106">The default behavior is that the Microsoft Teams client will sign into both the Microsoft Teams backend services and the Skype for Business services (a dual-stack approach).</span></span> <span data-ttu-id="ad841-107">O cliente Microsoft Teams apresentará apenas recursos de MI para o Skype for Business; assim, buscar um usuário do Microsoft Teams a partir do Skype for Business somente indicará o usuário como Apenas MI – no exemplo abaixo, Alix Wilber está acessando apenas o cliente Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ad841-107">The Microsoft Teams client will only present IM capabilities to Skype for Business, so looking up a Microsoft Teams user from Skype for Business will only indicate the user as IM Only – shown in the example below, Alix Wilber is only signed into the Microsoft Teams client.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

<span data-ttu-id="ad841-108">No Microsoft Teams, o usuário pode procurar outros usuários da sua empresa que estejam habilitados no momento somente para o Skype for Business e realizar sessões de bate-papo por mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="ad841-108">From Microsoft Teams, users can search for other users within their organization who are currently only enabled for Skype for Business, and conduct instant messaging chat sessions.</span></span>

<span data-ttu-id="ad841-109">No Skype for Business, os usuários podem responder as mensagens instantâneas, que chegarão na janela de bate-papo do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ad841-109">Users on Skype for Business can reply to the instant messages, which will arrive in Microsoft Teams’ chat window.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

<span data-ttu-id="ad841-110">No Microsoft Teams, se também habilitados para o Skype for Business, os usuários podem iniciar sessão no Microsoft Teams e no Skype for Business usando seus respectivos clientes simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="ad841-110">Users on Microsoft Teams, if enabled for Skype for Business as well, can sign in to Microsoft Teams and Skype for Business using their own respective clients simultaneously.</span></span>

<span data-ttu-id="ad841-111">O ponto de extremidade com atividade mais recente terá preferência, então se o usuário estiver usando o Microsoft Teams ativamente, todas as mensagens instantâneas enviadas por um usuário do Skype for Business chegarão na janela de bate-papo do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ad841-111">The last active endpoint will be honored, so if the user is actively using Microsoft Teams, any instant messages sent from a Skype for Business user will arrive in the Microsoft Teams chat window.</span></span> <span data-ttu-id="ad841-112">Se o usuário estiver, no momento, usando o Skype for Business para receber/fazer chamadas telefônicas, ou se tiver acabado de atender a uma chamada usando o Skype for Business e não tiver retornado ao cliente Microsoft Teams, as mensagens instantâneas enviadas por um usuário do Skype for Business chegarão no cliente Skype for Business, pois será esse o ponto de extremidade com atividade mais recente.</span><span class="sxs-lookup"><span data-stu-id="ad841-112">If the user is currently using Skype for Business to receive/make phone calls or just finished taking a call using Skype for Business, and have not returned to Microsoft Teams client, incoming instant messages sent from a Skype for Business user will arrive in Skype for Business client as this will be the most active endpoint.</span></span>

<span data-ttu-id="ad841-113">Como o Microsoft Teams suporta no momento apenas interoperabilidade de mensagens instantâneas de ponto a ponto (P2P) com o Skype for Business, todas as chamadas de áudio/vídeo e todos os convites para entrar em reuniões Skype for Business de qualquer modalidade, de qualquer usuário Skype for Business, chegarão apenas no cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ad841-113">As Microsoft Teams only currently supports peer-to-peer (P2P) instant messaging interop between Skype for Business, any audio/video calls or invitation to join a Skype for Business meetings, for any modalities, from other Skype for Business users will arrive on the Skype for Business client only.</span></span> <span data-ttu-id="ad841-114">E o inverso, todas as chamadas de áudio/vídeo e todos os convites para entrar em chamadas de grupo de qualquer modalidade, de um cliente Microsoft Teams, chegarão apenas no cliente Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ad841-114">In the reverse, any audio/video calls or invitation to join group calling, for any modalities from Microsoft Teams client, will only arrive on the Microsoft Teams client.</span></span>

<span data-ttu-id="ad841-115">Com o comportamento acima, os usuários finais podem usar confortavelmente o Microsoft Teams e o Skype for Business ao mesmo tempo, e lidar com as necessidades específicas de comunicação usando a ferramenta correta.</span><span class="sxs-lookup"><span data-stu-id="ad841-115">With the above behavior, end users can comfortably use both Microsoft Teams and Skype for Business at the same time, and handle specific communications needs using the right tool.</span></span> <span data-ttu-id="ad841-116">No entanto, pode ser necessário o conhecimento adequado do usuário final para entender como a interoperabilidade funciona e como ela pode afetar a experiência do usuário final.</span><span class="sxs-lookup"><span data-stu-id="ad841-116">However, proper end user awareness may be required to understand how interoperability works and how it may impact end user experience.</span></span>


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br><span data-ttu-id="ad841-117">Nota</span><span class="sxs-lookup"><span data-stu-id="ad841-117">Note:</span></span></br>      |<span data-ttu-id="ad841-118">Com a interoperabilidade do Skype for Business, as mensagens instantâneas que chegarem no Teams não ficarão registradas no histórico de conversas do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ad841-118">With Skype for Business interoperability, instant messages that arrive in Teams will not be recorded in Skype for Business conversation history.</span></span>         |

<span data-ttu-id="ad841-119">O Microsoft Teams oferece aos usuários a habilidade de desabilitar a interoperabilidade do Skype for Business nas configurações de Notificações.</span><span class="sxs-lookup"><span data-stu-id="ad841-119">Microsoft Teams provides the ability for users to disable Skype for Business interoperability from within the Notification settings.</span></span> <span data-ttu-id="ad841-120">Essa configuração é controlada pelo usuário, permitindo que cada um decida o comportamento de preferência.</span><span class="sxs-lookup"><span data-stu-id="ad841-120">This setting is user controlled, allowing each user to decide on the behavior they prefer.</span></span>
