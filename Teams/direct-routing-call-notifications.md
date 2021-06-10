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
description: Notificação de chamada de Roteamento Direto
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341800"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="97a27-103">Gerenciar notificações de chamadas</span><span class="sxs-lookup"><span data-stu-id="97a27-103">Manage call notifications</span></span>

<span data-ttu-id="97a27-104">Este artigo descreve como gerenciar notificações de chamada para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="97a27-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="97a27-105">Você pode configurar pontos de extremidade de chamada para Teams e para um PbX (Private Branch Exchange) de terceiros ou Controlador de Borda de Sessão (SBC).</span><span class="sxs-lookup"><span data-stu-id="97a27-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="97a27-106">Isso é útil, por exemplo, se você quiser enviar uma chamada para os telefones móveis e de mesa de um usuário ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="97a27-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="97a27-107">No diagrama a seguir, a Irena do usuário tem dois pontos de extremidade:</span><span class="sxs-lookup"><span data-stu-id="97a27-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="97a27-108">Um Teams ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="97a27-108">A Teams endpoint</span></span>
- <span data-ttu-id="97a27-109">Um telefone SIP conectado a um SBC de terceiros</span><span class="sxs-lookup"><span data-stu-id="97a27-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="97a27-110">Quando uma chamada chega, o SBC bifurca a chamada entre Sistema de Telefonia Roteamento Direto e o SBC de terceiros.</span><span class="sxs-lookup"><span data-stu-id="97a27-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![Diagrama mostrando pontos Teams pontos de extremidade bifurcados](media/direct-routing-call-notification-1.png)

<span data-ttu-id="97a27-112">Se a chamada for aceita no Fork 2 (pelo SBC de terceiros), Teams gerará uma notificação de "Chamada Perdida".</span><span class="sxs-lookup"><span data-stu-id="97a27-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="97a27-113">Você pode impedir a notificação de "Chamada Perdida" configurando o SBC para enviar um Cancelamento no Bifurcação 1 da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="97a27-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="97a27-114">MOTIVO: SIP; cause=200;text"Call completed elsewhere"</span><span class="sxs-lookup"><span data-stu-id="97a27-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="97a27-115">Observe que a chamada não será registrada nos registros de detalhes de chamada do Telefone Microsoft System como uma chamada bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="97a27-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="97a27-116">A chamada será registrada como uma "Tentativa" com o Código SIP Final "487", o subcodigo final da Microsoft "540200" e a frase de código SIP final "Chamada concluída em outro lugar".</span><span class="sxs-lookup"><span data-stu-id="97a27-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>  <span data-ttu-id="97a27-117">(Para exibir os registros de detalhes da chamada, acesse o portal de administração do Teams, Análise e Relatórios, Relatórios de Uso e selecione Uso de PSTN.)</span><span class="sxs-lookup"><span data-stu-id="97a27-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="97a27-118">O diagrama a seguir ilustra a escala SIP do Fork 1, explica o fluxo de chamada e o MOTIVO esperado na mensagem Cancelar.</span><span class="sxs-lookup"><span data-stu-id="97a27-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![Diagrama mostrando pontos Teams pontos de extremidade bifurcados](media/direct-routing-call-notification-2.png)
