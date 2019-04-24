---
title: Implantações locais de uma única floresta do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de floresta única.
ms.openlocfilehash: 5fd9ab3f2a2e581f2f1675bea0f663b95cfa3eb5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214993"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Implantações locais de uma única floresta do Sistema de Salas do Skype
 
Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de floresta única.
  
Esta seção fornece uma visão geral das etapas para a conta do sistema de sala do Skype no Exchange Server e do Skype de provisionamento para Business Server hospedado em uma implantação local de floresta única.
  
## <a name="single-forest-on-premises-deployments"></a>Implantações locais de floresta única

Se você já tem uma conta de caixa de correio de recursos para a sala de conferências, pode utilizá-la. Caso contrário, será necessário criar uma nova. Você pode usar o Shell de Gerenciamento do Exchange (PowerShell) ou o Console de Gerenciamento do Exchange para criar uma nova conta de caixa de correio de recursos. É recomendável usar um novo (antiga da caixa de correio de excluir e recriar) caixa de correio de recurso para o sistema de sala Skype. Faça o backup dos dados da caixa de correio antes de excluí-los e, em seguida, exporte-os novamente para a caixa de correio recriada usando o cliente Outlook (consulte Exportar ou fazer backup de mensagens, calendário, tarefas e contatos para obter mais informações). Para restaurar as reuniões perdidas, excluindo a caixa de correio, consulte [Connect ou restauração uma caixa de correio excluída](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Para usar uma conta de caixa de correio de recursos existente (por exemplo, LRS-01), siga as etapas abaixo:
  
1. Execute o seguinte comando do PowerShell de Gerenciamento do Exchange:
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Se você planeja criar uma nova caixa de correio, para uma empresa do Exchange local de floresta única, execute o comando a seguir:
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   O exemplo acima cria uma conta de usuário habilitada no Active Directory e uma caixa de correio para sala de conferência em uma empresa local do Exchange. O parâmetro RoomMailboxPassword especifica a senha para a conta de usuário.
    
3. Configure a conta para solucionar conflitos automaticamente ao aceitar/rejeitar reuniões. Skype sala de conferência equipado com o sistema de sala contas no Exchange podem ser gerenciadas por indivíduos, mas observe que até que a pessoa aceita uma reunião não aparecerá no calendário de tela inicial do sistema de sala do Skype.
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Para ver um conjunto completo de comandos disponíveis, consulte Set-CalendarProcessing.
    
   Para lembrar os organizadores de reuniões para tornar a reunião um Skype on-line para a reunião de negócios no Outlook, execute o seguinte comando para configurar uma dica de email para a nova conta: 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Use os seguintes comandos para configurar sequências de caracteres localizadas. Se for exigido por sua empresa, você pode também adicionar traduções personalizadas: 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Opcional: Configurar reunião texto de aceitação que fornece aos usuários informações sobre Skype para salas de reunião de negócios e o que esperar quando eles agendar e ingressem em reuniões. 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Verifique a Conta da Caixa de Correio de Recursos no Active Directory

A conta da caixa de correio da sala de conferência criada pelo Exchange na etapa 1 acima pode ser um objeto de usuário desativado no Active Directory. Sistema de sala Skype não consigo entrar ou autenticar usando a autenticação Kerberos/NTLM se a conta está desabilitada no Active Directory. Cliente do sistema do Skype sala deve ser capaz de autenticar os serviços Web do Exchange para recuperar as configurações de calendário e também deve ser capaz de enviar um email com o conteúdo do quadro de comunicações. 
  
Portanto, se a conta estiver desativada, você deverá habilitá-la no Active Directory fazendo o seguinte: 
  
1. No Active Directory, execute o seguinte comando para habilitar o login da conta: 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   A execução desse comando solicitará que você insira a senha atual e, em seguida, insira novamente a senha duas vezes para confirmar.
    
2. Após definir a senha, execute o seguinte comando para habilitar a conta: 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Habilitar o sistema de sala Skype contas para o Skype para negócios

Esta seção fornece uma visão geral das etapas necessárias para habilitar Skype for Business para sua conta de sala de conferência, que será configurada no sistema de sala Skype. 
  
Depois de criar uma conta de caixa de correio de recurso para as salas de conferência, use Skype do Shell de gerenciamento do servidor de negócios para habilitar contas de sistema de sala Skype para Skype para serviços corporativos.
  
> [!NOTE]
> O procedimento a seguir pressupõe que você habilitou a conta do sistema de sala do Skype no Active Directory. 
  
1. Execute o seguinte comando para habilitar a conta de sistema do Skype sala em um Skype para pool de servidores de negócios:
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Opcional: permita que essa conta faça e receba chamadas telefônicas PSTN, habilitando a conta para o Enterprise Voice. Enterprise Voice não é necessário para o sistema de sala Skype, mas se você não habilitá-lo para o Enterprise Voice, o cliente do sistema de sala Skype não será capaz de fornecer a funcionalidade de discagem de PSTN:
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se você habilitar o Enterprise Voice para a conta de sala de conferência do sistema de sala do Skype, certifique-se configurar uma política de voz restritos adequado para sua organização. Se o Skype para sala de reunião de negócios é um recurso disponível publicamente, qualquer pessoa pode usá-lo para ingressar em uma reunião, agendada ou ad hoc. Depois de ingressar em uma reunião, a pessoa pode discar para qualquer número. No Skype para Business Server, a discagem de recurso de conferências usa a política de voz do usuário, nesse caso, a conta de sistema de sala Skype usada para ingressar na reunião. Nas versões anteriores do Lync Server, a política de voz do organizador era utilizada. Portanto, se um usuário de uma versão anterior do Microsoft Lync Server agenda uma sala de reunião e convida a conta do sistema do Skype sala sala, qualquer pessoa poderia usar o Skype para negócios sala de reunião para ingressar na reunião e pode discar de qualquer telefone nacionais/regionais ou internacional número, desde que o organizador tem permissão para esses números de discagem. 
  

