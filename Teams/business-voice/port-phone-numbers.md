---
title: Migrar números de telefone para o Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Saiba como mover seus números de telefone existentes de seu provedor atual para o Microsoft 365 Business Voice.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26f686197963f53f20477ccd9a16935c86a16d9f
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282608"
---
# <a name="step-7-port-phone-numbers-to-business-voice-optional"></a><span data-ttu-id="7186a-103">Etapa 7: Migrar (portabilidade) números de telefone para o Business Voice (opcional)</span><span class="sxs-lookup"><span data-stu-id="7186a-103">Step 7: Port phone numbers to Business Voice (optional)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7186a-104">As informações contidas neste artigo se aplicam apenas ao Business Voice **com** plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="7186a-104">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="7186a-105">O Business Voice com o plano de chamada só está disponível em alguns países e regiões.</span><span class="sxs-lookup"><span data-stu-id="7186a-105">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="7186a-106">Antes de ler este artigo, verifique a [Disponibilidade do Business Voice em países e regiões](country-region-availability.md) para ver se seu país ou região é compatível com o Business Voice com plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="7186a-106">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="7186a-107">Se o locatário estiver localizado em um país ou região que não é compatível com o plano de chamada, confira [Obter ajuda de um revendedor ou parceiro da Microsoft](reseller-partner-support.md).</span><span class="sxs-lookup"><span data-stu-id="7186a-107">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="7186a-108">Anteriormente, neste guia de configuração, você adquiriu números de telefone para a linha principal da empresa e para qualquer usuário ao qual você tenha atribuído uma licença Business Voice.</span><span class="sxs-lookup"><span data-stu-id="7186a-108">Earlier in this setup guide, you acquired phone numbers for the main company line and for any users that you've assigned a Business Voice license to.</span></span> <span data-ttu-id="7186a-109">**Se você for um novo negócio e não tiver nenhum número de telefone existente que queira levar para o Business Voice, pode pular esta etapa.**</span><span class="sxs-lookup"><span data-stu-id="7186a-109">**If you're a new business and don't have any existing phone numbers that you want to bring to Business Voice, you can skip this step.**</span></span>

<span data-ttu-id="7186a-110">Se você já tiver números de telefone que deseja manter quando migrar para o Business Voice, poderá trazê-los com você usando um processo chamado portabilidade de número de telefone.</span><span class="sxs-lookup"><span data-stu-id="7186a-110">If you already have phone numbers that you want to keep when you move to Business Voice, you can bring them with you by using a process called phone number porting to bring them over to Business Voice.</span></span> <span data-ttu-id="7186a-111">Depois de transferir seus números de telefone para o Business Voice, atribua-os a usuários e serviços.</span><span class="sxs-lookup"><span data-stu-id="7186a-111">After you port your phone numbers to Business Voice, you assign them to users and services.</span></span> <span data-ttu-id="7186a-112">Os números antigos substituem os números temporários adquiridos anteriormente neste guia de configuração.</span><span class="sxs-lookup"><span data-stu-id="7186a-112">The old numbers replace the temporary numbers that you acquired earlier in this setup guide.</span></span>

