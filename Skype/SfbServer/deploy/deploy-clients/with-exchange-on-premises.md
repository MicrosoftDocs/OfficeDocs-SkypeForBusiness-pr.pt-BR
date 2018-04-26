---
title: Implantar o Skype Room Systems versão 2 com o Exchange no local (Híbrida)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: Leia este tópico para obter informações sobre como implantar o  em um ambiente híbrido com o  no local.
ms.openlocfilehash: a0a53b7f8be916d1c0c1a69a23a0f8c604420d9a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises-hybrid"></a>Implantar o Skype Room Systems versão 2 com o Exchange no local (Híbrida)
 
Leia este tópico para obter informações sobre como implantar o  em um ambiente híbrido com o  no local.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se ele não for adequado a sua configuração, recomendamos usar o  para obter o mesmo resultado final e para outras opções de implantação. You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup. (Veja Script de verificação de conta.)
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Implantar o Skype Room Systems versão 2 com o Exchange no local

Antes de implantar o  com o  no local, verifique se os requisitos foram atendidos. For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Se você estiver implantando o  com o  no local, usará as ferramentas administrativas do Active Directory para adicionar um endereço de email à conta de domínio local. Essa conta será sincronizada com o . Você deverá:
  
- Criar uma conta e sincronizá-la com o Active Directory.
    
- Habilitar a caixa de correio remota e as propriedades definidas.
    
- Atribuir uma licença do Office 365
    
- Habilitar a conta de dispositivo com o Skype for Business Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:
    
  - You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan. O plano precisa dar suporte à funcionalidade de conferência.
    
  - If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).
    
  - Os usuários de locatário devem ter caixas de correio do .
    
  - Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.
    
- Atribuir uma licença do Skype for Business Server 2015 a sua conta do Skype Room Systems versão 2
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a>Criar uma conta e sincronizá-la com o Active Directory

1. Na ferramenta Usuários e Computadores do Active Directory, clique com o botão direito do mouse na pasta ou na Unidade Organizacional em que as contas do  serão criadas, clique em Novo e em Usuário.
    
2. Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.
    
3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.
    
    > [!NOTE]
    > Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2. As regras do domínio podem proibir senhas que não expiram. Nesse caso, você deverá criar uma exceção para cada conta de dispositivo do .
  
4. Depois de criar a conta, execute a sincronização do diretório. Após a conclusão, vá para a página de usuários no Centro de administração do  e verifique se a conta criada nas etapas anteriores foi mesclada com a conta online.
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar a caixa de correio remota e as propriedades definidas

1. Habilite a caixa de correio remota abrindo o shell de gerenciamento do  no local com permissões de administrador e execute o seguinte comando:
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -RemoteRoutingAddress 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. Start a remote Windows PowerShell session and connect to Microsoft Exchange. No locatário do , execute os seguintes comandos:
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://outlook.office365.com/ps1-liveid/' -Credential $cred -Authentication Basic -AllowRedirection 
   Import-PSSession $sess
   ```

3. Para aprimorar a experiência de reunião, será necessário definir as propriedades do  na conta de dispositivo, como a seguir:
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    Para obter mais informações sobre propriedades que precisam ser definidas, consulte as propriedades do .
    
4. Você deverá conectar-se ao Azure AD para aplicar algumas configurações à conta. Você pode executar este comando para se conectar:
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a>Atribuir uma licença do Office 365

1. The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).
    
2. Em seguida, use Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do .
    
3. Depois de listar as SKUs, você poderá adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a>Habilitar a conta de dispositivo com o Skype for Business

1. Crie uma sessão remota do  em um computador, como a seguir:
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Se você não tem certeza sobre o valor que deve usar no parâmetro RegistrarPool em seu ambiente, pode obter o valor de um usuário do  existente usando este comando:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a>Atribuir uma licença do Skype for Business a sua conta do Skype Room Systems versão 2

1. Faça logon como administrador do locatário, abra o portal de administração do  e clique no aplicativo Administrador.
    
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
    
3. Clique na conta do  e clique no ícone de caneta para editar as informações da conta.
    
4. Clique em **Licenças**.
    
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Se quiser usar o Enterprise Voice no , será necessário usar uma licença com o Plano 3.
    
6. Clique em **Salvar**.
    
Para validação, você deverá ser capaz de usar qualquer cliente do  para fazer logon nessa conta.
  
## <a name="see-also"></a>Consulte também

#### 

[Planejar o Skype Room Systems versão 2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implantar o Skype Room Systems versão 2](room-systems-v2.md)
  
[Configurar o console do Skype Room Systems versão 2](console.md)
  
[Gerenciar o Skype Room Systems versão 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

