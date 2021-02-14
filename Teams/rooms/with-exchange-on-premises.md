---
title: Implantar salas do Microsoft Teams com o Exchange local
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams em um ambiente híbrido com o Exchange local.
ms.openlocfilehash: f9f80f5b993b9be95e35c8178d996973558e2512
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662316"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Implantar as Salas do Microsoft Teams com o Exchange no local

Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams em um ambiente híbrido com o Exchange local e o Microsoft Teams ou o Skype for Business Online.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda as implantações híbridas das Salas do Microsoft Teams com o Exchange hospedado no local. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não for o certo para sua configuração, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final que documentado aqui e para outras opções de implantação.

A Microsoft [ forneceSkypeRoomProvisioningScript.ps1, ](https://go.microsoft.com/fwlink/?linkid=870105)um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis com Salas do Microsoft Teams. Se preferir, siga as etapas abaixo para configurar contas que seu dispositivo Salas do Microsoft Teams usará.
  
## <a name="requirements"></a>Requisitos

Antes de implantar as Salas do Microsoft Teams com o Exchange no local, certifique-se de que você atendeu aos requisitos. Para obter mais informações, consulte [os requisitos de Salas do Microsoft Teams.](requirements.md)
  
Se estiver implantando salas do Microsoft Teams com o Exchange no local, você estará usando ferramentas administrativas do Active Directory para adicionar um endereço de email para sua conta de domínio local. Essa conta será sincronizada com o Microsoft 365 ou o Office 365. Você deverá:
  
- Criar uma conta e sincronizá-la com o Active Directory.

- Habilitar a caixa de correio remota e as propriedades definidas.

- Atribua uma licença do Microsoft 365 ou do Office 365.

- Habilitar a conta do dispositivo com o Skype for Business Server. Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:

  - Você precisará ter o Skype for Business Online (Plano 2) ou superior em seu plano Microsoft 365 ou Office 365. O plano precisa dar suporte à funcionalidade de conferência.
  
  - Se precisar do Enterprise Voice (telefonia PSTN) usando provedores de serviços de telefonia para salas do Microsoft Teams, você precisará do Skype for Business Online (Plano 3).
  
  - Os usuários do locatário devem ter caixas de correio do Exchange.
  
  - Sua conta do Microsoft Teams Rooms requer uma licença do Skype for Business Online (Plano 2) ou do Skype for Business Online (Plano 3), mas não requer uma licença do Exchange Online.

- Atribua uma licença do Skype for Business Server à sua conta do Microsoft Teams Rooms.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Criar uma conta e sincronizá-la com o Active Directory

1. Na ferramenta Usuários e Computadores do **Active Directory,** clique com o botão direito do mouse na pasta ou Unidade Organizacional na qual suas contas de Salas do Microsoft Teams serão criadas, clique em Novo e, em seguida, clique em **Usuário.**

2. Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.

3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionar **Senha nunca expira é** um requisito para o Skype for Business Server em Salas do Microsoft Teams. As regras do domínio podem proibir senhas que não expiram. Se sim, você precisará criar uma exceção para cada conta de dispositivo do Microsoft Teams Rooms.
  
4. Depois de criar a conta, execute a sincronização do diretório. Quando estiver concluído, vá para a página de usuários no centro de administração do Microsoft 365 e verifique se a conta criada nas etapas anteriores foi mesclada à online.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar a caixa de correio remota e as propriedades definidas

1. [Abra o Shell de Gerenciamento do Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [conecte-se ao seu servidor Exchange usando o PowerShell remoto.](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. No Exchange PowerShell, crie uma caixa de correio para a conta (caixa de correio habilitar a conta) executando o seguinte comando:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Habilitar-Caixa de Correio.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)

3. No Exchange PowerShell, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:

   - AutomateProcessing: AutoAccept (organizadores da reunião recebem a decisão de reserva da sala diretamente sem intervenção humana: gratuito = aceitar; ocupado = recusar.)

   - AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem das solicitações de reunião recebidas.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião recebidas.)

   - RemovePrivateProperty: $false (Garante o sinalizador particular que foi enviado pelo organizador da reunião na solicitação de reunião original permanece como especificado.)

   - AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)

   - AdicionalResponse: "Esta é uma sala de reunião do Skype!" (O texto adicional a ser acrescentado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio da sala chamada Project-Rigel-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Atribuir uma licença do Microsoft 365 ou do Office 365

1. Conecte-se ao Azure Active Directory. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [O PowerShell 2.0 do Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) não tem suporte. 

2. A conta do dispositivo precisa ter uma licença válida do Microsoft 365 ou do Office 365, ou o Exchange e o Microsoft Teams não funcionarão. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Em seguida, você pode adicionar uma licença usando o `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> Cmdlet. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Para obter instruções [detalhadas, consulte Atribuir licenças a contas de usuário com o PowerShell do Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="enable-the-device-account"></a>Habilitar a conta do dispositivo

O PowerShell do Skype for Business Online é usado para gerenciar serviços do Microsoft Teams e do Skype for Business Online.

1. Crie uma sessão remota do Windows PowerShell a partir de um computador da seguinte forma:
> [!NOTE]
> No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.
>
> Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Obtenha o endereço SIP da conta:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. Para habilitar sua conta do Microsoft Teams Rooms, execute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Se você não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, poderá obter o valor de um usuário existente usando este comando:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Atribuir uma licença à sua conta do Microsoft Teams Rooms

1. Entre como administrador de locatários, abra o Centro de administração do Microsoft 365 e clique no aplicativo Administrador.
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
3. Clique na conta salas do Microsoft Teams e, em seguida, clique no ícone de caneta para editar as informações da conta.
4. Clique em **Licenças**.
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você terá que usar uma licença do Plano 3 se quiser usar o Enterprise Voice em suas Salas do Microsoft Teams.
6. Clique em **Salvar**.

Para validação, você deve ser capaz de usar qualquer cliente para entrar nessa conta.
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
