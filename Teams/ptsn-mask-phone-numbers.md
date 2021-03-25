---
title: Mascarar números de telefone em reuniões do Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como mascarar números de telefone em reuniões do Microsoft Teams
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117709"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a><span data-ttu-id="9fffe-103">Mascarar números de telefone em reuniões do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9fffe-103">Mask phone numbers in Microsoft Teams meetings</span></span>

<span data-ttu-id="9fffe-104">Para privacidade adicional, os números de telefone dos participantes que discam para uma reunião do Teams usando audioconferência são totalmente exibidos para os participantes internos.</span><span class="sxs-lookup"><span data-stu-id="9fffe-104">For added privacy, the phone numbers of participants who dial in to a Teams meeting using audio conferencing are fully displayed to the internal participants.</span></span> <span data-ttu-id="9fffe-105">Os números são mascarados dos participantes de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9fffe-105">The numbers are masked from the participants outside of your organization.</span></span> <span data-ttu-id="9fffe-106">Essa configuração é o padrão para todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="9fffe-106">This setting is the default for all organizations.</span></span> <span data-ttu-id="9fffe-107">O número mascarado é exibido conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="9fffe-107">The masked number is displayed as shown in the following image:</span></span>

![um exemplo de um número de telefone mascarado](media/hiddenPhoneNum.png)

<span data-ttu-id="9fffe-109">Para casos específicos de uso do setor, os administradores têm a capacidade de escolher como os números de telefone dos participantes da audioconferência aparecem em reuniões organizadas em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="9fffe-109">For specific industry use cases, admins have the ability to choose how the audio conferencing participants' phone numbers appear in meetings that are organized in their tenant.</span></span> <span data-ttu-id="9fffe-110">Os administradores podem escolher entre três opções:</span><span class="sxs-lookup"><span data-stu-id="9fffe-110">The admins can choose from three options:</span></span>

- <span data-ttu-id="9fffe-111">Os números de telefone são mascarados somente de participantes externos.</span><span class="sxs-lookup"><span data-stu-id="9fffe-111">Phone numbers are masked only from external participants.</span></span> <span data-ttu-id="9fffe-112">Os participantes que pertencem ao locatário do organizador da reunião ainda veem o número de telefone completo.</span><span class="sxs-lookup"><span data-stu-id="9fffe-112">The participants who belong to the meeting organizer's tenant still see the full phone number.</span></span>
- <span data-ttu-id="9fffe-113">Os números de telefone são mascarados de todos na reunião, exceto o organizador.</span><span class="sxs-lookup"><span data-stu-id="9fffe-113">Phone numbers are masked from everyone in the meeting except the organizer.</span></span>
- <span data-ttu-id="9fffe-114">Os números de telefone não são máscaras, o que os torna visíveis para todos na reunião.</span><span class="sxs-lookup"><span data-stu-id="9fffe-114">Phone numbers are unmasked, which makes them visible to everyone in the meeting.</span></span>

<span data-ttu-id="9fffe-115">Essa configuração é aplicada a todas as superfícies na reunião em que os números de telefone são expostos.</span><span class="sxs-lookup"><span data-stu-id="9fffe-115">This setting is applied to all the surfaces in the meeting where phone numbers are exposed.</span></span>

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a><span data-ttu-id="9fffe-116">Usar o Microsoft PowerShell para definir o mascaramento de número de telefone</span><span class="sxs-lookup"><span data-stu-id="9fffe-116">Use Microsoft PowerShell to set phone-number masking</span></span>

<span data-ttu-id="9fffe-117">Para alterar a configuração de mascaramento rede telefônica pública comutado (PSTN), defina o parâmetro do **`MaskPstnNumbersType`** cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) como uma das opções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9fffe-117">To change the Public Switched Telephone Network (PSTN) masking setting, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to one of the available options.</span></span>

<span data-ttu-id="9fffe-118">Para mascarar números de telefone somente de participantes externos, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9fffe-118">To mask phone numbers only from external participants, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

<span data-ttu-id="9fffe-119">Para mascarar números de telefone de todos os participantes da reunião (exceto o organizador), execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9fffe-119">To mask phone numbers from all participants in the meeting (except the organizer), run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

<span data-ttu-id="9fffe-120">Para desabilitar o mascaramento de número de telefone, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9fffe-120">To disable phone number masking, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```