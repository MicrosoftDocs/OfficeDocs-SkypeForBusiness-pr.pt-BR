---
title: Configurar uma rota de voz do E9-1-1 no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configure rotas de voz do E9-1-1 no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: c31ac7c264fb931c127375eca5a383d10998c3f1
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server-2015"></a>Configurar uma rota de voz do E9-1-1 no Skype for Business Server 2015
 
Configure rotas de voz do E9-1-1 no Skype para Business Server Enterprise Voice. 
  
Para implantar o E9-1-1, é preciso primeiro configurar uma rota de voz de chamada de emergência. Para obter detalhes sobre a criação de rotas de voz, consulte [criar ou modificar uma rota de voz no Skype para negócios 2015](create-or-modify-a-voice-route.md). É possível definir mais de uma rota se, por exemplo, sua implantação incluir um tronco SIP primário e um secundário. 
  
> [!NOTE]
> Para incluir informações de localização em um E9-1-1 INVITE, você precisa configurar o tronco SIP que se conecta ao provedor de serviços de E9-1-1 para encaminhar as chamadas de emergência através do gateway. Para fazer isso, defina o sinalizador EnablePIDFLOSupport no cmdlet **Set-CsTrunkConfiguration** como True. O valor padrão de EnablePIDFLOSupport é False. Por exemplo: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` não é necessário habilitar o recebimento locais para pública fallback comutada gateways do telefone PSTN (rede) e gateways ELIN Emergency Location Identification número ().
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Para configurar uma rota de voz de E9-1-1

1. Faça logon no computador com uma conta que seja membro dos grupos RTCUniversalServerAdmins ou membro da função administrativa CsVoiceAdministrator.
    
2.  Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute o cmdlet a seguir para criar um novo registro de uso PSTN. 
    
    Esse deve ser o mesmo nome que você usará para a configuração **PSTN** na política de local. Embora sua implantação tenha vários registros de uso de telefone, o exemplo a seguir adiciona "Uso de emergência" à lista atual de usos de PSTN disponíveis. Para obter detalhes, consulte [Configure políticas de voz, registros de uso do PSTN e rotas de voz no Skype para negócios 2015](voice-and-pstn.md).
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Execute o cmdlet a seguir para criar uma nova rota de voz usando o registro de uso PSTN criado na etapa anterior.
    
    O padrão de número deve ser o mesmo usado na configuração de **Cadeia de Caracteres de Discagem de Emergência** na política de local. Um sinal de "+" é necessária porque Skype para negócios adiciona "+" para chamadas de emergência. "Co1-pstngateway-1" é a ID de serviço do tronco SIP do provedor de serviços de E9-1-1 ou a ID de serviço do gateway ELIN. O exemplo a seguir usa "EmergencyRoute" como o nome da rota de voz.
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

   ```

5. Opcionalmente, para conexões de tronco SIP, recomendamos que você execute o seguinte cmdlet para criar uma rota local para chamadas que não são manipuladas pelo tronco SIP do provedor de serviços E9-1-1. Essa rota será usada quando a conexão com o provedor de serviços de E9-1-1 não estiver disponível. 
    
    O exemplo a seguir pressupõe que o usuário tenha o uso "Local" em sua política de voz.
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


