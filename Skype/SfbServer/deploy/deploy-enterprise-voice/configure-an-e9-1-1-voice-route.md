---
title: Configurar uma rota de voz E9-1-1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configure as rotas de voz do E9-1-1 Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 86904c32db6ae43b9fa1b6f184048d3b9f419089
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833947"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Configurar uma rota de voz E9-1-1 no Skype for Business Server
 
Configure as rotas de voz do E9-1-1 Skype for Business Server Enterprise Voice. 
  
Para implantar o E9-1-1, é preciso primeiro configurar uma rota de voz de chamada de emergência. Para obter detalhes sobre como criar rotas de voz, consulte [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md). É possível definir mais de uma rota se, por exemplo, sua implantação incluir um tronco SIP primário e um secundário. 
  
> [!NOTE]
> Para incluir informações de localização em um E9-1-1 INVITE, você precisa configurar o tronco SIP que se conecta ao provedor de serviços de E9-1-1 para encaminhar as chamadas de emergência através do gateway. Para isso, defina o sinalizador EnablePIDFLOSupport no cmdlet **Set-CsTrunkConfiguration** como True. O valor padrão de EnablePIDFLOSupport é False. Por exemplo: não é necessário habilitar locais de recebimento para gateways PSTN (rede telefônica pública comutado) de fallback e gateways ELIN (Número de Identificação de Local de `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` Emergência).
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Para configurar uma rota de voz de E9-1-1

1. Faça logon no computador com uma conta que seja membro dos grupos RTCUniversalServerAdmins ou membro da função administrativa CsVoiceAdministrator.
    
2.  Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
3. Execute o cmdlet a seguir para criar um novo registro de uso PSTN. 
    
    Esse deve ser o mesmo nome que você usará para a configuração **PSTN** na política de local. Embora sua implantação tenha vários registros de uso de telefone, o exemplo a seguir adiciona "Uso de emergência" à lista atual de usos de PSTN disponíveis. Para obter detalhes, consulte [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Execute o cmdlet a seguir para criar uma nova rota de voz usando o registro de uso PSTN criado na etapa anterior.
    
    O padrão de número deve ser o mesmo usado na configuração de **Cadeia de Caracteres de Discagem de Emergência** na política de local. Um sinal "+" é necessário porque Skype for Business adiciona "+" a chamadas de emergência. "Co1-pstngateway-1" é a ID de serviço do tronco SIP do provedor de serviços de E9-1-1 ou a ID de serviço do gateway ELIN. O exemplo a seguir usa "EmergencyRoute" como o nome da rota de voz.
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. Opcionalmente, para conexões de tronco SIP, recomendamos que você execute o cmdlet a seguir para criar uma rota local para chamadas que não são manipuladas pelo tronco SIP do provedor de serviços E9-1-1. Essa rota será usada quando a conexão com o provedor de serviços de E9-1-1 não estiver disponível. 
    
    O exemplo a seguir pressupõe que o usuário tenha o uso "Local" em sua política de voz.
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


