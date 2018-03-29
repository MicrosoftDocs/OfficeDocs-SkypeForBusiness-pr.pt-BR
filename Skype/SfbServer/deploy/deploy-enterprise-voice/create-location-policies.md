---
title: Criar políticas de localização no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Leia este tópico para saber como configurar aprimorada políticas de local de serviço de emergência (E9-1-1) em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 7635199810e21f33bdbe30d5bf6f229987fa8c77
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="create-location-policies-in-skype-for-business-server-2015"></a>Criar políticas de localização no Skype for Business Server 2015
 
Leia este tópico para saber como configurar aprimorada políticas de local de serviço de emergência (E9-1-1) em Skype para Business Server Enterprise Voice. 
  
Skype para Business Server usa uma política de local para habilitar o Skype para clientes corporativos para E9-1-1 durante o registro de cliente. Uma política de local contém as configurações que definem como o serviço E9-1-1 será implementado. Para obter mais informações, consulte [planejar políticas de local para Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).
  
Defina as políticas de local usando o Skype para painel de controle corporativos ou usando o cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .
  
> [!NOTE]
> Skype para Business Server agora oferece suporte a configuração de vários números de emergências para um cliente. Se você deseja configurar vários números de emergências, você deve seguir as informações em [vários números de emergências Skype para Business Server 2015 planejar](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) e [Configurar vários números de emergências Skype para negócios 2015](configure-multiple-emergency-numbers.md). 
  
É possível editar a política de localização global e criar novas políticas de localização sinalizadas. Um cliente obtém uma política global quando não está localizado dentro de uma sub-rede com uma política de localização associada ou quando o cliente não foi atribuído diretamente com uma política de localização. As políticas sinalizadas são atribuídas à sub-redes ou usuários.   
  
Para criar uma política de localização, você deve usar uma conta membro do grupo RTCUniversalServerAdmins, membro da função administrativa CsVoiceAdministrator ou com direitos e permissões de administrador equivalentes.
  
Para obter mais informações, consulte [planejar políticas de local para Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). Os cmdlets contidos neste procedimento usam uma política de local definida com os valores a seguir. Para obter uma descrição completa dos valores e de parâmetros do cmdlet, consulte [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).
  
|**Elemento**|**Valor**|
|:-----|:-----|
|EnhancedEmergencyServicesEnabled  <br/> |**True** <br/> |
|LocationRequired  <br/> |**Disclaimer** <br/> |
|EnhancedEmergencyServiceDisclaimer  <br/> |Sua empresa exige a definição de uma localização. Se você não a definir, os serviços de emergência não poderão localizá-lo em caso de emergência. Defina uma localização.  <br/> |
|UseLocationForE911Only  <br/> |**False** <br/> |
|PstnUsage  <br/> |**EmergencyUsage** <br/> |
|EmergencyDialString  <br/> |**911** <br/> |
|EmergencyDialMask  <br/> |**112** <br/> |
|NotificationUri  <br/> |**SIP:Security@litwareinc.com** <br/> |
|ConferenceUri  <br/> |**SIP:+14255550123@litwareinc.com** <br/> |
|ConferenceMode  <br/> |**twoway** <br/> |
|LocationRefreshInterval  <br/> |**2** <br/> |
   
### <a name="to-create-location-policies"></a>Para criar políticas de localização

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
    > [!NOTE]
    > O CsLocationPolicy irá falhar se a configuração do **PstnUsage** ainda não estiver na lista Global de PstnUsages.
  
2. Opcionalmente, execute o seguinte cmdlet para editar a política de localização global:
    
   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

   ```

3. Execute o seguinte para criar uma política de localização sinalizada.
    
   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

   ```

4. Execute o seguinte cmdlet para aplicar a política de localização sinalizada criada na etapa 3 em uma política de usuário.
    
   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```


