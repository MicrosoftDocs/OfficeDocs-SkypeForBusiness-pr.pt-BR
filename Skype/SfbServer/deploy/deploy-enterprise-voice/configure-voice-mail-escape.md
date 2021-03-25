---
title: Configurar escape de caixa postal no Skype for Business
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumo: saiba como configurar o escape de caixa postal no Skype for Business Server usando o Shell de Gerenciamento do Skype for Business Server.'
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106367"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="a76c5-103">Configurar escape de caixa postal no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a76c5-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="a76c5-104">**Resumo:** Saiba como configurar o escape de caixa postal no Skype for Business Server usando o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a76c5-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="a76c5-105">Quando um usuário configura o toque simultâneo para um telefone celular, um chamador normalmente será roteado para a caixa postal pessoal do usuário se o telefone celular estiver desligado, sem bateria ou fora do intervalo.</span><span class="sxs-lookup"><span data-stu-id="a76c5-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="a76c5-106">Com o Skype for Business Server, os usuários podem optar por ter chamadas relacionadas aos negócios roteados para seu sistema de caixa postal corporativo.</span><span class="sxs-lookup"><span data-stu-id="a76c5-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="a76c5-107">Especificamente, um temporizador pode ser configurado e, se a chamada for atendida pela caixa postal da operadora dentro do intervalo de tempo definido, o Skype for Business Server se desconecta do sistema de caixa postal da operadora (e da caixa postal pessoal do usuário), enquanto os pontos de extremidade restantes do usuário no sistema corporativo continuam a tocar.</span><span class="sxs-lookup"><span data-stu-id="a76c5-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="a76c5-108">Dessa forma, o chamador é automaticamente roteado para a caixa postal corporativa do usuário.</span><span class="sxs-lookup"><span data-stu-id="a76c5-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="a76c5-109">Essa configuração é executada usando o cmdlet Shell de Gerenciamento do Skype for Business Server, **Set-CsVoicePolicy**, no nível da política de voz, com os seguintes parâmetros.</span><span class="sxs-lookup"><span data-stu-id="a76c5-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="a76c5-110">Para configurar a escape de caixa postal</span><span class="sxs-lookup"><span data-stu-id="a76c5-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="a76c5-111">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="a76c5-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a76c5-112">Especifique os parâmetros a seguir para **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="a76c5-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="a76c5-113">**EnableVoicemailEscapeTimer** - Ativa ou desativa o timer de escape</span><span class="sxs-lookup"><span data-stu-id="a76c5-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="a76c5-p102">**PSTNVoicemailEscapeTimer** - Especifica o valor do tempo limite em milissegundos. O valor padrão é 1500 milissegundos e o valor pode ir de 0 a 8000 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="a76c5-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="a76c5-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a76c5-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="a76c5-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="a76c5-117">See also</span></span>

[<span data-ttu-id="a76c5-118">Configurando políticas de voz e registros de uso PSTN para autorizar privilégios e recursos de chamada</span><span class="sxs-lookup"><span data-stu-id="a76c5-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)