---
title: Como a identificação de chamadas pode ser usada em sua organização
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
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
description: A identificação de chamadas pode ser controlada para chamadas de entrada e de saída para usuários do sistema telefônico usando uma política chamada CallingLineIdentity.
ms.openlocfilehash: 2547e6ca3aed10d112897aa1b24900a479c5c8ef
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224204"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="66e7f-103">Como a identificação de chamadas pode ser usada em sua organização</span><span class="sxs-lookup"><span data-stu-id="66e7f-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="66e7f-104">A identificação de chamadas pode ser controlada para chamadas de entrada e de saída para usuários do sistema telefônico usando uma política chamada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="66e7f-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="66e7f-105">A funcionalidade de identificação de chamadas está disponível para todos os usuários do sistema telefônico independentemente da conectividade PSTN:</span><span class="sxs-lookup"><span data-stu-id="66e7f-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="66e7f-106">Conectividade PSTN Online</span><span class="sxs-lookup"><span data-stu-id="66e7f-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="66e7f-107">Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)</span><span class="sxs-lookup"><span data-stu-id="66e7f-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="66e7f-108">Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)</span><span class="sxs-lookup"><span data-stu-id="66e7f-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="66e7f-109">[!OBSERVAçãO] Esta política não está disponível no Skype for Business 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="66e7f-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="66e7f-110">Identificação de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="66e7f-110">Outbound caller ID</span></span>

<span data-ttu-id="66e7f-111">Há três opções disponíveis para a identificação de chamadas PSTN de saída:</span><span class="sxs-lookup"><span data-stu-id="66e7f-111">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="66e7f-112">O número de telefone atribuído ao usuário, que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="66e7f-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="66e7f-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="66e7f-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="66e7f-115">Definido como anônimo.</span><span class="sxs-lookup"><span data-stu-id="66e7f-115">Set to anonymous.</span></span>
    
<span data-ttu-id="66e7f-116">No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamada de saída:</span><span class="sxs-lookup"><span data-stu-id="66e7f-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="66e7f-117">Qualquer número de telefone classificado como um *usuário* em seu plano de número de telefone de planos de chamadas</span><span class="sxs-lookup"><span data-stu-id="66e7f-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="66e7f-118">Um número de telefone local do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="66e7f-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="66e7f-119">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="66e7f-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="66e7f-120">Controle do usuário final da identificação de chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="66e7f-120">End user control of outbound caller ID</span></span>

<span data-ttu-id="66e7f-p102">O atributo EnableUserOverride permite que um ou vários usuários alterem a configuração de identificação de chamadas para **anônima**. Isso só se aplica quando uma política CallingLineIdentity é configurada com um parâmetro CallingIDSubstitute de LineURI ou substituto. O valor padrão de EnableUserOverride é false.</span><span class="sxs-lookup"><span data-stu-id="66e7f-p102">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="66e7f-124">Seus usuários finais podem definir a identificação de chamadas como **anônimas** usando a guia **configurações** no cliente da área de trabalho do Skype for Business, selecione **chamadas para um usuário final** (se habilitada por administrador) e selecione **ocultar meu número de telefone e informações de perfil para todas as chamadas**.</span><span class="sxs-lookup"><span data-stu-id="66e7f-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="66e7f-125">No Teams, os usuários podem acessar a imagem do perfil no canto superior direito, selecionar **configurações**  >  de**chamadas**e, em seguida, em **identificação de chamadas**, selecionar **ocultar meu número de telefone e informações de perfil para todas as chamadas**.</span><span class="sxs-lookup"><span data-stu-id="66e7f-125">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="66e7f-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="66e7f-126">**Windows**</span></span> <br/> |<span data-ttu-id="66e7f-127">**Versão**</span><span class="sxs-lookup"><span data-stu-id="66e7f-127">**Version**</span></span> <br/> |<span data-ttu-id="66e7f-128">**Compatível**</span><span class="sxs-lookup"><span data-stu-id="66e7f-128">**Supported**</span></span> <br/> |
|<span data-ttu-id="66e7f-129">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="66e7f-129">Click-to-Run</span></span>  <br/> |<span data-ttu-id="66e7f-130">CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="66e7f-130">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="66e7f-131">Sim</span><span class="sxs-lookup"><span data-stu-id="66e7f-131">Yes</span></span>  <br/> |
|<span data-ttu-id="66e7f-132">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="66e7f-132">Click-to-Run</span></span>  <br/> |<span data-ttu-id="66e7f-133">CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="66e7f-133">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="66e7f-134">Sim</span><span class="sxs-lookup"><span data-stu-id="66e7f-134">Yes</span></span>  <br/> |
|<span data-ttu-id="66e7f-135">Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="66e7f-135">Click-to-Run</span></span>  <br/> |<span data-ttu-id="66e7f-136">Canal Adiado lançado em 13 de junho de 2017 - versão 1701 (Compilação 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="66e7f-136">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="66e7f-137">Sim</span><span class="sxs-lookup"><span data-stu-id="66e7f-137">Yes</span></span>  <br/> |
|<span data-ttu-id="66e7f-138">MSI</span><span class="sxs-lookup"><span data-stu-id="66e7f-138">MSI</span></span>  <br/> |<span data-ttu-id="66e7f-139">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="66e7f-139">Skype for Business</span></span>  <br/> |<span data-ttu-id="66e7f-140">Não</span><span class="sxs-lookup"><span data-stu-id="66e7f-140">No</span></span>  <br/> |
|<span data-ttu-id="66e7f-141">Mac</span><span class="sxs-lookup"><span data-stu-id="66e7f-141">Mac</span></span>  <br/> |<span data-ttu-id="66e7f-142">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="66e7f-142">Skype for Business</span></span>  <br/> |<span data-ttu-id="66e7f-143">Não</span><span class="sxs-lookup"><span data-stu-id="66e7f-143">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="66e7f-144">IDENTIFICAÇÃO de chamada de entrada</span><span class="sxs-lookup"><span data-stu-id="66e7f-144">Inbound caller ID</span></span>

<span data-ttu-id="66e7f-145">O sistema de telefonia mostrará a ID chamada para um número de telefone externo se o número estiver associado a um usuário no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="66e7f-145">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="66e7f-146">Se o número de telefone não estiver no Azure AD, o nome de exibição fornecido pela Telco será exibido se estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="66e7f-146">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="66e7f-147">O atributo BlockIncomingCallerID permite o bloqueio da identificação de chamada nas chamadas PSTN de entrada.</span><span class="sxs-lookup"><span data-stu-id="66e7f-147">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="66e7f-148">Você pode definir esse atributo, mas ele não está disponível para os usuários finais na página Configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="66e7f-148">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="66e7f-149">E ele está disponível atualmente apenas com a conectividade PSTN Online.</span><span class="sxs-lookup"><span data-stu-id="66e7f-149">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="66e7f-150">Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="66e7f-150">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="66e7f-151">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="66e7f-151">Related topics</span></span>
[<span data-ttu-id="66e7f-152">Perguntas comuns sobre a transferência de números de telefone</span><span class="sxs-lookup"><span data-stu-id="66e7f-152">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="66e7f-153">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="66e7f-153">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="66e7f-154">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="66e7f-154">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="66e7f-155">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="66e7f-155">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="66e7f-156">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="66e7f-156">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
