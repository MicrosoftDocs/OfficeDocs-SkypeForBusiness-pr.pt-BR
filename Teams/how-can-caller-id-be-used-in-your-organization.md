---
title: Como a identificação de chamadas pode ser usada em sua organização
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: A ID do chamador pode ser controlada para chamadas de entrada e de saída para usuários Sistema de Telefonia usando uma política chamada CallingLineIdentity.
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723542"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="e6f25-103">Como a identificação de chamadas pode ser usada em sua organização</span><span class="sxs-lookup"><span data-stu-id="e6f25-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="e6f25-104">A ID do chamador consiste em duas informações identificáveis voltadas para o usuário:</span><span class="sxs-lookup"><span data-stu-id="e6f25-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="e6f25-105">Um número de telefone (geralmente chamado de CLID ou ID de linha de chamada).</span><span class="sxs-lookup"><span data-stu-id="e6f25-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="e6f25-106">Este é o PSTN (Número de Telefone Comutado Público) apresentado como a identificação do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6f25-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="e6f25-107">Um nome de parte de chamada (normalmente conhecido como CNAM).</span><span class="sxs-lookup"><span data-stu-id="e6f25-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="e6f25-108">A funcionalidade de ID do chamador está disponível para todos os usuários Sistema de Telefonia independentemente da opção de conectividade PSTN:</span><span class="sxs-lookup"><span data-stu-id="e6f25-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="e6f25-109">Planos de Chamada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6f25-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="e6f25-110">Roteamento Direto do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="e6f25-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="e6f25-111">Você pode controlar a ID do Chamador para chamadas de entrada e de saída usando uma política chamada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="e6f25-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="e6f25-112">Para obter mais informações, consulte Mais sobre a ID da Linha de Chamada [e o Nome da Parte de Chamada.](more-about-calling-line-id-and-calling-party-name.md)</span><span class="sxs-lookup"><span data-stu-id="e6f25-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="e6f25-113">ID do chamador PSTN de saída</span><span class="sxs-lookup"><span data-stu-id="e6f25-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="e6f25-114">Para a ID do chamador PSTN de saída, as opções a seguir estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e6f25-114">For the outbound PSTN caller ID, the following options are available.</span></span> 
  
- <span data-ttu-id="e6f25-115">O número de telefone atribuído ao usuário, que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="e6f25-115">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="e6f25-116">Anônimo, que está disponível removendo a apresentação do número PSTN do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6f25-116">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="e6f25-117">Um número de telefone substituto, que pode ser:</span><span class="sxs-lookup"><span data-stu-id="e6f25-117">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="e6f25-118">Um número de telefone que é classificado como um número de serviço e de chamada gratuita no inventário de números de telefone de Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="e6f25-118">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="e6f25-119">Normalmente, ele é atribuído a um Teams Atendedor Automático ou Fila de Chamada.</span><span class="sxs-lookup"><span data-stu-id="e6f25-119">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="e6f25-120">Um número de telefone local por meio do Roteamento Direto atribuído a uma conta de recurso usada por um Teams Atendedor Automático ou Fila de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="e6f25-120">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="e6f25-121">O Nome da Parte de Chamada ou CNAM definido na chamada PSTN de saída.</span><span class="sxs-lookup"><span data-stu-id="e6f25-121">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="e6f25-122">Para obter mais informações, consulte [Definir a ID do Chamador para um usuário](./set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="e6f25-122">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="e6f25-123">Controle do usuário final da ID do chamador de saída</span><span class="sxs-lookup"><span data-stu-id="e6f25-123">End user control of outbound caller ID</span></span>

<span data-ttu-id="e6f25-124">Os usuários podem alterar a configuração de ID do chamador como **Anônimo** definindo o atributo EnableUserOverride.</span><span class="sxs-lookup"><span data-stu-id="e6f25-124">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="e6f25-125">Se a ID do chamador de saída estiver definida como Anônima, EnableUserOverride não terá efeito e a ID do chamador será sempre definida como Anônima.</span><span class="sxs-lookup"><span data-stu-id="e6f25-125">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="e6f25-126">O valor padrão do EnableUserOverride é False.</span><span class="sxs-lookup"><span data-stu-id="e6f25-126">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="e6f25-127">Os usuários finais podem definir **a** ID do chamador como Anônimo indo para Chamadas Configurações > e, em Seguida, em **ID** do Chamador, selecione Ocultar o número de telefone e informações de perfil para todas as **chamadas**.</span><span class="sxs-lookup"><span data-stu-id="e6f25-127">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="e6f25-128">Observações</span><span class="sxs-lookup"><span data-stu-id="e6f25-128">Notes</span></span>

