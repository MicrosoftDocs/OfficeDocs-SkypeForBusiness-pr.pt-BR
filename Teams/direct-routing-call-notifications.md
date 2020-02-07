---
title: Roteamento Direto do Sistema de Telefonia
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notificação de chamada de roteamento direto
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 3d53245d241435e869dbdbeb15dcb1c81e18ff96
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837591"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="beb6e-103">Gerenciar notificações de chamadas</span><span class="sxs-lookup"><span data-stu-id="beb6e-103">Manage call notifications</span></span>

<span data-ttu-id="beb6e-104">Este artigo descreve como gerenciar notificações de chamada para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="beb6e-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="beb6e-105">Você pode configurar pontos de extremidade de chamada para as duas equipes e para um PBX ou um controlador de borda de sessão (SBC) ou um controlador de borda de sessão (SBC) de terceiros.</span><span class="sxs-lookup"><span data-stu-id="beb6e-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="beb6e-106">Isso é útil, por exemplo, se você quiser enviar uma chamada para telefones celulares e de mesa de um usuário ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="beb6e-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="beb6e-107">No diagrama a seguir, o usuário Irena tem dois pontos de extremidade:</span><span class="sxs-lookup"><span data-stu-id="beb6e-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="beb6e-108">Um ponto de extremidade do teams</span><span class="sxs-lookup"><span data-stu-id="beb6e-108">A Teams endpoint</span></span>
- <span data-ttu-id="beb6e-109">Um telefone SIP conectado a um SBC de terceiros</span><span class="sxs-lookup"><span data-stu-id="beb6e-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="beb6e-110">Quando chega uma chamada, o SBC bifurca a chamada entre o roteamento direto do sistema telefônico e o SBC de terceiros.</span><span class="sxs-lookup"><span data-stu-id="beb6e-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![Diagrama mostrando pontos de extremidade de equipes bifurcadas](media/direct-routing-call-notification-1.png)

<span data-ttu-id="beb6e-112">Se a chamada for aceita na bifurcação 2 (pelo SBC de terceiros), o Teams irá gerar uma notificação de "chamada perdida".</span><span class="sxs-lookup"><span data-stu-id="beb6e-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="beb6e-113">Você pode impedir a notificação de "chamada perdida" Configurando o SBC para enviar um cancelamento na bifurcação 1 da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="beb6e-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="beb6e-114">MOTIVO: SIP; causa = 200; texto "chamada concluída em outro lugar"</span><span class="sxs-lookup"><span data-stu-id="beb6e-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="beb6e-115">Observe que a chamada não será registrada nos registros de detalhes da chamada do sistema de telefonia da Microsoft como uma chamada bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="beb6e-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="beb6e-116">A chamada será registrada como uma "tentativa" com o código SIP final "487", subcódigo final da Microsoft "540200" e a frase de código SIP final "chamada concluída".</span><span class="sxs-lookup"><span data-stu-id="beb6e-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>   <span data-ttu-id="beb6e-117">(Para exibir os registros de detalhes da chamada, vá para o portal de administração do Teams, análises e relatórios, relatórios de uso e selecione uso de PSTN.)</span><span class="sxs-lookup"><span data-stu-id="beb6e-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="beb6e-118">O diagrama a seguir ilustra a escada SIP para a bifurcação 1, explica o fluxo de chamadas e o motivo esperado na mensagem de cancelamento.</span><span class="sxs-lookup"><span data-stu-id="beb6e-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![Diagrama mostrando pontos de extremidade de equipes bifurcadas](media/direct-routing-call-notification-2.png)
