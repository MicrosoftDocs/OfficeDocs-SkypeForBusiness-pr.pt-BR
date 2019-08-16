---
title: Implantar salas do Microsoft Teams com o Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Skype for Business Server.
ms.openlocfilehash: 0c970adeae5531b76b1ebfe55ab750efe8bd3ba3
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427758"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Implantar salas do Microsoft Teams com o Skype for Business Server
  
Este tópico explica como adicionar uma conta de dispositivo para as salas do Microsoft Teams quando você tem uma implantação em uma única floresta local.
  
Se você tiver uma implantação local de uma única floresta com o Exchange 2013 SP1 ou posterior e o Skype for Business Server 2015 ou posterior, poderá usar os scripts do Windows PowerShell fornecidos para criar contas de dispositivo. Se você estiver usando uma implantação de várias florestas, poderá usar cmdlets equivalentes que produzirão os mesmos resultados. Esses cmdlets são descritos nesta seção.

  
Antes de começar a implantar salas do Microsoft Teams, certifique-se de ter as permissões corretas para executar os cmdlets associados.
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   Observe que $strExchangeServer é o nome de domínio totalmente qualificado (FQDN) do seu servidor Exchange e $strLyncFQDN é o FQDN da implantação do Skype for Business Server.

2. Depois de estabelecer uma sessão, você criará uma nova caixa de correio e a habilitará como uma RoomMailboxAccount ou alterará as configurações de uma caixa de correio de sala existente. Isso permitirá que a conta seja autenticada para salas do Microsoft Teams.

    Se você alterar uma caixa de correio do recurso:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Se você estiver criando uma nova caixa de correio de recurso:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Você pode definir várias propriedades do Exchange na conta do dispositivo para melhorar a experiência de reunião para as pessoas. Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Se você decidir que a senha não expira, é possível configurá-la com cmdlets do Windows PowerShell também. Para obter mais informações, confira Gerenciamento de senha.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Habilite a conta no Active Directory para que ela seja autenticada para salas do Microsoft Teams.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Habilite a conta do dispositivo com o Skype for Business Server habilitando sua conta do Active Directory de salas do Microsoft Teams em um pool de servidores do Skype for Business:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Você deverá usar o endereço do protocolo SIP e o controlador de domínio do projeto

7. **Opcional**. Você também pode permitir que as salas do Microsoft Teams façam e recebam chamadas telefônicas PSTN (rede telefônica pública comutada) habilitando o Enterprise Voice para a sua conta. O Enterprise Voice não é um requisito para salas do Microsoft Teams, mas se você quiser a funcionalidade de discagem PSTN para o cliente de salas do Microsoft Teams, veja como habilitá-lo:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Novamente, será necessário substituir o controlador de domínio fornecido e os exemplos de números de telefone por suas próprias informações. O valor do parâmetro $true permanece o mesmo.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Exemplo: configuração da conta de sala no Exchange e no Skype for Business Server no local

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="see-also"></a>Confira também

[Configurar contas para salas do Microsoft Teams](room-systems-v2-configure-accounts.md)

[Plano para salas do Microsoft Teams](skype-room-systems-v2-0.md)
  
[Implantar salas do Microsoft Teams](room-systems-v2.md)
  
[Configurar um console de salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)
