---
title: Criar ou modificar uma regra de conversão para apresentação de ID do chamador no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Resumo: Saiba como configurar a ID do Chamador usando o Painel de Controle do Skype for Business Server.'
ms.openlocfilehash: 2ffe547927c9f4d6df16a06cc8c95dff9814fc7f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113027"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="8f4be-103">Criar ou modificar uma regra de conversão para apresentação de ID do chamador no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8f4be-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="8f4be-104">**Resumo:** Saiba como configurar a ID do Chamador usando o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8f4be-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="8f4be-105">Com o Skype for Business Server, o número de telefone da parte chamada (ou seja, o número de telefone chamado) pode ser convertido do formato E.164 para o formato de discagem local exigido pelo par de tronco  _(ou_ seja, o gateway associado, o PBX ou o tronco SIP).</span><span class="sxs-lookup"><span data-stu-id="8f4be-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="8f4be-106">Para fazer isso, você deve definir uma ou mais regras de conversão para traduzir o URI de solicitação antes de roteá-lo para o ponto de tronco.</span><span class="sxs-lookup"><span data-stu-id="8f4be-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="8f4be-107">O Skype for Business Server também oferece a opção de também traduzir o número de telefone do chamador (ou seja, o número de telefone do qual o chamador está chamando) do formato E.164 para o formato de discagem local exigido pelo ponto de tronco.</span><span class="sxs-lookup"><span data-stu-id="8f4be-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="8f4be-108">Por exemplo, você pode criar uma regra de conversão para remover +44 do começo de uma sequência de caracteres de discagem e o substituir por 0144.</span><span class="sxs-lookup"><span data-stu-id="8f4be-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8f4be-109">Para configurar a ID do Chamador usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8f4be-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8f4be-110">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8f4be-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="8f4be-111">Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.</span><span class="sxs-lookup"><span data-stu-id="8f4be-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="8f4be-112">Na página **Configuração do** Tronco, clique duas vezes em um tronco existente (por exemplo, o **tronco Global)** para exibir a caixa de diálogo Editar Configuração **do** Tronco.</span><span class="sxs-lookup"><span data-stu-id="8f4be-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="8f4be-113">Para configurar a apresentação da ID do chamador:</span><span class="sxs-lookup"><span data-stu-id="8f4be-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="8f4be-114">Para escolher uma ou mais regras em uma lista de todas as regras de conversão disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="8f4be-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="8f4be-115">Em **Regras de conversão de número de** chamada, clique nas regras que você deseja associar ao tronco e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f4be-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="8f4be-116">Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8f4be-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="8f4be-117">Para obter detalhes sobre como definir uma nova regra, consulte  [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) na documentação de Implantação.</span><span class="sxs-lookup"><span data-stu-id="8f4be-117">For details about defining a new rule, see  [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.</span></span>

   - <span data-ttu-id="8f4be-118">Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="8f4be-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="8f4be-119">Para obter detalhes, consulte [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) na documentação da implantação.</span><span class="sxs-lookup"><span data-stu-id="8f4be-119">For details, see [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.</span></span>

   - <span data-ttu-id="8f4be-120">Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="8f4be-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="8f4be-121">Para obter detalhes, consulte [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).</span><span class="sxs-lookup"><span data-stu-id="8f4be-121">For details, see [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).</span></span>

   - <span data-ttu-id="8f4be-122">Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="8f4be-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="8f4be-123">Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="8f4be-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>