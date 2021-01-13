---
title: Implantações locais de floresta única do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente local de floresta única.
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820751"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Implantações locais de floresta única do Sistema de Sala do Skype
 
Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente local de floresta única.
  
Esta seção fornece uma visão geral das etapas para provisionar a conta do Sistema de Sala do Skype no Exchange Server e no Skype for Business Server hospedado em uma implantação local de floresta única.
  
## <a name="single-forest-on-premises-deployments"></a>Implantação de uma única floresta no local

Se você já tiver uma conta de caixa de correio de recursos para a sala de conferência, poderá usá-la. Caso contrário, você precisará criar um novo. Você pode usar o Shell de Gerenciamento do Exchange (PowerShell) ou o Console de Gerenciamento do Exchange para criar uma nova conta de caixa de correio de recurso. Recomendamos usar uma nova caixa de correio de recurso (excluir a caixa de correio antiga e re-criar) para o Sistema de Sala do Skype. Certifique-se de fazer o back up de dados de caixa de correio antes de excluir e exportá-los de volta para a caixa de correio criada novamente usando o cliente outlook (consulte Exportar ou fazer o back up de mensagens, calendário, tarefas e contatos para obter mais informações). Para restaurar as reuniões perdidas pela exclusão da caixa de correio, consulte [Conectar ou restaurar uma caixa de correio excluída.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx) 
  
Para usar uma conta de caixa de correio de recurso existente (por exemplo, LRS-01), siga as etapas abaixo:
  
1. Execute o seguinte comando do PowerShell de Gerenciamento do Exchange:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Se você planeja criar uma nova caixa de correio, para uma organização local de floresta única do Exchange, execute o seguinte comando:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   O exemplo acima cria uma conta de usuário habilitada no Active Directory e uma caixa de correio de sala para uma sala de conferência em uma organização local do Exchange. O parâmetro RoomMailboxPassword especifica a senha da conta de usuário.
    
3. Configure a conta para resolver automaticamente conflitos aceitando/rejeitando reuniões. As contas da sala de conferência equipados com o Sistema de Sala do Skype no Exchange podem ser gerenciadas por indivíduos, mas observe que até que o indivíduo aceite uma reunião, ela não aparecerá no calendário da tela inicial do Sistema de Sala do Skype.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Para um conjunto completo de comandos disponíveis, consulte Set-CalendarProcessing.
    
   Para lembrar os organizadores da reunião de tornar a reunião uma reunião online do Skype for Business no Outlook, execute o seguinte comando para configurar uma Dica de Email para a nova conta: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Use os comandos a seguir para configurar cadeias de caracteres localizadas. Se for exigido pela sua organização, você também poderá adicionar traduções personalizadas: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Opcional: configure o texto de aceitação da reunião que fornece aos usuários informações sobre a Sala de Reunião do Skype for Business e o que esperar ao agendar e ingressar em reuniões. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Verificar Conta de Caixa de Correio de Recurso no Active Directory

A conta de caixa de correio de sala de conferência criada pelo Exchange na etapa 1 acima pode ser um objeto de usuário desabilitado no Active Directory. O Sistema de Sala do Skype não pode entrar ou autenticar usando a autenticação Kerberos/NTLM se a conta estiver desabilitada no Active Directory. O cliente do Sistema de Sala do Skype deve ser capaz de se autenticar nos Serviços Web do Exchange para recuperar as configurações de calendário e também deve ser capaz de enviar emails com o conteúdo do quadro de mensagens. 
  
Portanto, se a conta estiver desabilitada, você deverá habilitar essa conta no Active Directory fazendo o seguinte: 
  
1. No Active Directory, execute o seguinte comando para habilitar o logoff da conta: 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   A execução desse comando solicitará que você insira a senha atual e, em seguida, insira a senha duas vezes para confirmação.
    
2. Depois que a senha for definida, execute o seguinte comando para habilitar a conta: 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Habilitando contas do Sistema de Sala do Skype para o Skype for Business

Esta seção fornece uma visão geral das etapas necessárias para habilitar o Skype for Business para sua conta de sala de conferência, que será configurada no Sistema de Sala do Skype. 
  
Depois de criar uma conta de caixa de correio de recursos para as salas de conferência, use o Shell de Gerenciamento do Skype for Business Server para habilitar as contas do Sistema de Salas do Skype para os serviços do Skype for Business.
  
> [!NOTE]
> O procedimento a seguir presume que você tenha habilitado a conta do Sistema de Sala do Skype no Active Directory. 
  
1. Execute o seguinte comando para habilitar a conta do Sistema de Sala do Skype em um pool do Skype for Business Server:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Opcional: permita que esta conta faça e receba chamadas telefônicas PSTN habilitando a conta para o Enterprise Voice. O Enterprise Voice não é necessário para o Sistema de Sala do Skype, mas se você não habilita-o para o Enterprise Voice, o cliente do Sistema de Sala do Skype não poderá fornecer a funcionalidade de discagem PSTN:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se você habilitar o Enterprise Voice para a conta da sala de conferência do Sistema de Sala do Skype, configure uma Política de Voz restrita adequada para sua organização. Se a Sala de Reunião do Skype for Business for um recurso publicamente disponível, qualquer pessoa poderá usá-la para ingressar em uma reunião, agendada ou ad hoc. Depois de ingressar em uma reunião, a pessoa pode discar para qualquer número. No Skype for Business Server, o recurso discagem de conferências usa a política de voz do usuário, neste caso, a conta do Sistema de Sala do Skype usada para ingressar na reunião. Em versões anteriores do Lync Server, a política de voz do organizador é usada. Portanto, se um usuário de uma versão anterior do Lync Server agendar uma sala de reunião e convidar a conta da sala do Sistema de Sala do Skype, qualquer pessoa poderá usar a Sala de Reunião do Skype for Business para participar da reunião e pode discar qualquer número de telefone nacional/regional ou internacional, desde que o organizador tenha permissão para discar esses números. 
  

