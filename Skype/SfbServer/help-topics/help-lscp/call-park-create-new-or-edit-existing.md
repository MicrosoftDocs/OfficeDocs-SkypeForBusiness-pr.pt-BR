---
title: Estacionamento de Chamada Criar Novo ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Os intervalos de números de Estacionamento de Chamada definem os números temporários em que as chamadas estacionadas são mantidas até que alguém as recupere ou o tempo se esvae.
ms.openlocfilehash: 5ee0891ebaabc97b965aadc5f1ab1c4390669427
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819381"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="dc7bd-103">Estacionamento de Chamada: Criar Novo ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="dc7bd-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="dc7bd-104">Os intervalos de números de Estacionamento de Chamada definem os números temporários em que as chamadas estacionadas são mantidas até que alguém as recupere ou o tempo se esvae.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="dc7bd-105">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="dc7bd-105">UI Reference</span></span>

<span data-ttu-id="dc7bd-106">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="dc7bd-107">**Nome** Digite um nome descritivo que identifique o intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="dc7bd-108">Depois de salvar o intervalo de números, esse nome não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="dc7bd-109">**Intervalo de números** No primeiro campo, digite o número inicial do intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="dc7bd-110">No segundo campo, digite o número final do intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="dc7bd-111">O número inicial do intervalo deve ser menor ou igual ao número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="dc7bd-112">O valor do número inicial do intervalo deve ter a mesma extensão que o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="dc7bd-113">O intervalo de números deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-113">The number range must be unique.</span></span> <span data-ttu-id="dc7bd-114">Esse intervalo não pode se sobrepor a nenhum outro intervalo.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-114">This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="dc7bd-115">Se o intervalo de números começar com o caractere \* ou #, o intervalo deverá ser maior que 100.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="dc7bd-116">Valores válidos: devem corresponder à cadeia de caracteres de expressão regular ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="dc7bd-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="dc7bd-117">Isso significa que o valor deve ser uma cadeia de caracteres começando com o caractere ou # ou um número de 1 a 9 (o primeiro caractere \* não pode ser zero).</span><span class="sxs-lookup"><span data-stu-id="dc7bd-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="dc7bd-118">Se o primeiro caractere for ou #, o caractere seguinte deverá ser um número \* de 1 a 9 (não pode ser zero).</span><span class="sxs-lookup"><span data-stu-id="dc7bd-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="dc7bd-119">Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000", " \* 92000", " \* 95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="dc7bd-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="dc7bd-120">Se o primeiro caractere não for ou #, o primeiro caractere deverá ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um deles um número \* de 0 a 9 (por exemplo: 915551212;41212;300).</span><span class="sxs-lookup"><span data-stu-id="dc7bd-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="dc7bd-121">Você não deve ter mais de um total de 50.000 números por pool.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-121">You should not have more than a total of 50,000 numbers per pool.</span></span> <span data-ttu-id="dc7bd-122">Cada intervalo de números geralmente abrange 100 ou menos números, mas pode ser muito maior, desde que inclua menos de 10.000 números.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-122">Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers.</span></span> <span data-ttu-id="dc7bd-123">Por exemplo, em vez de especificar um número inicial em "7000000" e um número final em "8000000", considere especificar um número inicial em "7000000" e um número final em "7000100".</span><span class="sxs-lookup"><span data-stu-id="dc7bd-123">For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="dc7bd-124">**FQDN do servidor de destino** Selecione o nome de domínio totalmente qualificado (FQDN) ou o ID de serviço do serviço de Aplicativo que hospeda o aplicativo Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="dc7bd-125">Todas as chamadas estacionadas em números dentro do intervalo especificado pelo número inicial e número final no intervalo de números serão roteadas para este servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="dc7bd-126">Para obter detalhes sobre recursos de Estacionamento de Chamada, consulte [Plan for Call Park in Skype for Business 2015.](../../plan-your-deployment/enterprise-voice-solution/call-park.md)</span><span class="sxs-lookup"><span data-stu-id="dc7bd-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="dc7bd-127">Para obter detalhes sobre como trabalhar com intervalos de números de Estacionamento de Chamadas, consulte Configurar Extensões de Número de Telefone [para Estacionamento de Chamadas.](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc7bd-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


