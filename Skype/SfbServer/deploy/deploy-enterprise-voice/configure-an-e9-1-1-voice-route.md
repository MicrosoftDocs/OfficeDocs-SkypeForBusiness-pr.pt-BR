---
title: Configurar uma rota de voz E9-1-1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurar o E9-1-1 roteiros de voz no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: a8121cc7a7345150e485dc2e2b81e062672f5703
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233711"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="9adea-103">Configurar uma rota de voz E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9adea-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="9adea-104">Configurar o E9-1-1 roteiros de voz no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9adea-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="9adea-105">Para implantar o E9-1-1, é preciso primeiro configurar uma rota de voz de chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="9adea-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="9adea-106">Para obter detalhes sobre como criar rotas de voz, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="9adea-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="9adea-107">É possível definir mais de uma rota se, por exemplo, sua implantação incluir um tronco SIP primário e um secundário.</span><span class="sxs-lookup"><span data-stu-id="9adea-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9adea-108">Para incluir informações de localização em um E9-1-1 INVITE, você precisa configurar o tronco SIP que se conecta ao provedor de serviços de E9-1-1 para encaminhar as chamadas de emergência através do gateway.</span><span class="sxs-lookup"><span data-stu-id="9adea-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="9adea-109">Para isso, defina o sinalizador EnablePIDFLOSupport no cmdlet **Set-CsTrunkConfiguration** como True.</span><span class="sxs-lookup"><span data-stu-id="9adea-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="9adea-110">O valor padrão de EnablePIDFLOSupport é False.</span><span class="sxs-lookup"><span data-stu-id="9adea-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="9adea-111">Por exemplo: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` não é necessário habilitar os locais de recebimento de gateways PSTN (rede telefônica pública comutada) e gateways de número de identificação de local de emergência (Elin) de fallback.</span><span class="sxs-lookup"><span data-stu-id="9adea-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="9adea-112">Para configurar uma rota de voz de E9-1-1</span><span class="sxs-lookup"><span data-stu-id="9adea-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="9adea-113">Faça logon no computador com uma conta que seja membro dos grupos RTCUniversalServerAdmins ou membro da função administrativa CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9adea-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="9adea-114">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9adea-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9adea-115">Execute o cmdlet a seguir para criar um novo registro de uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="9adea-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="9adea-116">Esse deve ser o mesmo nome que você usará para a configuração **PSTN** na política de local.</span><span class="sxs-lookup"><span data-stu-id="9adea-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="9adea-117">Embora sua implantação tenha vários registros de uso de telefone, o exemplo a seguir adiciona "Uso de emergência" à lista atual de usos de PSTN disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9adea-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="9adea-118">Para obter detalhes, consulte [Configurar políticas de voz, registros de uso PSTN e rotas de voz no Skype for Business](voice-and-pstn.md).</span><span class="sxs-lookup"><span data-stu-id="9adea-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="9adea-119">Execute o cmdlet a seguir para criar uma nova rota de voz usando o registro de uso PSTN criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="9adea-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="9adea-120">O padrão de número deve ser o mesmo usado na configuração de **Cadeia de Caracteres de Discagem de Emergência** na política de local.</span><span class="sxs-lookup"><span data-stu-id="9adea-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="9adea-121">É necessário um sinal "+" porque o Skype for Business adiciona "+" às chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="9adea-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="9adea-122">"Co1-pstngateway-1" é a ID de serviço do tronco SIP do provedor de serviços de E9-1-1 ou a ID de serviço do gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="9adea-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="9adea-123">O exemplo a seguir usa "EmergencyRoute" como o nome da rota de voz.</span><span class="sxs-lookup"><span data-stu-id="9adea-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="9adea-124">Opcionalmente, para conexões de tronco SIP, recomendamos que você execute o cmdlet a seguir para criar uma rota local para chamadas que não são manipuladas pelo tronco SIP do provedor de serviços E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="9adea-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="9adea-125">Essa rota será usada quando a conexão com o provedor de serviços de E9-1-1 não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="9adea-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="9adea-126">O exemplo a seguir pressupõe que o usuário tenha o uso "Local" em sua política de voz.</span><span class="sxs-lookup"><span data-stu-id="9adea-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


