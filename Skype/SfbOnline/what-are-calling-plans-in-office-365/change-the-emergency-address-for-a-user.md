---
title: Alterar o endereço de emergência de um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 5412636c-ad0e-48a5-b199-5925156abee4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Consulte as etapas sobre como alterar o endereço de emergência de um usuário para trabalhar com a Rede Telefônica Pública Comutada (PSTN) nos EUA e na Europa. '
ms.openlocfilehash: 31162e24471cb4e9259678f779143900fa61ac08
ms.sourcegitcommit: c5940ef2674a00281604045baf8b2a320c4b189d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2018
ms.locfileid: "24958347"
---
# <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="69786-103">Alterar o endereço de emergência de um usuário</span><span class="sxs-lookup"><span data-stu-id="69786-103">Change the emergency address for a user</span></span>

<span data-ttu-id="69786-104">Quando você configura Planos de Chamadas no Office 365, precisa atribuir um endereço de emergência a cada número de telefone ou suário.</span><span class="sxs-lookup"><span data-stu-id="69786-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="69786-105">Nos países europeus, o endereço de emergência é associado ao número de telefone quando você o obtém do Office 365 ou quando você transfere um número de telefone para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="69786-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="69786-106">Nos Estados Unidos, o endereço de emergência é associado ao número de telefone quando ele é atribuído ao usuário.</span><span class="sxs-lookup"><span data-stu-id="69786-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="69786-107">O endereço de emergência pode ser alterado se o usuário a quem ele está designado se mudar para um novo local.</span><span class="sxs-lookup"><span data-stu-id="69786-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="69786-108">Para mais informações sobre endereços e locais de emergência, consulte [O que são locais e endereços de emergência e encaminhamento de chamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="69786-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span></span>
  
<span data-ttu-id="69786-109">Para saber como obter um Plano de Chamada no Office 365 e o seu preço, consulte [Licenciamento de suplementos para Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="69786-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="69786-110">Alterar o endereço de emergência de um usuário</span><span class="sxs-lookup"><span data-stu-id="69786-110">Change the emergency address for a user</span></span>

<span data-ttu-id="69786-111">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="69786-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="69786-112">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="69786-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="69786-113">Navegue para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="69786-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="69786-114">No painel de navegação esquerdo, vá para **voz** > **usuários de voz**.</span><span class="sxs-lookup"><span data-stu-id="69786-114">In the left navigation, go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="69786-115">Para você ver a opção de **voz** no painel de navegação esquerdo no Skype para centro de administração de negócios, primeiro você deve comprar uma licença de complemento de **Conferência de áudio** , uma licença de complemento de **Sistema telefônico** ou pelo menos uma **licença Enterprise E5**.</span><span class="sxs-lookup"><span data-stu-id="69786-115">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="69786-116">Na página **Usuários de voz**, localize e selecione o usuário cujo endereço de emergência você quer alterar.</span><span class="sxs-lookup"><span data-stu-id="69786-116">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="69786-117">No painel Ação, em **Local de emergência**, clique em **Alterar**.</span><span class="sxs-lookup"><span data-stu-id="69786-117">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="69786-118">Na página **Atribuir número**, clique em **Alterar local**.</span><span class="sxs-lookup"><span data-stu-id="69786-118">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="69786-119">Em **Alterar endereço de emergência para**, digite o nome da cidade na caixa e clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="69786-119">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="69786-120">[!IMPORTANTE] Você só pode alterar um endereço de emergência que já foi validado.</span><span class="sxs-lookup"><span data-stu-id="69786-120">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="69786-121">Para alterar um endereço de emergência que não foi validado, excluí-la e crie outro endereço de emergência.</span><span class="sxs-lookup"><span data-stu-id="69786-121">To change an emergency address that hasn't been validated, delete it and create another emergency address.</span></span> 
  
8. <span data-ttu-id="69786-122">Selecione um novo endereço de emergência na lista e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="69786-122">Select a new emergency address from the list, and then click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="69786-123">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="69786-123">Related topics</span></span>
[<span data-ttu-id="69786-124">Adicionar ou remover um endereço de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="69786-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="69786-125">Adicionar, alterar ou remover um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="69786-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="69786-126">O que é validação de endereço?</span><span class="sxs-lookup"><span data-stu-id="69786-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="69786-127">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="69786-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="69786-128">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="69786-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="69786-129">[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="69786-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 