---
title: Implantar Skype sala v2 de sistemas com Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 com Skype para Business Server.
ms.openlocfilehash: 891f716be3a2b7d8479af83b57dfccd70500e50d
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699377"
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a>Implantar Skype sala v2 de sistemas com Skype para Business Server
  
Este tópico explica como adicionar uma conta de dispositivo para sistemas de sala Skype v2 quando você tem uma implantação de floresta única, no local.
  
Se você tiver uma floresta única, a implantação no local com Exchange 2013 SP1 ou posterior e Skype para Business Server 2015 ou posterior, você pode usar os scripts do Windows PowerShell fornecidos para criar contas de dispositivo. Se você estiver usando uma implantação de várias floresta, você pode usar os cmdlets equivalentes que produzirá os mesmos resultados. Esses cmdlets são descritos nesta seção.

A maneira mais fácil de configurar as contas de usuário é configurá-los usando o Windows PowerShell remoto. A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de v2 Skype sala sistemas compatíveis. Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo v2 de sistemas de sala Skype usará.
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a>Implantar Skype sala v2 de sistemas com Skype para Business Server

Antes de implantar sistemas de sala Skype v2 com Skype para Business Server, certifique-se de que você cumpre os requisitos. Para obter mais informações, veja [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Antes de começar a implantar sistemas de sala Skype v2, certifique-se de que você tem as permissões corretas para executar os cmdlets associados.
  
1. Iniciar uma sessão remota do Windows PowerShell a partir de um PC e se conectar ao Exchange. 
    
   ```
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
    
2. Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente. Isso permitirá a conta para se autenticar v2 Skype sistemas de sala.
    
    Se você alterar uma caixa de correio do recurso:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Se você estiver criando uma nova caixa de correio de recursos:
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Você pode definir várias propriedades do Exchange na conta do dispositivo para melhorar a experiência de reunião para as pessoas. Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Se você decidir que a senha não expirar, você pode definir que com os cmdlets do Windows PowerShell muito. Para obter mais informações, confira Gerenciamento de senha.
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Habilite a conta no Active Directory para que ele irá autenticar para sistemas de sala Skype v2.
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Habilite a conta de dispositivo com Skype para Business Server, permitindo que sua conta do Skype sala sistemas v2 do Active Directory em um Skype para pool de servidores de negócios:
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Você deverá usar o endereço do protocolo SIP e o controlador de domínio do projeto 
    
7. **Opcional**. Você também pode permitir que os sistemas de sala Skype v2 fazer e receber telefonemas do telefônica pública comutada (PSTN) de rede, permitindo que o Enterprise Voice para sua conta. Enterprise Voice não é um requisito para sistemas de sala Skype v2, mas se você deseja as funcionalidades de discagem de PSTN para o cliente do Skype sala sistemas v2, aqui está como ativá-la:
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Novamente, será necessário substituir o controlador de domínio fornecido e os exemplos de números de telefone por suas próprias informações. O valor do parâmetro $true permanece o mesmo.
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Exemplo: configuração de conta de sala no Exchange e Skype para Business Server no local

```
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

## <a name="see-also"></a>Consulte também

[Configurar contas para sistemas de sala Skype v2](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implantar o Skype Room Systems versão 2](room-systems-v2.md)
  
[Configurar o console do Skype Room Systems versão 2](console.md)
  
[Gerenciar o Skype Room Systems versão 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)