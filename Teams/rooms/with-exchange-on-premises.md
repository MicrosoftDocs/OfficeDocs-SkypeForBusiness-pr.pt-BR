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
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams em um ambiente híbrido com o Exchange no local.
ms.openlocfilehash: fcf7216a4fcadee1e81ef11b5310b9d0a88e378a
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460511"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Implantar as Salas do Microsoft Teams com o Exchange no local

Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams em um ambiente híbrido com o Exchange local e o Microsoft Teams ou o Skype for Business Online.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda implantações híbridas para Salas do Microsoft Teams com o Exchange hospedado no local. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não estiver correto para sua instalação, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final documentado aqui e para outras opções de implantação.

A Microsoft [ forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis do Microsoft Teams Rooms. Se preferir, siga as etapas abaixo para configurar contas que o dispositivo salas do Microsoft Teams usará.
  
## <a name="requirements"></a>Requisitos

Antes de implantar salas do Microsoft Teams com o Exchange no local, certifique-se de ter atendido aos requisitos. Para obter mais informações, consulte [Requisitos de Salas do Microsoft Teams.](requirements.md)
  
Se você estiver implantando salas do Microsoft Teams com o Exchange no local, você estará usando ferramentas administrativas do Active Directory para adicionar um endereço de email para sua conta de domínio local. Essa conta será sincronizada com o Microsoft 365 ou o Office 365. Você deverá:
  
- Criar uma conta e sincronizá-la com o Active Directory.

- Habilitar a caixa de correio remota e as propriedades definidas.

- Atribua uma licença do Microsoft 365 ou office 365.

- Habilita a conta de dispositivo com o Skype for Business Server. Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:

  - Você precisará ter o Skype for Business Online (Plano 2) ou superior em seu plano do Microsoft 365 ou Office 365. O plano precisa dar suporte à funcionalidade de conferência.
  
  - Se você precisar Enterprise Voice (telefonia PSTN) usando provedores de serviços de telefonia para Salas do Microsoft Teams, você precisa do Skype for Business Online (Plano 3).
  
  - Os usuários de locatários devem ter caixas de correio do Exchange.
  
  - Sua conta de Salas do Microsoft Teams exige uma licença do Skype for Business Online (Plano 2) ou do Skype for Business Online (Plano 3), mas não exige uma licença do Exchange Online.

- Atribua uma licença do Skype for Business Server à sua conta do Microsoft Teams Rooms.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Criar uma conta e sincronizá-la com o Active Directory

1. Na ferramenta Usuários e Computadores do **Active Directory,** clique com o botão direito do mouse na pasta ou Unidade Organizacional na qual suas contas de Salas do Microsoft Teams serão criadas, clique em Novo **e** em **Usuário**.

2. Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.

3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionar **Senha nunca expira é** um requisito para o Skype for Business Server em Salas do Microsoft Teams. As regras do domínio podem proibir senhas que não expiram. Em caso afirmado, você precisará criar uma exceção para cada conta de dispositivo do Microsoft Teams Rooms.
  
4. Depois de criar a conta, execute a sincronização do diretório. Quando estiver concluída, vá até a página usuários no centro de administração do Microsoft 365 e verifique se a conta criada nas etapas anteriores foi mesclada para online.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar a caixa de correio remota e as propriedades definidas

1. [Abra o Shell de Gerenciamento do Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [conecte-se ao seu servidor Exchange usando o PowerShell remoto.](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. No Exchange PowerShell, crie uma caixa de correio para a conta (habilitada para caixa de correio da conta) executando o seguinte comando:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. No Exchange PowerShell, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência de reunião:

   - AutomateProcessing: AutoAccept (Os organizadores da reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião de entrada.)

   - RemovePrivateProperty: $false (Garante que o sinalizador privado enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)

   - AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)

   - AdditionalResponse: "Esta é uma sala de reunião do Skype!" (O texto adicional a ser acrescentado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio de sala chamada Project-Rigel-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Atribuir uma licença do Microsoft 365 ou Office 365

1. Conecte-se ao Azure Active Directory. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Não há suporte para o PowerShell 2.0 do Azure Active Directory.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 

2. A conta de dispositivo precisa ter uma licença válida do Microsoft 365 ou Office 365, ou o Exchange e o Microsoft Teams não funcionarão. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Em seguida, você pode adicionar uma licença usando o `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).

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

   Para obter instruções [detalhadas, consulte Atribuir licenças a contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Habilitar a conta do dispositivo

O PowerShell do Skype for Business Online é usado para gerenciar serviços para o Microsoft Teams e o Skype for Business Online.

1. Crie uma sessão Windows PowerShell remota de um computador da seguinte forma:
> [!NOTE]
> O Skype for Business Online Connector atualmente faz parte do módulo mais recente do Teams PowerShell.
>
> Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Conector do Skype for Business Online.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Obtenha o endereço SIP da conta:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. Para habilitar sua conta de Salas do Microsoft Teams, execute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Se você não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, poderá obter o valor de um usuário existente usando este comando:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Atribuir uma licença à sua conta do Microsoft Teams Rooms

1. Faça logoff como administrador de locatário, abra o Centro de administração do Microsoft 365 e clique no aplicativo Administrador.
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
3. Clique na conta salas do Microsoft Teams e clique no ícone de caneta para editar as informações da conta.
4. Clique em **Licenças**.
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você terá que usar uma licença do Plano 3 se quiser usar Enterprise Voice salas do Microsoft Teams.
6. Clique em **Salvar**.

Para validação, você deve ser capaz de usar qualquer cliente para fazer logoff nessa conta.
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
