---
title: Implantar salas de equipes da Microsoft com Skype para Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Leia este tópico para obter informações sobre como implantar o Microsoft salas de equipes com Skype para Business Server.
ms.openlocfilehash: f62006dc3f83d6f60c224f8e75ba4958ff0a7bfc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915793"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Implantar salas de equipes da Microsoft com Skype para Business Server
  
Este tópico explica como adicionar uma conta de dispositivo para salas de equipes da Microsoft quando você tem uma implantação de floresta única, no local.
  
Se você tiver uma floresta única, a implantação no local com Exchange 2013 SP1 ou posterior e Skype para Business Server 2015 ou posterior, você pode usar os scripts do Windows PowerShell fornecidos para criar contas de dispositivo. Se você estiver usando uma implantação de várias floresta, você pode usar os cmdlets equivalentes que produzirá os mesmos resultados. Esses cmdlets são descritos nesta seção.

  
Antes de começar a implantar o Microsoft equipes salas, certifique-se de que você tem as permissões corretas para executar os cmdlets associados.
  

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

   Observe que $strExchangeServer é o nome de domínio totalmente qualificado (FQDN) do seu servidor Exchange e $strLyncFQDN é o FQDN do seu Skype para implantação de servidor de negócios.

2. Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente. Isso permitirá a conta autenticar a salas de equipes da Microsoft.

    Se você alterar uma caixa de correio do recurso:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Se você estiver criando uma nova caixa de correio de recursos:

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

4. Se você decidir que a senha não expirar, você pode definir que com os cmdlets do Windows PowerShell muito. Para obter mais informações, confira Gerenciamento de senha.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Habilite a conta no Active Directory para que ele irá autenticar a salas de equipes da Microsoft.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Habilite a conta de dispositivo com Skype para Business Server, permitindo que sua conta do Active Directory do Microsoft equipes salas em um Skype para pool de servidores de negócios:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Você deverá usar o endereço do protocolo SIP e o controlador de domínio do projeto

7. **Opcional**. Você também pode permitir salas de equipes da Microsoft fazer e receber telefonemas do telefônica pública comutada (PSTN) de rede, permitindo que o Enterprise Voice para sua conta. Enterprise Voice não é um requisito para salas de equipes da Microsoft, mas se você deseja as funcionalidades de discagem de PSTN para o cliente Microsoft equipes salas, aqui está como ativá-la:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Novamente, será necessário substituir o controlador de domínio fornecido e os exemplos de números de telefone por suas próprias informações. O valor do parâmetro $true permanece o mesmo.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Exemplo: configuração de conta de sala no Exchange e Skype para Business Server no local

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

[Configurar contas para salas de equipes da Microsoft](room-systems-v2-configure-accounts.md)

[Planejar para salas de equipes da Microsoft](skype-room-systems-v2-0.md)
  
[Implantar salas de equipes da Microsoft](room-systems-v2.md)
  
[Configurar um console de salas de equipes da Microsoft](console.md)
  
[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)
