---
title: Implantar Salas do Microsoft Teams com Skype for Business Server
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams com Skype for Business Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 358fa9295ec150f9c57a18252c76d309078b8e29
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503478"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Implantar Salas do Microsoft Teams com Skype for Business Server
  
Este tópico explica como você adiciona uma conta de recurso para Salas do Microsoft Teams quando você tem uma implantação local e de floresta única.
  
Se você tiver uma implantação local de floresta única com o Exchange 2013 SP1 ou posterior e o Skype for Business Server 2015 ou posterior, poderá usar os scripts Windows PowerShell fornecidos para criar contas de dispositivo. Se você estiver usando uma implantação de várias florestas, poderá usar cmdlets equivalentes que produzirão os mesmos resultados. Esses cmdlets são descritos nesta seção.
  
Antes de começar a Salas do Microsoft Teams, certifique-se de ter as permissões certas para executar os cmdlets associados.
  

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

   Observe que $strExchangeServer é o FQDN (nome de domínio totalmente qualificado) do seu servidor Exchange, e $strLyncFQDN é o FQDN da sua implantação Skype for Business Server.

2. Depois de estabelecer uma sessão, você criará uma nova caixa de correio e a habilitará como RoomMailboxAccount ou alterará as configurações de uma caixa de correio de sala existente. Isso permitirá que a conta seja autenticada Salas do Microsoft Teams.

    Se você alterar uma caixa de correio do recurso:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Se você estiver criando uma nova caixa de correio de recurso:

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Você pode definir várias propriedades Exchange na conta Salas do Teams de recursos para melhorar a experiência de reunião para as pessoas. Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. Desativar a expiração de senha na conta de recurso.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. Habilita a conta de recurso no Active Directory para que ela seja autenticada Salas do Microsoft Teams.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. Habilita a conta de recurso com Skype for Business Server habilitando sua Salas do Microsoft Teams do Active Directory em um Skype for Business Server pool:

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    Altere os `-DomainController` atributos `-RegistrarPool` e para os valores apropriados para seu ambiente.

7. **Opcional**. Você também pode permitir Salas do Microsoft Teams fazer e receber chamadas telefônicas PSTN (rede telefônica pública comutado) habilitando Enterprise Voice para sua conta. Enterprise Voice não é um requisito para Salas do Microsoft Teams, mas se você quiser a funcionalidade de discagem PSTN para Salas do Microsoft Teams, veja como habilita-la:

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   Novamente, será necessário substituir o controlador de domínio fornecido e os exemplos de números de telefone por suas próprias informações. O valor do parâmetro $true permanece o mesmo. Você também precisará substituir a política de voz e os nomes da política de plano de discagem.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Exemplo: configuração de conta de sala Exchange e Skype for Business Server local

``` Powershell
New-Mailbox -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) -UserPrincipalName ConferenceRoom01@contoso.com

Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"

Enable-CsMeetingRoom -Identity ConferenceRoom01@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity ConferenceRoom01 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName dk
Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName e15dp2.contoso.com
```

## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
