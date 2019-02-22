---
title: Planejar Aparência de linha compartilhada no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Leia este tópico para saber como planejar para Shared linha aparência (SLA) no Skype 2015 do servidor de negócios, novembro de 2015 atualizações cumulativas.
ms.openlocfilehash: b65d637426b0a8533089b21021bce566373ca9f1
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "23884505"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="329d7-103">Planejar Aparência de linha compartilhada no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="329d7-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="329d7-104">Leia este tópico para saber como planejar para Shared linha aparência (SLA) no Skype 2015 do servidor de negócios, novembro de 2015 atualizações cumulativas.</span><span class="sxs-lookup"><span data-stu-id="329d7-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="329d7-105">Aparência da linha compartilhado é um recurso do Skype for Business para lidar com várias chamadas em um número específico de um número compartilhado chamado.</span><span class="sxs-lookup"><span data-stu-id="329d7-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="329d7-106">SLA pode configurar qualquer enterprise voice habilitado Skype para comercial do usuário como um número compartilhado com várias linhas para responder a várias chamadas.</span><span class="sxs-lookup"><span data-stu-id="329d7-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="329d7-107">As chamadas não serão realmente recebidas no número compartilhado, em vez disso, elas serão encaminhadas para os usuários que atuam como representantes para o número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="329d7-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="329d7-108">Qualquer um dos representantes pode atender a chamada enquanto o restante dos representantes recebe uma notificação no telefone sobre quem obteve o convite e que linha ficou ocupada como resultado.</span><span class="sxs-lookup"><span data-stu-id="329d7-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="329d7-109">Tanto o número de linhas quanto os representantes são configuráveis para um número compartilhado no SLA.</span><span class="sxs-lookup"><span data-stu-id="329d7-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="329d7-110">Além disso, as opções avançadas, como BusyOption (o que acontece em uma situação quando todas as linhas estão ocupadas) e MissedCallOption (caso em que nenhum dos representantes atende uma chamada), também podem ser configuradas para um número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="329d7-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="329d7-111">SLA tem suporte apenas nos seguintes dispositivos telefônicos (ele não há suporte para Skype para clientes corporativos nos computadores, telefones celulares ou outros dispositivos):</span><span class="sxs-lookup"><span data-stu-id="329d7-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="329d7-112">Polycom VVX300 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="329d7-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="329d7-113">Polycom VVX400 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="329d7-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="329d7-114">Polycom VVX500 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="329d7-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="329d7-115">Polycom VVX600 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="329d7-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="329d7-116">SLA é um novo recurso do Skype para Business Server, novembro de 2015 atualizações cumulativas.</span><span class="sxs-lookup"><span data-stu-id="329d7-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="329d7-117">Para obter informações sobre como implantar o SLA, consulte [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="329d7-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="329d7-118">Lista de recursos</span><span class="sxs-lookup"><span data-stu-id="329d7-118">Feature List</span></span>

<span data-ttu-id="329d7-119">Configuração de um grupo de SLA permite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="329d7-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="329d7-p102">Todos os representantes do grupo podem atender chamadas de entrada para o mesmo número compartilhado. As chamadas podem ser baseadas em PSTN ou em SIP.</span><span class="sxs-lookup"><span data-stu-id="329d7-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="329d7-122">Os representantes podem reter e atender chamadas.</span><span class="sxs-lookup"><span data-stu-id="329d7-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="329d7-123">Os representantes podem transferir chamadas para um número externo do grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="329d7-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="329d7-124">Os representantes podem ver quantas chamadas estão atualmente no número compartilhado e ver o estado de cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="329d7-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="329d7-p103">Você pode configurar um número máximo de chamadas simultâneas para o número compartilhado. Você também pode definir como deseja que as chamadas adicionais sejam manipuladas depois que esse máximo for atingido. As chamadas em excesso podem ser rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou encaminhadas para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="329d7-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="329d7-p104">Você pode configurar como você deseja que as chamadas não atendidas (chamadas não atendidas após um determinado período de tempo) sejam tratadas. Se você ativar o correio de voz para a identidade do grupo, as chamadas não atendidas automaticamente irão para o correio de voz. Se você não tiver correio de voz habilitado para a identidade do grupo (número compartilhado), você poderá escolher que as chamadas perdidas sejam rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou desconectadas.</span><span class="sxs-lookup"><span data-stu-id="329d7-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

