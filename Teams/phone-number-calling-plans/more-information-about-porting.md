---
title: Mais informações sobre portabilidade
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tonysmit,jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1keyword: ms.teamsadmincenter.voice.phonenumbers.porting.moreinfo
description: Obtenha as diretrizes necessárias para portar seus números de telefone para o Microsoft Teams.
ms.openlocfilehash: 53a2c640a708e5da0ed4c0d30bb678fc3cd2cbe3
ms.sourcegitcommit: ced9b584eeceff7ca0109cba5823c7c3ddbd092e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2019
ms.locfileid: "37886954"
---
# <a name="more-information-about-porting"></a><span data-ttu-id="bdd8f-103">Mais informações sobre portabilidade</span><span class="sxs-lookup"><span data-stu-id="bdd8f-103">More information about porting</span></span>

<span data-ttu-id="bdd8f-104">Aqui você encontrará mais informações sobre como fazer a portabilidade de seus números de telefone para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-104">Here you'll find more information about porting your phone numbers to Microsoft Teams.</span></span>

<span data-ttu-id="bdd8f-105">Para obter instruções passo a passo completas, consulte transferir números de telefone para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-105">For complete step-by-step instructions, see Transfer phone numbers to Teams.</span></span>

<span data-ttu-id="bdd8f-106">Se precisar de ajuda ou se precisar de mais números de telefone, entre em contato com a [ajuda da PSTN Desk do serviço](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span><span class="sxs-lookup"><span data-stu-id="bdd8f-106">If you need help or if you need to get more phone numbers, contact the [PSTN service desk help](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>

## <a name="port-order-account-information"></a><span data-ttu-id="bdd8f-107">Informações da conta do pedido de portabilidade</span><span class="sxs-lookup"><span data-stu-id="bdd8f-107">Port order account information</span></span>

<span data-ttu-id="bdd8f-108">Quando estiver na página **adicionar informações de conta** do assistente de portabilidade para enviar um pedido de portabilidade, você digitará quase todas as mesmas informações que você forneceria no loa, incluindo:</span><span class="sxs-lookup"><span data-stu-id="bdd8f-108">When you're on the **Add account information** page of the porting wizard to submit a port order, you'll  enter almost all the same information that you would provide in the LOA, including:</span></span>
  
- <span data-ttu-id="bdd8f-109">Número da conta para o provedor de serviços ou operadora</span><span class="sxs-lookup"><span data-stu-id="bdd8f-109">Account number for the service provider or carrier</span></span>
    
- <span data-ttu-id="bdd8f-110">Número de telefone de cobrança (BTN)</span><span class="sxs-lookup"><span data-stu-id="bdd8f-110">Billing Telephone Number (BTN)</span></span>
    
- <span data-ttu-id="bdd8f-111">PIN-se necessário para o seu provedor de serviços ou operadora atual</span><span class="sxs-lookup"><span data-stu-id="bdd8f-111">PIN - if needed by your current service provider or carrier</span></span>
    
- <span data-ttu-id="bdd8f-112">Nome da organização</span><span class="sxs-lookup"><span data-stu-id="bdd8f-112">Organization name</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bdd8f-113">Isso só aceita 25 caracteres, incluindo os espaços.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-113">This will only accept 25 characters, including spaces.</span></span> <span data-ttu-id="bdd8f-114">Se o nome da organização tiver mais de 25 caracteres, serão enviados os 25 primeiros caracteres do nome e o pedido de portabilidade ainda será processado.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-114">If the organization name is longer than 25 characters, the first 25 characters of the name will be submitted and the port order will still be processed.</span></span>
  
- <span data-ttu-id="bdd8f-115">Nome da pessoa autorizada a fazer alterações na conta</span><span class="sxs-lookup"><span data-stu-id="bdd8f-115">Name of person authorized to make changes to the account</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bdd8f-116">Isso só aceitará 15 caracteres, incluindo espaços.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-116">This will only accept 15 characters, including spaces.</span></span> <span data-ttu-id="bdd8f-117">Se o nome da pessoa tiver mais de 15 caracteres, os 15 primeiros caracteres do nome serão enviados e o pedido de portabilidade ainda será processado.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-117">If the authorized person's name is longer than 15 characters, the first 15 characters of the name will be submitted and the port order will still be processed.</span></span> 
  
- <span data-ttu-id="bdd8f-118">Endereço do serviço</span><span class="sxs-lookup"><span data-stu-id="bdd8f-118">Service address</span></span>
  
<span data-ttu-id="bdd8f-119">Para que o envio do pedido de portabilidade seja fácil e evitar erros, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bdd8f-119">To make submitting the port order easy and avoid errors, make sure you do the following:</span></span>
  
- <span data-ttu-id="bdd8f-120">Remova todos os recursos (como grupos de buscas) associados a seus números.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-120">Remove any features (such as Hunt Groups) associated with your numbers.</span></span> <span data-ttu-id="bdd8f-121">Certifique-se de que não haja recursos de controle de chamada avançados, como chamadas de caça ou toques distintos, habilitados nestes números de telefone.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-121">Make sure there are no advanced call control features, such as Call Hunt or Distinctive Ring, enabled on these phone numbers.</span></span>
    
- <span data-ttu-id="bdd8f-122">Certifique-se de que você não tenha feito nenhuma nova encomenda de serviço ou se desconectará com seu provedor de serviços atual.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-122">Ensure that you haven't placed any new service orders or disconnects with your current service provider.</span></span>
    
- <span data-ttu-id="bdd8f-123">Verifique se todos os números são da mesma operadora e da mesma conta.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-123">Make sure all numbers are from the same carrier and the same account.</span></span>
    
- <span data-ttu-id="bdd8f-124">Verifique se as informações da conta que você forneceu correspondem exatamente às que a operadora de telefonia possui.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-124">Make sure the account information you give matches exactly what your phone carrier has on record.</span></span> <span data-ttu-id="bdd8f-125">As informações incompatíveis são a causa mais comum de erros e podem atrasar seu pedido de portabilidade.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-125">Mismatched information is the most common cause of errors and can delay your port order.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="bdd8f-126">Não desconecte seus serviços com o seu provedor de serviços ou operadora.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-126">Don't disconnect your services with your service provider or carrier.</span></span> <span data-ttu-id="bdd8f-127">Você deve manter o serviço anterior ativo para portar seus números de telefone para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-127">You must keep your previous service active in order to port your phone numbers to Teams.</span></span> <span data-ttu-id="bdd8f-128">Não congele sua conta com seu provedor de serviços ou operadora.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-128">Don't freeze your account with your service provider or carrier.</span></span> <span data-ttu-id="bdd8f-129">O congelamento da conta impede a alteração de operadoras nela.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-129">Freezing the account prevents the change of carriers on the account.</span></span> <span data-ttu-id="bdd8f-130">O usuário autorizado precisará enviar uma solicitação à operadora atual para cancelar o congelamento.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-130">The authorized user will need to submit an order to the current carrier to remove the freeze.</span></span> <span data-ttu-id="bdd8f-131">Esse processo pode levar de uma a três semanas, dependendo da operadora.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-131">This process can take one to three weeks, depending on the carrier.</span></span>

## <a name="authorized-person-on-the-account"></a><span data-ttu-id="bdd8f-132">Pessoa autorizada na conta</span><span class="sxs-lookup"><span data-stu-id="bdd8f-132">Authorized person on the account</span></span>

<span data-ttu-id="bdd8f-133">No assistente de portabilidade, você deve digitar o nome da pessoa que está autorizada a fazer alterações na conta com o provedor de serviços ou operadora.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-133">In the porting wizard, you must enter the name of the person who is authorized to make changes to the account with the service provider or carrier.</span></span> <span data-ttu-id="bdd8f-134">O nome não é usado para processar a ordem da portabilidade, mas é usado no caso de uma contestação, ou se algo estiver incorreto quando os números forem portados.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-134">The name isn't used to process the port order, but is used in the case of a dispute, or if something is incorrect when numbers are ported.</span></span> <span data-ttu-id="bdd8f-135">Essa pessoa é responsável pela autorização da carta de autorização (LOA) para um pedido de portabilidade.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-135">This person is accountable for the Letter of Authorization (LOA) for a port order.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bdd8f-136">A caixa está limitada a 15 caracteres (incluindo espaços).</span><span class="sxs-lookup"><span data-stu-id="bdd8f-136">The box is limited to 15 characters (including spaces).</span></span> <span data-ttu-id="bdd8f-137">Não ter o nome completo na caixa não atrasa ou cancela o pedido de portabilidade.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-137">Not having the complete name in the box won't delay or cancel the port order.</span></span>
  
## <a name="whats-my-billing-telephone-number"></a><span data-ttu-id="bdd8f-138">Qual é o meu número de telefone de cobrança?</span><span class="sxs-lookup"><span data-stu-id="bdd8f-138">What's my billing telephone number?</span></span>

<span data-ttu-id="bdd8f-139">O número de telefone de cobrança (BTN) é o número de telefone principal que está incluído em sua fatura e cobrado pelo seu provedor de serviços ou operadora.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-139">The billing telephone number (BTN) is the main phone number that's included on your bill and billed by your service provider or carrier.</span></span> <span data-ttu-id="bdd8f-140">Se você estiver transferindo um número de telefone de uma conta que tem apenas um número de telefone, será necessário digitar este número de telefone.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-140">If you're transferring a phone number from an account that has only one phone number, you need to enter this phone number.</span></span> <span data-ttu-id="bdd8f-141">Se você estiver transferindo números de telefone de uma conta que tenha mais de um, examine sua fatura ou entre em contato com seu provedor de serviços ou operadora para determinar o que o BTN é para a sua conta.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-141">If you're transferring phone numbers from an account that has more than one, you can look at your bill or contact your service provider or carrier to determine what the BTN is for your account.</span></span>

## <a name="what-should-i-put-in-for-the-account-number"></a><span data-ttu-id="bdd8f-142">O que devo colocar no número da conta?</span><span class="sxs-lookup"><span data-stu-id="bdd8f-142">What should I put in for the account number?</span></span>

<span data-ttu-id="bdd8f-143">Em geral, você pode encontrar o número da conta em qualquer cobrança ou fatura que você tiver do seu provedor de serviços ou operadora ou pode fazer logon no site da sua operadora.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-143">Typically, you can find the account number on any bill or invoice you have from your service provider or carrier, or you can log on to your carrier's website.</span></span> <span data-ttu-id="bdd8f-144">Se ainda não souber o número da conta, você pode entrar em contato com o provedor de serviços ou operadora para obtê-lo.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-144">If you still don't know the account number, you can contact your service provider or carrier to get it.</span></span>
  
> [!CAUTION]
>  <span data-ttu-id="bdd8f-145">É importante que você não use espaços, traços ou hifens ao digitar seu provedor de serviço ou número de conta da operadora.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-145">It's important that you make sure you don't use spaces, dashes, or hyphens when entering your service provider or carrier account number.</span></span>

## <a name="what-should-i-put-in-for-the-organization-name"></a><span data-ttu-id="bdd8f-146">O que devo colocar no nome da organização?</span><span class="sxs-lookup"><span data-stu-id="bdd8f-146">What should I put in for the organization name?</span></span>

<span data-ttu-id="bdd8f-147">Este é o nome da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-147">This is the name of your organization.</span></span> <span data-ttu-id="bdd8f-148">O nome da organização é limitado a 25 caracteres, que inclui espaços.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-148">The organization name is limited to 25 characters, which includes spaces.</span></span> <span data-ttu-id="bdd8f-149">O nome da empresa não é usado para processar a solicitação de pedido de portabilidade.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-149">The name of the company isn't used to process the port order request.</span></span> <span data-ttu-id="bdd8f-150">Ele é usado no caso de uma contestação ou se algo estiver incorreto quando os números de telefone estiverem sendo portados.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-150">It's used in the case of a dispute or if something is incorrect when the phone numbers are being ported over.</span></span> <span data-ttu-id="bdd8f-151">Se não for possível ajustar o nome inteiro da empresa na caixa, não será possível atrasar ou cancelar o pedido de portabilidade.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-151">If you can't fit the entire name of the company in the box, it won't delay or cancel the port order.</span></span>
  
## <a name="what-should-i-put-in-for-the-service-address"></a><span data-ttu-id="bdd8f-152">O que devo colocar no endereço do serviço?</span><span class="sxs-lookup"><span data-stu-id="bdd8f-152">What should I put in for the service address?</span></span>

<span data-ttu-id="bdd8f-153">O endereço do serviço é diferente do endereço de cobrança ou de emergência que você registrou com o seu provedor de serviços de telefonia ou operadora.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-153">The service address is different from the billing or emergency address that you have registered with your phone service provider or carrier.</span></span> <span data-ttu-id="bdd8f-154">Se você não souber isso, entre em contato com seu provedor de serviços ou operadora para saber qual é o endereço de serviço listado na sua conta.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-154">If you don't know this, contact your service provider or carrier to find out the service address listed on your account.</span></span>

## <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="bdd8f-155">Como devo inserir os números de telefone?</span><span class="sxs-lookup"><span data-stu-id="bdd8f-155">How should I enter the phone numbers?</span></span>
<span data-ttu-id="bdd8f-156"><a name="bkadding"> </a></span><span class="sxs-lookup"><span data-stu-id="bdd8f-156"></span></span>

<span data-ttu-id="bdd8f-157">Ao enviar um pedido de portabilidade, você deve usar um arquivo CSV formatado corretamente para enviar seus números de telefone.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-157">When you submit a port order, you must use a properly formatted CSV file to submit your phone numbers.</span></span> <span data-ttu-id="bdd8f-158">Estes são os requisitos para o arquivo CSV:</span><span class="sxs-lookup"><span data-stu-id="bdd8f-158">Here are the requirements for the CSV file:</span></span>

 - <span data-ttu-id="bdd8f-159">Você pode fornecer o nome do arquivo desejado.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-159">You can give the file any name that you want.</span></span>
 - <span data-ttu-id="bdd8f-160">O arquivo só deve ter uma coluna com um cabeçalho chamado intervalo.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-160">The file must only have one column with a header named PhoneNumber.</span></span>
 - <span data-ttu-id="bdd8f-161">Cada número de telefone deve estar em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-161">Each phone number must be on a separate row.</span></span>
 - <span data-ttu-id="bdd8f-162">Os números de telefone podem ser apenas dígitos ou no formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-162">Phone numbers can be digits only or in E.164 format.</span></span>
 - <span data-ttu-id="bdd8f-163">O formato do número de telefone deve corresponder ao país ou região selecionado.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-163">The phone number format must match the country or region you selected.</span></span> <span data-ttu-id="bdd8f-164">Por exemplo, se você escolher o Reino Unido no assistente de portabilidade, use 44, que é o código do país, seguido do número de telefone com o número correto de dígitos.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-164">For example, if you choose the United Kingdom in the porting wizard, use 44, which is the country code, followed by the phone number with the correct number of digits.</span></span> <span data-ttu-id="bdd8f-165">Por exemplo, 4420812341234.</span><span class="sxs-lookup"><span data-stu-id="bdd8f-165">For example, 4420812341234.</span></span>

## <a name="how-do-i-see-the-status-of-my-port-order"></a><span data-ttu-id="bdd8f-166">Como posso ver o status do meu pedido de portabilidade?</span><span class="sxs-lookup"><span data-stu-id="bdd8f-166">How do I see the status of my port order?</span></span>

<span data-ttu-id="bdd8f-167">Veja qual é o status dos seus pedidos de portabilidade?</span><span class="sxs-lookup"><span data-stu-id="bdd8f-167">See What's the status of your port orders?</span></span>

## <a name="related-topics"></a><span data-ttu-id="bdd8f-168">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bdd8f-168">Related topics</span></span>

- <span data-ttu-id="bdd8f-169">O que é um pedido de portabilidade?</span><span class="sxs-lookup"><span data-stu-id="bdd8f-169">What's a port order?</span></span>
- [<span data-ttu-id="bdd8f-170">Diferentes tipos de números de telefone usados para Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="bdd8f-170">Different kinds of phone numbers used for Calling Plans</span></span>](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="bdd8f-171">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="bdd8f-171">Manage phone numbers for your organization</span></span>](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="bdd8f-172">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="bdd8f-172">Emergency calling terms and conditions</span></span>](../emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="bdd8f-173">[Rótulo de isenção de isenção de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="bdd8f-173">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