<span data-ttu-id="e6f25-129">Considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6f25-129">Keep the following in mind:</span></span>

- <span data-ttu-id="e6f25-130">Não é possível atribuir os seguintes tipos de números de telefone para a ID do chamador de saída:</span><span class="sxs-lookup"><span data-stu-id="e6f25-130">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="e6f25-131">Qualquer número de telefone que seja classificado como um usuário no inventário de números de telefone de Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="e6f25-131">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="e6f25-132">Qualquer número de telefone local por meio de Roteamento Direto atribuído a um usuário.</span><span class="sxs-lookup"><span data-stu-id="e6f25-132">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="e6f25-133">Um Skype for Business Server número de telefone local.</span><span class="sxs-lookup"><span data-stu-id="e6f25-133">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="e6f25-134">O uso da substituição de número de telefone da conta de recurso só funciona para Teams usuários.</span><span class="sxs-lookup"><span data-stu-id="e6f25-134">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="e6f25-135">A substituição do número de telefone de serviço funciona para usuários Skype for Business Online e Teams.</span><span class="sxs-lookup"><span data-stu-id="e6f25-135">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="e6f25-136">O Nome da Parte de Chamada só é enviado em chamadas nas quais a ID do chamador é substituída por LineUri, um número de telefone de conta de recurso ou serviço e quando o chamador é um usuário Teams.</span><span class="sxs-lookup"><span data-stu-id="e6f25-136">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="e6f25-137">Chamar Nome da Parte pode ter no máximo 200 caracteres, mas sistemas downstream podem suportar menos caracteres.</span><span class="sxs-lookup"><span data-stu-id="e6f25-137">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="e6f25-138">Para Roteamento Direto, a substituição de número de telefone e o Nome da Parte de Chamada é enviada no header SIP FROM.</span><span class="sxs-lookup"><span data-stu-id="e6f25-138">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="e6f25-139">Se o OnlinePstnGateway correspondente estiver configurado com ForwardPai = True, o header SIP P-ASSERTED-IDENTITY conterá o usuário de chamada real.</span><span class="sxs-lookup"><span data-stu-id="e6f25-139">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="e6f25-140">EnableUserOverride tem precedência sobre outras configurações na política, a menos que a substituição seja definida como Anônima.</span><span class="sxs-lookup"><span data-stu-id="e6f25-140">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="e6f25-141">Por exemplo, suponha que a instância de política tenha substituição usando uma conta de recurso e EnableUserOverride seja definida e habilitada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="e6f25-141">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="e6f25-142">Nesse caso, a ID do chamador de saída será bloqueada e Anonymous será usado.</span><span class="sxs-lookup"><span data-stu-id="e6f25-142">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="e6f25-143">Se uma instância de política tiver a substituição definida como Anonymous e EnableUserOverride estiver definida, a ID do chamador de saída sempre será Anônima, independentemente da configuração do usuário final.</span><span class="sxs-lookup"><span data-stu-id="e6f25-143">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="e6f25-144">ID do chamador de entrada</span><span class="sxs-lookup"><span data-stu-id="e6f25-144">Inbound caller ID</span></span>

<span data-ttu-id="e6f25-145">Sistema de Telefonia mostrará o número de telefone externo de entrada como a ID do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6f25-145">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="e6f25-146">Se o número estiver associado a um usuário ou contato no Azure AD ou a um contato pessoal, os clientes Skype for Business e Teams mostrarão a ID do chamador com base nessa informação.</span><span class="sxs-lookup"><span data-stu-id="e6f25-146">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="e6f25-147">Se o número de telefone não estiver no Azure AD ou em um contato pessoal, o nome de exibição fornecido por telco será mostrado se ele estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="e6f25-147">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="e6f25-148">O atributo BlockIncomingCallerID permite o bloqueio da identificação de chamada nas chamadas PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="e6f25-148">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="e6f25-149">Você pode definir esse atributo, mas ele não está disponível para os usuários finais na página de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6f25-149">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="e6f25-150">Quando essa configuração estiver habilitada, o chamador PSTN de entrada será exibido como proveniente do Anonymous.</span><span class="sxs-lookup"><span data-stu-id="e6f25-150">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="e6f25-151">Para bloquear a ID do chamador de entrada, consulte Definir a [ID do Chamador para um usuário](./set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="e6f25-151">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e6f25-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e6f25-152">Related topics</span></span>
[<span data-ttu-id="e6f25-153">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="e6f25-153">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="e6f25-154">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="e6f25-154">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="e6f25-155">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="e6f25-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="e6f25-156">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="e6f25-156">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="e6f25-157">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="e6f25-157">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
