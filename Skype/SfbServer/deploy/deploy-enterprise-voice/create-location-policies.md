---
title: Criar políticas de localização em Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Leia este tópico para saber como configurar políticas de local de serviço de emergência aprimorado (E9-1-1) em Skype for Business Server Enterprise Voice.
---

# <a name="create-location-policies-in-skype-for-business-server"></a>Criar políticas de localização em Skype for Business Server

Leia este tópico para saber como configurar políticas de local de serviço de emergência aprimorado (E9-1-1) em Skype for Business Server Enterprise Voice. 

Skype for Business Server usa uma política de local para habilitar Skype for Business clientes do E9-1-1 durante o registro do cliente. Uma política de localização contém as configurações que definem como o E9-1-1 será implementado. Para obter mais informações, consulte [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).

Você define políticas de localização usando o Painel de Controle Skype for Business ou usando o cmdlet [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps).

> [!NOTE]
> Skype for Business Server agora suporta a configuração de vários números de emergência para um cliente. Se você quiser configurar vários números de emergência, siga as informações em [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md). 

É possível editar a política de localização global e criar novas políticas de localização sinalizadas. Um cliente obtém uma política global quando não está localizado dentro de uma subrede com uma política de localização associada ou quando o cliente não foi atribuído diretamente com uma política de localização. As políticas sinalizadas são atribuídas à subredes ou usuários. 

Para criar uma política de localização, você deve usar uma conta membro do grupo RTCUniversalServerAdmins, membro da função administrativa CsVoiceAdministrator ou com direitos e permissões de administrador equivalentes.

Para obter mais informações, consulte [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). Os cmdlets neste procedimento usam uma política de local definida usando os seguintes valores. Para uma descrição completa dos parâmetros e valores do cmdlet, consulte [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps).


| **Elemento**                               | **Valor**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **Verdadeiro** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **Aviso de isenção** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | Sua empresa exige a definição de uma localização. Se você não a definir, os serviços de emergência não poderão localizá-lo em caso de emergência. Defina uma localização.  <br/> |
| UseLocationForE911Only  <br/>             | **Falso** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>Para criar políticas de localização

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.

    > [!NOTE]
    > O CsLocationPolicy irá falhar se a configuração do **PstnUsage** ainda não estiver na lista Global de PstnUsages.

2. Opcionalmente, execute o seguinte cmdlet para editar a política de localização global:

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. Execute o seguinte para criar uma política de localização sinalizada.

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. Execute o seguinte cmdlet para aplicar a política de localização sinalizada criada na etapa 3 em uma política de usuário.

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```