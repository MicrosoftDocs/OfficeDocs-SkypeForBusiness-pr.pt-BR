---
title: Estacionamento de chamada criar novo ou editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Intervalos de números do estacionamento de chamada definem os números temporários nos quais as chamadas estacionadas são mantidas até que alguém as recupere ou tempo limite.
ms.openlocfilehash: 4052354ac50a3881817593485567a8197175b05f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23248422"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="1f33c-103">Estacionamento de Chamada: Criar Novo ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="1f33c-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="1f33c-104">Intervalos de números do estacionamento de chamada definem os números temporários nos quais as chamadas estacionadas são mantidas até que alguém as recupere ou tempo limite.</span><span class="sxs-lookup"><span data-stu-id="1f33c-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1f33c-105">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="1f33c-105">UI Reference</span></span>

<span data-ttu-id="1f33c-106">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="1f33c-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="1f33c-107">**Nome** Digite um nome descritivo que identifica o intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="1f33c-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="1f33c-108">Depois de salvar o intervalo de números, esse nome não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="1f33c-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="1f33c-109">**Intervalo de número** No primeiro campo, digite o número inicial do intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="1f33c-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="1f33c-110">No segundo campo, digite o número final do intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="1f33c-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="1f33c-111">O número inicial do intervalo deve ser menor ou igual ao número final.</span><span class="sxs-lookup"><span data-stu-id="1f33c-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="1f33c-112">O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="1f33c-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="1f33c-p103">O intervalo de números precisa ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.</span><span class="sxs-lookup"><span data-stu-id="1f33c-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="1f33c-115">Se o intervalo de números começa com o caractere \* ou #, o intervalo deve ser maior que 100.</span><span class="sxs-lookup"><span data-stu-id="1f33c-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="1f33c-116">Valores válidos: deve coincidir com a cadeia de caracteres de expressão regular ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="1f33c-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="1f33c-117">Isso significa que o valor deve ser uma cadeia de caracteres iniciada com o caractere \* ou #, ou um número entre 1 e 9 (o primeiro caractere não pode ser um zero).</span><span class="sxs-lookup"><span data-stu-id="1f33c-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="1f33c-118">Se o primeiro caractere for \* ou #, o caractere seguinte deve ser um número entre 1 e 9 (ele não pode ser um zero).</span><span class="sxs-lookup"><span data-stu-id="1f33c-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="1f33c-119">Os caracteres subsequentes podem ser qualquer número entre 0 e 9 até sete caracteres adicionais (por exemplo, "#6000", "\*92000", "\*95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="1f33c-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="1f33c-120">Se o primeiro caractere não for \* ou #, o primeiro caractere deve ser um número entre 1 e 9 (ele não pode ser zero), seguido por até oito caracteres, cada um número entre 0 e 9 (por exemplo: 915551212; 41212; 300).</span><span class="sxs-lookup"><span data-stu-id="1f33c-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="1f33c-p105">No total, você não deve ter mais do que 50.000 números por pool. Cada intervalo de números envolve normalmente 100 ou menos números, mas pode ser muito maior, contanto que inclua menos de 10.000 números. Por exemplo, em vez de especificar um número inicial de "7000000" e um número final de "8000000", considere especificar um número inicial de"7000000" e um número final de"7000100".</span><span class="sxs-lookup"><span data-stu-id="1f33c-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="1f33c-124">**FQDN do servidor de destino** Selecione o nome de domínio totalmente qualificado (FQDN) ou ID de serviço do serviço aplicativo que hospeda o aplicativo de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1f33c-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="1f33c-125">Todas as chamadas estacionadas em números dentro do intervalo especificado pelos números inicial e final serão encaminhadas para esse servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="1f33c-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="1f33c-126">Para obter detalhes sobre os recursos de estacionamento de chamada e capacidades, consulte [Planejar estacionamento de chamada no Skype para negócios](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="1f33c-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="1f33c-127">Para obter detalhes sobre como trabalhar com intervalos de números do estacionamento de chamada, consulte [Configurar extensões de número de telefone para o estacionamento de chamadas](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="1f33c-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


