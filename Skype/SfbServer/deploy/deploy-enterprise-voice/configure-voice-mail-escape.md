---
title: Configurar escape da caixa postal no Skype para negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Resumo: Saiba como configurar escape da caixa postal no Skype para Business Server usando o Skype do Shell de gerenciamento do servidor de negócios.'
ms.openlocfilehash: 3e8686690634b9571cae963b8ca91d73a6758e26
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985133"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="96ce2-103">Configurar escape da caixa postal no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="96ce2-103">Configure voice mail escape in Skype for Business</span></span>
 
<span data-ttu-id="96ce2-104">**Resumo:** Saiba como configurar escape da caixa postal no Skype para Business Server usando o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="96ce2-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="96ce2-105">Quando um usuário configura o toque simultâneo para um celular, um chamador geralmente será roteado para caixa postal do usuário pessoal se o telefone celular está desativado, sem bateria ou fora do intervalo.</span><span class="sxs-lookup"><span data-stu-id="96ce2-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="96ce2-106">Com o Skype para Business Server, os usuários podem optar por ter relacionado aos negócios as chamadas roteadas para seu sistema de correio de voz corporativa.</span><span class="sxs-lookup"><span data-stu-id="96ce2-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="96ce2-107">Especificamente, um temporizador pode ser configurado e se a chamada é atendida por postal da operadora dentro do intervalo de tempo definido, o Skype para Business Server será desconectada do sistema de caixa postal da operadora (e caixa postal do usuário pessoal), enquanto o usuário pontos de extremidade restantes no sistema corporativo continuam a tocar.</span><span class="sxs-lookup"><span data-stu-id="96ce2-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="96ce2-108">Dessa forma, o chamador é roteado automaticamente para postal corporativo do usuário.</span><span class="sxs-lookup"><span data-stu-id="96ce2-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>
  
<span data-ttu-id="96ce2-109">Essa configuração é realizada usando o Skype para o cmdlet do Shell de gerenciamento do servidor de negócios, **Set-CsVoicePolicy**, no nível de política de voz, com os seguintes parâmetros.</span><span class="sxs-lookup"><span data-stu-id="96ce2-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>
  
### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="96ce2-110">Para configurar o escape da caixa postal</span><span class="sxs-lookup"><span data-stu-id="96ce2-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="96ce2-111">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="96ce2-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="96ce2-112">Especifique os parâmetros a seguir para **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="96ce2-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
   - <span data-ttu-id="96ce2-113">**EnableVoicemailEscapeTimer** - Ativa ou desativa o timer de escape.</span><span class="sxs-lookup"><span data-stu-id="96ce2-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
   - <span data-ttu-id="96ce2-p102">**PSTNVoicemailEscapeTimer** - Especifica o valor do tempo limite em milissegundos. O valor padrão é 1500 milissegundos e o valor pode ir de 0 a 8000 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="96ce2-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>
    
## <a name="example"></a><span data-ttu-id="96ce2-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="96ce2-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="96ce2-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="96ce2-117">See also</span></span>

[<span data-ttu-id="96ce2-118">Configurando políticas de voz e registros de uso do PSTN para autorizar privilégios e recursos de chamada</span><span class="sxs-lookup"><span data-stu-id="96ce2-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

