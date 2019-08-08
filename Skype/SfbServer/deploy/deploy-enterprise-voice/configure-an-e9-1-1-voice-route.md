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
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Configurar uma rota de voz E9-1-1 no Skype for Business Server
 
Configurar o E9-1-1 roteiros de voz no Skype for Business Server Enterprise Voice. 
  
Para implantar o E9-1-1, é preciso primeiro configurar uma rota de voz de chamada de emergência. Para obter detalhes sobre como criar rotas de voz, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md). É possível definir mais de uma rota se, por exemplo, sua implantação incluir um tronco SIP primário e um secundário. 
  
> [!NOTE]
> Para incluir informações de localização em um E9-1-1 INVITE, você precisa configurar o tronco SIP que se conecta ao provedor de serviços de E9-1-1 para encaminhar as chamadas de emergência através do gateway. Para isso, defina o sinalizador EnablePIDFLOSupport no cmdlet **Set-CsTrunkConfiguration** como True. O valor padrão de EnablePIDFLOSupport é False. Por exemplo: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` não é necessário habilitar os locais de recebimento de gateways PSTN (rede telefônica pública comutada) e gateways de número de identificação de local de emergência (Elin) de fallback.
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Para configurar uma rota de voz de E9-1-1

1. Faça logon no computador com uma conta que seja membro dos grupos RTCUniversalServerAdmins ou membro da função administrativa CsVoiceAdministrator.
    
2.  Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute o cmdlet a seguir para criar um novo registro de uso PSTN. 
    
    Esse deve ser o mesmo nome que você usará para a configuração **PSTN** na política de local. Embora sua implantação tenha vários registros de uso de telefone, o exemplo a seguir adiciona "Uso de emergência" à lista atual de usos de PSTN disponíveis. Para obter detalhes, consulte [Configurar políticas de voz, registros de uso PSTN e rotas de voz no Skype for Business](voice-and-pstn.md).
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Execute o cmdlet a seguir para criar uma nova rota de voz usando o registro de uso PSTN criado na etapa anterior.
    
    O padrão de número deve ser o mesmo usado na configuração de **Cadeia de Caracteres de Discagem de Emergência** na política de local. É necessário um sinal "+" porque o Skype for Business adiciona "+" às chamadas de emergência. "Co1-pstngateway-1" é a ID de serviço do tronco SIP do provedor de serviços de E9-1-1 ou a ID de serviço do gateway ELIN. O exemplo a seguir usa "EmergencyRoute" como o nome da rota de voz.
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. Opcionalmente, para conexões de tronco SIP, recomendamos que você execute o cmdlet a seguir para criar uma rota local para chamadas que não são manipuladas pelo tronco SIP do provedor de serviços E9-1-1. Essa rota será usada quando a conexão com o provedor de serviços de E9-1-1 não estiver disponível. 
    
    O exemplo a seguir pressupõe que o usuário tenha o uso "Local" em sua política de voz.
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


