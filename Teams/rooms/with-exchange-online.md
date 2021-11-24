---
title: Implantar as Salas do Microsoft Teams com o Exchange Online
ms.author: dstrome
author: dstrome
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
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams com Exchange Online e Skype for Business Server local.
ms.openlocfilehash: 7e80da026164fc2b1feba3d03c220e4622454e49
ms.sourcegitcommit: 95c7603b47fcd5fba8f762a4590693ee9f026328
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2021
ms.locfileid: "61153284"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implantar as Salas do Microsoft Teams com o Exchange Online

Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams com Exchange Online e Skype for Business Server local.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda implantações híbridas para Salas do Microsoft Teams com Exchange hospedado online. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não estiver correto para sua instalação, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final como documentado aqui e para outras opções de implantação.

A maneira mais fácil de configurar contas de usuário é configurá-las usando Windows PowerShell. A Microsoft [forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis Salas do Microsoft Teams usuário. Se preferir, siga as etapas abaixo para configurar contas que seu Salas do Microsoft Teams dispositivo usará.

## <a name="requirements"></a>Requisitos

Antes de implantar Salas do Microsoft Teams com Exchange Online, certifique-se de ter atendido aos requisitos. Para obter mais informações, [consulte Salas do Microsoft Teams requisitos](requirements.md).
  
Para implantar Salas do Microsoft Teams com Exchange Online, siga as etapas abaixo. Verifique se você tem as permissões apropriadas para executar os cmdlets associados. 

   > [!NOTE]
   >  O módulo Azure Active Directory para [cmdlets](/powershell/azure/active-directory/overview) Windows PowerShell nesta seção (por exemplo, Set-MsolUser) foi testado na configuração de contas para Salas do Microsoft Teams dispositivos. É possível que outros cmdlets funcionem, no entanto, eles não foram testados neste cenário específico.

Se você implantou os Serviços de Federação do Active Directory (AD FS), talvez seja necessário converter a conta de usuário em um usuário gerenciado antes de seguir essas etapas e converter o usuário de volta em um usuário federado depois de concluir essas etapas.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Criar uma conta e definir as propriedades do Exchange

1. Inicie uma sessão Windows PowerShell remota em um computador e conecte-se Exchange Online seguinte:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Depois de estabelecer uma sessão, você criará uma nova caixa de correio e a habilitará como RoomMailboxAccount ou alterará as configurações de uma caixa de correio de sala existente. Isso permitirá que a conta se autenture em Salas do Microsoft Teams.

   Se você alterar uma caixa de correio do recurso:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se você estiver criando uma nova caixa de correio de recurso:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para melhorar a experiência de reunião, você precisará definir as propriedades Exchange na conta do usuário da seguinte forma:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Adicionar um endereço de e-mail à conta de domínio local

1. Na ferramenta AD Usuários e Computadores do **Active Directory,** clique com o botão direito do mouse no contêiner ou unidade organizacional em que suas contas Salas do Microsoft Teams serão criadas, clique em Novo e em **Usuário**. 
2. Digite o nome de exibição (- Identity ) do cmdlet anterior (Set-Mailbox ou New-Mailbox) na caixa **Nome** completo e o alias na caixa Nome de **logon do** usuário. Click **Next**.
3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionar **Senha nunca expira é** um requisito para Skype for Business Server no Salas do Microsoft Teams. As regras do domínio podem proibir senhas que não expiram. Em caso afirmado, você precisará criar uma exceção para cada Salas do Microsoft Teams de usuário.
  
4. Clique em **Concluir** para criar a conta.
5. Depois de criar a conta, execute uma sincronização de diretório. Isso pode ser feito usando [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration) no PowerShell. Quando isso for concluído, vá para a página usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Atribuir uma Microsoft 365 ou Office 365 licença

1. Primeiro, conecte-se ao Azure AD para aplicar algumas configurações de conta. Você poderá executar este cmdlet para se conectar. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview).

   > [!NOTE]
   > Azure Active Directory não há suporte para o [PowerShell 2.0.](/powershell/azure/active-directory/overview)

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. A conta de usuário precisa ter uma licença Microsoft 365 ou Office 365 para garantir que Exchange e Skype for Business Server funcionem. Se você tiver a licença, precisará atribuir um local de uso à sua conta de usuário— isso determina quais SKUs de licença estão disponíveis para sua conta. Você fará a atribuição em uma etapa a seguir.
3. Em seguida, use `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> para recuperar uma lista de SKUs disponíveis para sua Microsoft 365 ou Office 365 organização.
4. Depois de listar as SKUs, você pode adicionar uma licença usando o `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK). 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Habilitar a conta de usuário com Skype for Business Server

> [!NOTE]
> Se você estiver configurando uma Salas do Teams apenas para participar Microsoft Teams reuniões, não será necessário fazer as etapas a seguir. As etapas a seguir só serão necessárias se você quiser habilitar o suporte para Skype for Business.

1. Crie uma sessão Windows PowerShell remota de um computador da seguinte forma:

   > [!NOTE]
   > O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.
   >
   > Se você estiver usando a versão pública mais [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o conector Skype for Business Online.

   ``` Powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. Para habilitar sua Salas do Microsoft Teams para Skype for Business Server, execute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Se você não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, poderá obter o valor de um usuário Skype for Business Server existente usando este comando

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Atribuir uma Skype for Business Server de usuário à sua conta Salas do Microsoft Teams de usuário

> [!NOTE]
> Se você estiver configurando uma Salas do Teams apenas para participar Microsoft Teams reuniões, não será necessário fazer as etapas a seguir. As etapas a seguir só serão necessárias se você quiser habilitar o suporte para Skype for Business.

1. Faça logoff como administrador de locatário, abra o Centro de administração do Microsoft 365 e clique no aplicativo Administrador.
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
3. Clique na Salas do Microsoft Teams e clique no ícone de caneta para editar as informações da conta.
4. Clique em **Licenças**.
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você terá que usar uma licença de Plano 3 se quiser usar Enterprise Voice em Salas do Microsoft Teams.
6. Clique em **Salvar**.

Para validação, você deve ser capaz de usar qualquer Skype for Business cliente para fazer logoff nessa conta.

> [!NOTE]
> Se você estiver usando atualmente SKUs E1, E3, E4 ou E5 com Skype for Business Plano 2 com Audioconferência ou com Sistema de Telefonia e um Plano de Chamada, eles continuarão a funcionar. No entanto, você deve considerar a mudança para um modelo de licenciamento mais simples, conforme descrito [na atualização de](rooms-licensing.md)licenciamento Teams Sala de Reunião , após a expiração das licenças atuais.

> [!IMPORTANT]
> Se você estiver usando o Skype for Business Plano 2, só poderá usar o Salas do Microsoft Teams no modo Somente Skype for Business, o que significa que todas as reuniões serão Skype for Business reuniões. Para habilitar sua sala de reunião para Microsoft Teams reuniões, recomendamos que você compre a Sala de Reunião de reunião.
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
