---
title: Implantar salas de equipes da Microsoft com o Exchange Online
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
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leia este tópico para obter informações sobre como implantar as salas de equipes da Microsoft com o Exchange Online.
ms.openlocfilehash: b00a4e09a74cabc7a47879eea3d075220245c704
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835294"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implantar salas de equipes da Microsoft com o Exchange Online

Leia este tópico para obter informações sobre como implantar o Microsoft salas de equipes com o Exchange Online e Skype para Business Server local.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda as implantações híbridas para salas de equipes da Microsoft com o Exchange hospedado online. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não é ideal para sua instalação, é recomendável usar o Windows PowerShell para obter o mesmo resultado final conforme documentadas aqui e para obter outras opções de implantação.

A maneira mais fácil de configurar as contas de usuário é configurá-los usando o Windows PowerShell remoto. A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de salas de equipes da Microsoft compatíveis. Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo de salas de equipes da Microsoft usará.

## <a name="requirements"></a>Requisitos

Antes de implantar salas de equipes da Microsoft com o Exchange Online, certifique-se de que você cumpre os requisitos. Para obter mais informações, consulte [requisitos de salas de equipes da Microsoft](requirements.md).
  
Para implantar as salas de equipes da Microsoft com o Exchange Online, siga as etapas abaixo. Verifique se você tem as permissões apropriadas para executar os cmdlets associados.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Criar uma conta e definir as propriedades do Exchange

1. Iniciar uma sessão remota do Windows PowerShell em um PC e conecte-se ao Exchange Online da seguinte maneira:

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente. Isso permitirá a conta autenticar em salas de equipes da Microsoft.

   Se você alterar uma caixa de correio do recurso:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se você estiver criando uma nova caixa de correio de recursos:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para melhorar a experiência de reunião, você precisará definir as propriedades do Exchange na conta de usuário da seguinte maneira:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Adicionar um endereço de e-mail à conta de domínio local

1. Na ferramenta de **usuários do Active Directory e computadores AD** , clique com botão direito no contêiner ou unidade organizacional que suas salas de equipes da Microsoft contas serão criadas, clique em **novo**e, em seguida, clique em **usuário**.
2. Digite o nome de exibição (-Identity) do cmdlet anterior (Set-Mailbox ou New-Mailbox) na caixa **nome completo** e o alias na caixa **nome de logon do usuário** . Clique em **Avançar**.
3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionando a **senha nunca expira** é um requisito para Skype para Business Server em salas de equipes da Microsoft. As regras do domínio podem proibir senhas que não expiram. Nesse caso, você precisará criar uma exceção para cada conta de usuário de salas de equipes da Microsoft.
  
4. Clique em **Concluir** para criar a conta.
5. Depois de criar a conta, execute a sincronização do diretório. Depois de concluir, vá para a página de usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.

### <a name="assign-an-office-365-license"></a>Atribuir uma licença do Office 365

1. Primeiro, conecte-se para o Windows Azure AD para aplicar algumas configurações de conta. Você poderá executar este cmdlet para se conectar. Para obter detalhes sobre o Active Directory, consulte o [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > Não há suporte para o [Windows Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) . 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. A conta de usuário precisa ter uma licença válida do Office 365 para garantir que Exchange e Skype para Business Server funcionará. Se você tiver a licença, você precisa atribuir um local de uso para sua conta de usuário — Isso determina quais SKUs de licença estão disponíveis para sua conta. Você vai fazer a atribuição em uma etapa a seguir.
3. Em seguida, usar`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365.
4. Depois que você lista check-out SKUs do, você pode adicionar uma licença usando o`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK). 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Habilitar a conta de usuário com Skype para Business Server

1. Crie uma sessão remota do Windows PowerShell de um PC, da seguinte maneira:

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Para habilitar sua conta de salas de equipes da Microsoft para Skype para Business Server, execute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Se você não tiver certeza sobre qual valor usar para o parâmetro RegistrarPool no seu ambiente, você pode obter o valor de um existente Skype para usuário Business Server usando este comando

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Atribuir um Skype licença Business Server à sua conta de salas de equipes da Microsoft

1. Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
3. Clique na conta de salas de equipes da Microsoft e clique no ícone de caneta para editar as informações de conta.
4. Clique em **Licenças**.
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você terá que usar uma licença de plano 3 se você quiser usar o Enterprise Voice em salas de equipes da Microsoft.
6. Clique em **Salvar**.

Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para fazer logon conta.
  
## <a name="see-also"></a>Confira também

[Configurar contas para salas de equipes da Microsoft](room-systems-v2-configure-accounts.md)

[Planejar para salas de equipes da Microsoft](skype-room-systems-v2-0.md)
  
[Implantar salas de equipes da Microsoft](room-systems-v2.md)
  
[Configurar um console de salas de equipes da Microsoft](console.md)
  
[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)
