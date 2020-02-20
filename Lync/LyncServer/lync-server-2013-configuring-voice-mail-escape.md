---
title: 'Lync Server 2013: Configurando o escape de caixa postal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43e5ec9a9f932b9c8970886daf439bae6934d36b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="c8492-102">Configurando o escape de caixa postal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8492-102">Configuring voice mail escape in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8492-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c8492-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c8492-104">Quando um usuário configura ligação simultânea para um celular, um chamador geralmente é roteado para a caixa postal pessoal do usuário, caso o celular esteja desligado, sem bateria ou fora de área.</span><span class="sxs-lookup"><span data-stu-id="c8492-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="c8492-105">Com o Lync Server 2013, os usuários podem optar por ter chamadas relacionadas à empresa roteadas para seu sistema de caixa postal corporativo.</span><span class="sxs-lookup"><span data-stu-id="c8492-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="c8492-106">Especificamente, um timer pode ser configurado e, se a chamada for atendida pela caixa postal da operadora dentro do intervalo de tempo definido, o Lync Server será desconectado do sistema de caixa postal da operadora (e da caixa postal pessoal do usuário), enquanto o restante do usuário os pontos de extremidade no sistema corporativo continuam a tocar.</span><span class="sxs-lookup"><span data-stu-id="c8492-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="c8492-107">Desta maneira, o chamador será roteado automaticamente para a caixa postal corporativa do usuário.</span><span class="sxs-lookup"><span data-stu-id="c8492-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="c8492-108">Essa configuração é realizada usando o cmdlet do Shell de gerenciamento do Lync Server, **set-CsVoicePolicy**, no nível de política de voz, com os parâmetros a seguir.</span><span class="sxs-lookup"><span data-stu-id="c8492-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="c8492-109">Para configurar o escape de caixa postal</span><span class="sxs-lookup"><span data-stu-id="c8492-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="c8492-110">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c8492-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c8492-111">Especifique os parâmetros a seguir para **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="c8492-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="c8492-112">**EnableVoicemailEscapeTimer** - Ativa ou desativa o timer de escape</span><span class="sxs-lookup"><span data-stu-id="c8492-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="c8492-p102">**PSTNVoicemailEscapeTimer** - Especifica o valor do tempo limite em milissegundos. O valor padrão é 1500 milissegundos e o valor pode ir de 0 a 8000 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="c8492-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="c8492-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c8492-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8492-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c8492-116">See Also</span></span>


[<span data-ttu-id="c8492-117">Configurando políticas de voz e registros de uso de PSTN para autorizar recursos e privilégios de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8492-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

