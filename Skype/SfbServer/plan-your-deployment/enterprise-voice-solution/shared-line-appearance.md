---
title: Planejar aparência de linha compartilhada no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Leia este tópico para saber como planejar a Aparência de Linha Compartilhada (SLA) no Skype for Business Server 2015, atualização cumulativa de novembro de 2015.
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813341"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="864f7-103">Planejar aparência de linha compartilhada no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="864f7-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="864f7-104">Leia este tópico para saber como planejar a Aparência de Linha Compartilhada (SLA) no Skype for Business Server 2015, atualização cumulativa de novembro de 2015.</span><span class="sxs-lookup"><span data-stu-id="864f7-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="864f7-105">A Aparência de Linha Compartilhada é um recurso do Skype for Business para lidar com várias chamadas em um número específico chamado número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="864f7-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="864f7-106">O SLA pode configurar qualquer usuário do Skype for Business habilitado para enterprise voice como um número compartilhado com várias linhas para responder a várias chamadas.</span><span class="sxs-lookup"><span data-stu-id="864f7-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="864f7-107">As chamadas não são realmente recebidas no número compartilhado, em vez disso, são encaminhadas aos usuários que atuam como representantes do número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="864f7-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="864f7-108">Qualquer um dos representantes pode atender a chamada enquanto o restante dos representantes recebe uma notificação no telefone sobre quem a atende e qual linha está ocupada como resultado.</span><span class="sxs-lookup"><span data-stu-id="864f7-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="864f7-109">Tanto o número de linhas quanto os representantes são configuráveis para um número compartilhado no SLA.</span><span class="sxs-lookup"><span data-stu-id="864f7-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="864f7-110">Além disso, opções avançadas, como BusyOption (o que acontece em uma situação quando todas as linhas estão ocupadas) e MissedCallOption (o caso em que nenhum dos representantes atende uma chamada), também podem ser configuradas para um número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="864f7-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="864f7-111">O SLA só tem suporte nos seguintes dispositivos telefônicos (não há suporte para clientes do Skype for Business em computadores, telefones celulares ou outros dispositivos):</span><span class="sxs-lookup"><span data-stu-id="864f7-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="864f7-112">Polycom VVX300 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="864f7-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="864f7-113">Polycom VVX400 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="864f7-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="864f7-114">Polycom VVX500 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="864f7-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="864f7-115">Polycom VVX600 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="864f7-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="864f7-116">O SLA é um novo recurso do Skype for Business Server, atualização cumulativa de novembro de 2015.</span><span class="sxs-lookup"><span data-stu-id="864f7-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="864f7-117">Para obter informações sobre como implantar o SLA, consulte [Deploy Shared Line Appearance in Skype for Business Server 2015.](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)</span><span class="sxs-lookup"><span data-stu-id="864f7-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="864f7-118">Lista de Recursos</span><span class="sxs-lookup"><span data-stu-id="864f7-118">Feature List</span></span>

<span data-ttu-id="864f7-119">A configuração de um grupo SLA permite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="864f7-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="864f7-120">Todos os representantes do grupo podem atender chamadas de entrada para o mesmo número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="864f7-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="864f7-121">As chamadas podem ser baseadas em PSTN ou SIP.</span><span class="sxs-lookup"><span data-stu-id="864f7-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="864f7-122">Os representantes podem segurar e atender chamadas.</span><span class="sxs-lookup"><span data-stu-id="864f7-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="864f7-123">Os representantes podem transferir chamadas para um número fora do grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="864f7-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="864f7-124">Os representantes podem ver quantas chamadas estão atualmente no número compartilhado e exibir o status de cada uma dessas chamadas.</span><span class="sxs-lookup"><span data-stu-id="864f7-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="864f7-125">Você pode configurar um número máximo de chamadas simultâneas para o número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="864f7-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="864f7-126">Você também pode definir como deseja que as chamadas adicionais sejam tratadas depois que esse máximo for atingido.</span><span class="sxs-lookup"><span data-stu-id="864f7-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="864f7-127">Chamadas em excesso podem ser rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou encaminhadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="864f7-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="864f7-128">Você pode configurar como deseja que as chamadas perdidas (chamadas não a escolhidas após um determinado tempo) sejam tratadas.</span><span class="sxs-lookup"><span data-stu-id="864f7-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="864f7-129">Se você habilitar a caixa postal para a identidade do grupo, as chamadas perdidas serão automaticamente para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="864f7-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="864f7-130">Se você não tiver uma caixa postal habilitada para a identidade do grupo (número compartilhado), poderá optar por que as chamadas perdidas sejam rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou desconectadas.</span><span class="sxs-lookup"><span data-stu-id="864f7-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