<span data-ttu-id="7186a-113">Antes de migrar números para o Business Voice, dê uma olhada em [Perguntas comuns sobre transferência de números de telefone](../phone-number-calling-plans/port-order-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7186a-113">Before you move numbers to Business Voice, take a look at [Transferring phone numbers common questions](../phone-number-calling-plans/port-order-overview.md).</span></span> <span data-ttu-id="7186a-114">O artigo inclui respostas a várias perguntas, incluindo quais os países ou regiões que têm suporte, quais números podem e não podem ser transferidos, quais as informações necessárias e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="7186a-114">This article includes answers to questions including what countries and regions are supported, what numbers can and can't be transferred, and what information you'll need.</span></span>

<span data-ttu-id="7186a-115">Quando estiver pronto para transferir os seus números de telefone para o Business Voice, siga as etapas indicadas em [Transferir números de telefone para o Office 365](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) para criar um pedido de portabilidade.</span><span class="sxs-lookup"><span data-stu-id="7186a-115">When you're ready to move your phone numbers to Business Voice, follow the steps in [Transfer phone numbers to Office 365](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to create a port order.</span></span> <span data-ttu-id="7186a-116">Um pedido de portabilidade inclui todas as informações necessárias para migrar seus números da operadora atual para o Business Voice.</span><span class="sxs-lookup"><span data-stu-id="7186a-116">The order includes the information that's needed to move your numbers from your current phone service carrier to Business Voice.</span></span>

<span data-ttu-id="7186a-117">Depois que seus números de telefone forem migrados para o Business Voice, você precisará atribuí-los a pessoas.</span><span class="sxs-lookup"><span data-stu-id="7186a-117">After your phone numbers have been moved to Business Voice, you need to assign them to people.</span></span> <span data-ttu-id="7186a-118">Para fazer isso, siga as etapas em [Alterar um número de telefone para um usuário](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="7186a-118">To do that, follow the steps in [Change a phone number for a user](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user).</span></span> <span data-ttu-id="7186a-119">Ao seguir estas etapas, você substituirá o número de telefone temporariamente atribuído ao usuário pelo seu número de telefone original.</span><span class="sxs-lookup"><span data-stu-id="7186a-119">When you follow these steps, you'll replace the phone number that was temporarily assigned to the user with their original phone number that you ported over.</span></span>

<span data-ttu-id="7186a-120">Se precisar de ajuda, fale conosco!</span><span class="sxs-lookup"><span data-stu-id="7186a-120">If you need help, let us know!</span></span> <span data-ttu-id="7186a-121">Estamos aqui para ajudá-lo a migrar seus números de telefone para o Business Voice da maneira mais fácil possível.</span><span class="sxs-lookup"><span data-stu-id="7186a-121">We're here to help you get your phone numbers moved to Business Voice as easy as possible.</span></span> <span data-ttu-id="7186a-122">Não deixe de incluir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="7186a-122">Be sure to include the following information:</span></span>

- <span data-ttu-id="7186a-123">A ID da sua organização ***(como contoso***. onmicrosoft.com)</span><span class="sxs-lookup"><span data-stu-id="7186a-123">Your organization ID (such as ***contoso***.onmicrosoft.com)</span></span>
- <span data-ttu-id="7186a-124">Quais tipos e quantos números para os quais você precisa obter ajuda</span><span class="sxs-lookup"><span data-stu-id="7186a-124">What types and how many numbers you need help with</span></span>
- <span data-ttu-id="7186a-125">A pessoa que autoriza a sua conta</span><span class="sxs-lookup"><span data-stu-id="7186a-125">The authorizing person on your account</span></span>
- <span data-ttu-id="7186a-126">Uma descrição do seu problema ou da sua dúvida</span><span class="sxs-lookup"><span data-stu-id="7186a-126">A description of the issue or question that you have</span></span>

<span data-ttu-id="7186a-127">Para obter ajuda com números de telefone no Canadá e nos Estados Unidos, envie a solicitação para [ptn@microsoft.com](mailto:ptn@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7186a-127">For help with phone numbers in Canada and the United States, send your request to [ptn@microsoft.com](mailto:ptn@microsoft.com).</span></span>

<span data-ttu-id="7186a-128">Para obter ajuda com números de telefone na Europa, envie a solicitação para [ptneu@microsoft.com](mailto:ptneu@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7186a-128">For help with phone numbers in Europe, send your request to [ptneu@microsoft.com](mailto:ptneu@microsoft.com).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7186a-129">Próxima etapa: Concluir a configuração do Business Voice</span><span class="sxs-lookup"><span data-stu-id="7186a-129">Next step: Finish Business Voice setup</span></span>](set-up-finish.md)
