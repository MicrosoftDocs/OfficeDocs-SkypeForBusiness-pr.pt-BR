---
title: Implantações locais de uma única floresta do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de floresta única.
ms.openlocfilehash: 107d4724defa11cbe506dcfa1b4f3c4725ee9910
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245863"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Implantações locais de uma única floresta do Sistema de Salas do Skype
 
Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de floresta única.
  
Esta seção fornece uma visão geral das etapas para provisionar a conta do sistema de sala do Skype no Exchange Server e no Skype for Business Server hospedada em uma única implantação local da floresta.
  
## <a name="single-forest-on-premises-deployments"></a>Implantações locais de floresta única

Se você já tem uma conta de caixa de correio de recursos para a sala de conferências, pode utilizá-la. Caso contrário, será necessário criar uma nova. Você pode usar o Shell de Gerenciamento do Exchange (PowerShell) ou o Console de Gerenciamento do Exchange para criar uma nova conta de caixa de correio de recursos. Recomendamos usar uma nova caixa de correio de recurso (excluir caixa de correio antiga e recriar) para o sistema de sala do Skype. Faça o backup dos dados da caixa de correio antes de excluí-los e, em seguida, exporte-os novamente para a caixa de correio recriada usando o cliente Outlook (consulte Exportar ou fazer backup de mensagens, calendário, tarefas e contatos para obter mais informações). Para restaurar as reuniões perdidas excluindo a caixa de correio, consulte [conectar ou restaurar uma caixa de correio excluída](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
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
    
3. Configure a conta para solucionar conflitos automaticamente ao aceitar/rejeitar reuniões. Sala de reuniões do Skype-as contas da sala de conferências equipadas no Exchange podem ser gerenciadas por indivíduos, mas observe que, até que a pessoa aceite uma reunião, ela não aparecerá no calendário da tela inicial do Skype Room System.
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Para ver um conjunto completo de comandos disponíveis, consulte Set-CalendarProcessing.
    
   Para lembrar os organizadores da reunião para que a reunião seja uma reunião online do Skype for Business no Outlook, execute o seguinte comando para configurar uma dica de tela para a nova conta: 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Use os seguintes comandos para configurar sequências de caracteres localizadas. Se for exigido por sua empresa, você pode também adicionar traduções personalizadas: 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Opcional: configurar o texto de aceitação da reunião que fornece aos usuários informações sobre a sala de reunião do Skype for Business e o que esperar quando agendar e ingressar em reuniões. 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Verifique a Conta da Caixa de Correio de Recursos no Active Directory

A conta da caixa de correio da sala de conferência criada pelo Exchange na etapa 1 acima pode ser um objeto de usuário desativado no Active Directory. O sistema de sala da Skype não pode entrar ou autenticar usando a autenticação Kerberos/NTLM se a conta estiver desabilitada no Active Directory. O cliente do sistema de sala do Skype deve ser capaz de se autenticar nos serviços Web do Exchange para recuperar as configurações do calendário e também deve ser capaz de enviar emails com conteúdo do whiteboard. 
  
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

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Como habilitar contas do sistema de sala do Skype para o Skype for Business

Esta seção fornece uma visão geral das etapas necessárias para habilitar o Skype for Business para a sua conta de sala de conferência, que será configurada no sistema de salas da Skype. 
  
Depois de criar uma conta de caixa de correio de recursos para as salas de conferência, use o Shell de gerenciamento do Skype for Business Server para habilitar as contas do sistema de sala do Skype para serviços do Skype for Business.
  
> [!NOTE]
> O procedimento a seguir pressupõe que você habilitou a conta do sistema de sala do Skype no Active Directory. 
  
1. Execute o seguinte comando para habilitar a conta do sistema de sala do Skype em um pool do servidor do Skype for Business:
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Opcional: permita que essa conta faça e receba chamadas telefônicas PSTN, habilitando a conta para o Enterprise Voice. O Enterprise Voice não é necessário para o sistema de sala da Skype, mas se você não habilitá-lo para o Enterprise Voice, o cliente do sistema de sala do Skype não poderá fornecer funcionalidade de discagem PSTN:
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se você habilitar o Enterprise Voice para a conta da sala de conferências do Skype Room System, certifique-se de configurar uma política de voz restrita adequada para a sua organização. Se a sala de reunião do Skype for Business for um recurso disponível publicamente, qualquer pessoa poderá usá-lo para ingressar em uma reunião, seja agendada ou ad hoc. Depois de ingressar em uma reunião, a pessoa pode discar para qualquer número. No Skype for Business Server, o recurso discagem de conferências usa a política de voz do usuário, nesse caso, a conta do sistema de sala do Skype usada para ingressar na reunião. Nas versões anteriores do Lync Server, a política de voz do organizador era utilizada. Portanto, se um usuário de uma versão anterior do Lync Server agendar uma sala de reunião e convidar a conta da sala do sistema de sala da Skype, qualquer pessoa poderá usar a sala de reunião do Skype for Business para participar da reunião e poderá discar para qualquer telefone nacional/regional ou internacional número, desde que o organizador tenha permissão para discar esses números. 
  

