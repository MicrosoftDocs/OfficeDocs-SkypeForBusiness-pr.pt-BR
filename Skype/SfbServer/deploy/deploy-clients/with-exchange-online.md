---
title: Implantar o Skype Room Systems versão 2 com o Exchange Online
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 com o Exchange Online.
ms.openlocfilehash: dad47f56d96da0f84383b2638684c65554e5a8f9
ms.sourcegitcommit: 4e9f4e2297cea3372a97f4ea178eb75ba6f8753f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2018
ms.locfileid: "19887888"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>Implantar o Skype Room Systems versão 2 com o Exchange Online 
 
Leia este tópico para obter informações sobre como implantar v2 de sistemas de sala Skype com o Exchange Online e Skype para Business Server local.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda as implantações híbridas para sistemas de sala Skype v2 com o Exchange hospedado online. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não é ideal para sua instalação, é recomendável usar o Windows PowerShell para obter o mesmo resultado final conforme documentadas aqui e para obter outras opções de implantação. 

A maneira mais fácil de configurar as contas de usuário é configurá-los usando o Windows PowerShell remoto. A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de v2 Skype sala sistemas compatíveis. Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo v2 de sistemas de sala Skype usará.


  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>Implantar o Skype Room Systems versão 2 com o Exchange Online

Antes de implantar sistemas de sala Skype v2 com o Exchange Online, certifique-se de que você cumpre os requisitos. Para obter mais informações, consulte [requisitos de v2 de sistemas de sala Skype](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Para implantar sistemas de sala Skype v2 com o Exchange Online, siga as etapas abaixo. Verifique se você tem as permissões apropriadas para executar os cmdlets associados. 
  
### <a name="create-an-account-and-set-exchange-properties"></a>Criar uma conta e definir as propriedades do Exchange

1. Iniciar uma sessão remota do Windows PowerShell em um PC e conecte-se ao Exchange Online da seguinte maneira:
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente. Isso permitirá a conta para se autenticar no v2 Skype sistemas de sala.
    
   Se você alterar uma caixa de correio do recurso:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se você estiver criando uma nova caixa de correio de recursos:
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para melhorar a experiência de reunião, você precisará definir as propriedades do Exchange na conta de usuário da seguinte maneira:
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. Você deverá conectar-se ao Azure AD para aplicar algumas configurações à conta. Você poderá executar este cmdlet para se conectar.
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Adicionar um endereço de e-mail à conta de domínio local

1. Na ferramenta de **usuários do Active Directory e computadores AD** , clique com botão direito na pasta ou unidade organizacional que seus sistemas de sala Skype v2 contas serão criadas, clique em **novo**e clique em **usuário**.
    
2. Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.


3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.
    
    > [!NOTE]
    > Selecionando a **senha nunca expira** é um requisito para Skype para Business Server 2015 em sistemas de sala Skype v2. As regras do domínio podem proibir senhas que não expiram. Nesse caso, você precisará criar uma exceção para cada conta de usuário do Skype sala sistemas v2.
  
4. Clique em **Concluir** para criar a conta.
    
5. Depois de criar a conta, execute a sincronização do diretório. Depois de concluir, vá para a página de usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.
    
### <a name="assign-an-office-365-license"></a>Atribuir uma licença do Office 365

1. A conta de usuário precisa ter uma licença válida do Office 365 para garantir que Exchange e Skype para Business Server 2015 funcionará. Se você tiver a licença, você precisa atribuir um local de uso para sua conta de usuário — Isso determina quais SKUs de licença estão disponíveis para sua conta.
    
2. Em seguida, use o Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365.
    
3. Depois de listar as SKUs, você poderá adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a>Habilitar a conta de usuário com o Skype for Business Server 2015

1. Crie uma sessão remota do Windows PowerShell de um PC, da seguinte maneira:
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Para habilitar sua conta do Skype sala sistemas v2 para Skype para Business Server 2015, execute este comando:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Se você não tiver certeza sobre qual valor usar para o parâmetro RegistrarPool no seu ambiente, você pode obter o valor de um existente Skype para usuário Business Server 2015 usando este comando
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a>Atribuir uma licença do Skype for Business Server 2015 a sua conta do Skype Room Systems versão 2

1. Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.
    
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
    
3. Clique na conta de sistemas de sala Skype v2 e, em seguida, clique no ícone de caneta para editar as informações de conta.
    
4. Clique em **Licenças**.
    
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você terá que usar uma licença de plano 3 se você quiser usar o Enterprise Voice em sua v2 Skype sistemas de sala.
    
6. Clique em **Salvar**.
    
Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para fazer logon conta.
  
## <a name="see-also"></a>Consulte também

[Configurar contas para sistemas de sala Skype v2](room-systems-v2-configure-accounts.md)

[Planejar a sala Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implantar Skype sala v2 de sistemas](room-systems-v2.md)
  
[Configurar um console v2 de sistemas de sala do Skype](console.md)
  
[Gerenciar Skype sala v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

