---
title: Configurar Microsoft 365 Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Saiba como configurar o Microsoft 365 Business Voice em sua empresa ou organização de pequeno a médio porte.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 534005df5161a69fd64ac94c444046508b9d7fd1
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130324"
---
# <a name="set-up-microsoft-365-business-voice"></a><span data-ttu-id="d8ab0-103">Configurar Microsoft 365 Business Voice</span><span class="sxs-lookup"><span data-stu-id="d8ab0-103">Set up Microsoft 365 Business Voice</span></span>

<span data-ttu-id="d8ab0-104">O Business Voice é um sistema de telefonia completo que pode substituir seu provedor de telefonia existente.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-104">Business Voice is a complete phone system that can replace your existing telephony provider.</span></span> <span data-ttu-id="d8ab0-105">Se você é uma nova empresa configurando números de telefone pela primeira vez ou uma empresa estabelecida mudando de um provedor de telefonia local herdado, as etapas nestes artigos podem ajudá-lo a se levantar e executar com o Business Voice.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-105">Whether you're a new business setting up phone numbers for the first time, or an established business moving from a legacy on-premises telephony provider, the steps in these articles can help you get up and running with Business Voice.</span></span> <span data-ttu-id="d8ab0-106">Quando terminar de configurar o Business Voice:</span><span class="sxs-lookup"><span data-stu-id="d8ab0-106">When you're finished setting up Business Voice:</span></span>

* <span data-ttu-id="d8ab0-107">Você poderá receber chamadas telefônicas gratuitas ou de chamada gratuita em uma linha telefônica principal da empresa.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-107">You'll be able to receive toll or toll-free phone calls on a main company phone line.</span></span> <span data-ttu-id="d8ab0-108">Você pode até configurar um menu de chamada, se quiser.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-108">You can even set up a call menu if you want.</span></span>
* <span data-ttu-id="d8ab0-109">Os usuários definidos com o Business Voice terão seus próprios números de telefone de discagem direta que podem usar para fazer e receber chamadas telefônicas de qualquer dispositivo com Teams instalado.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-109">Users set up with Business Voice will have their own direct-dial phone numbers that they can use to make and receive phone calls from any device with Teams installed.</span></span>
* <span data-ttu-id="d8ab0-110">Os participantes da reunião poderão ligar para reuniões usando um telefone normal se não puderem ingressar em um cliente Teams.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-110">Meeting participants will be able to call in to meetings using a regular phone if they're unable to join from a Teams client.</span></span>
* <span data-ttu-id="d8ab0-111">Se você tiver números de telefone existentes, poderá continuar a usá-los depois que eles são movidos para o Business Voice.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-111">If you have existing phone numbers, you'll be able to continue using them after they're moved to Business Voice.</span></span>

<span data-ttu-id="d8ab0-112">Se você quiser saber mais sobre o Business Voice, confira O que é [Microsoft 365 Business Voice?](whats-business-voice.md).</span><span class="sxs-lookup"><span data-stu-id="d8ab0-112">If you want to learn more about Business Voice, check out [What is Microsoft 365 Business Voice?](whats-business-voice.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8ab0-113">As informações nesses artigos são aplicáveis somente ao Business Voice **com** Plano de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-113">The information in these articles is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="d8ab0-114">O Business Voice com o plano de chamada só está disponível em alguns países e regiões.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-114">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="d8ab0-115">Antes de começar a configurar o Business Voice, verifique a disponibilidade de país e região para [o Business Voice](country-region-availability.md) para ver se seu país ou região dá suporte ao Business Voice com Plano de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-115">Before you start setting up Business Voice, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="d8ab0-116">Se o locatário estiver localizado em um país ou região que não é compatível com o plano de chamada, confira [Obter ajuda de um revendedor ou parceiro da Microsoft](reseller-partner-support.md).</span><span class="sxs-lookup"><span data-stu-id="d8ab0-116">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>
>
> <span data-ttu-id="d8ab0-117">O Microsoft Teams e o Business Voice funcionam apenas quando as caixas de correio dos usuários estão localizadas no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-117">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="d8ab0-118">Eles não oferecem suporte a caixas de correio no Servidor Exchange local.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-118">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="d8ab0-119">Esse processo de instalação não dá suporte Skype for Business implantações híbridas.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-119">This setup process doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="d8ab0-120">Se você tiver uma implantação híbrida do Skype for Business e quiser configurar ao Business Voice, consulte [Configurar o sistema telefônico na sua organização](../setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="d8ab0-120">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d8ab0-121">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="d8ab0-121">Before you begin</span></span>

<span data-ttu-id="d8ab0-122">Antes de configurar o Business Voice, há algumas coisas que você precisa fazer.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-122">Before you set up Business Voice, there are a few things you need to do.</span></span> <span data-ttu-id="d8ab0-123">As tarefas a seguir garantirão que sua organização esteja pronta para o Business Voice.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-123">The following tasks will make sure your organization is ready for Business Voice.</span></span>

* <span data-ttu-id="d8ab0-124">**Compre licenças do Business Voice** e, se você quiser obter um número de chamada gratuita ou fazer chamadas telefônicas de longa distância, Créditos de Comunicação.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-124">**Buy Business Voice licenses** and, if you want to get a toll-free number or make long-distance phone calls, Communication Credits.</span></span> <span data-ttu-id="d8ab0-125">Para obter mais informações, consulte [O que preciso comprar para usar Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="d8ab0-125">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
* <span data-ttu-id="d8ab0-126">**Certifique-se de que sua conexão com a Internet possa dar suporte ao Business Voice.**</span><span class="sxs-lookup"><span data-stu-id="d8ab0-126">**Make sure your Internet connection can support Business Voice**.</span></span> <span data-ttu-id="d8ab0-127">Para obter mais informações, [consulte Check your Internet connection for Business Voice](get-ready-internet.md).</span><span class="sxs-lookup"><span data-stu-id="d8ab0-127">For more information, see [Check your Internet connection for Business Voice](get-ready-internet.md).</span></span>
* <span data-ttu-id="d8ab0-128">**Configurar Teams nos dispositivos dos** usuários, configurar saudações de caixa postal e ajudar os usuários a aprender sobre Teams.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-128">**Set up Teams on your users' devices**, set up voicemail greetings, and help your users learn about Teams.</span></span> <span data-ttu-id="d8ab0-129">Para obter mais informações, consulte Como posso preparar meus usuários para [Microsoft 365 Business Voice?](prepare-users.md).</span><span class="sxs-lookup"><span data-stu-id="d8ab0-129">For more information, see [How do I get my users ready for Microsoft 365 Business Voice?](prepare-users.md).</span></span>

<span data-ttu-id="d8ab0-130">Depois de preparar sua organização para o Business Voice, selecione **Próxima etapa: Iniciar a configuração do Business Voice**.</span><span class="sxs-lookup"><span data-stu-id="d8ab0-130">After you've prepare your organization for Business Voice, select **Next step: Start setting up Business Voice**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d8ab0-131">Próxima etapa: Iniciar a configuração do Business Voice</span><span class="sxs-lookup"><span data-stu-id="d8ab0-131">Next step: Start setting up Business Voice</span></span>](set-up-emergency-locations.md)
