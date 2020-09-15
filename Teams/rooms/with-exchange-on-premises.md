---
title: Implantar salas do Microsoft Teams com o Exchange local
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 71b1ab2ba641b25764f5c546343a3c7a597f121a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814530"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Implantar as Salas do Microsoft Teams com o Exchange no local

Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams em um ambiente híbrido com o Exchange no local e o Microsoft Teams ou o Skype for Business online.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda implantações híbridas de salas do Microsoft Teams com o Exchange hospedado no local. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não está correto para a sua configuração, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final conforme documentado aqui e para outras opções de implantação.

A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar as contas de recursos existentes que você tem para ajudar a transformá-las em contas de usuário de salas do Microsoft Teams compatíveis. Se preferir, você pode seguir as etapas abaixo para configurar contas que o dispositivo de salas do Microsoft Teams vai usar.
  
## <a name="requirements"></a>Requisitos

Antes de implantar salas do Microsoft Teams com o Exchange no local, certifique-se de que atenda aos requisitos. Para obter mais informações, consulte [requisitos de salas do Microsoft Teams](requirements.md).
  
Se você estiver implantando salas do Microsoft Teams com o Exchange no local, usará as ferramentas administrativas do Active Directory para adicionar um endereço de email para a sua conta de domínio local. Esta conta será sincronizada com o Microsoft 365 ou o Office 365. Você deverá:
  
- Criar uma conta e sincronizá-la com o Active Directory.

- Habilitar a caixa de correio remota e as propriedades definidas.

- Atribua uma licença do Microsoft 365 ou do Office 365.

- Habilite a conta do dispositivo com o Skype for Business Server. Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:

  - Você precisará ter o Skype for Business online (plano 2) ou versão mais recente no seu plano do Microsoft 365 ou do Office 365. O plano precisa dar suporte à funcionalidade de conferência.
  
  - Se você precisa do Enterprise Voice (telefonia PSTN) usando provedores de serviços de telefonia para salas do Microsoft Teams, você precisa do Skype for Business online (plano 3).
  
  - Os usuários do locatário devem ter caixas de correio do Exchange.
  
  - Sua conta de salas do Microsoft Teams exige uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3), mas não requer uma licença do Exchange Online.

- Atribua uma licença do Skype for Business Server à sua conta de salas do Microsoft Teams.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Criar uma conta e sincronizá-la com o Active Directory

1. Na ferramenta **usuários e computadores do Active Directory** , clique com o botão direito do mouse na pasta ou unidade organizacional na qual as contas de salas do Microsoft Teams serão criadas, clique em **novo**e, em seguida, clique em **usuário**.

2. Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.

3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionar a **senha nunca expira** é um requisito para as salas do Skype for Business Server em Microsoft Teams. As regras do domínio podem proibir senhas que não expiram. Em caso afirmativo, você precisará criar uma exceção para cada conta de dispositivo de salas do Microsoft Teams.
  
4. Depois de criar a conta, execute a sincronização do diretório. Quando ele estiver concluído, vá para a página usuários no centro de administração do Microsoft 365 e verifique se a conta criada nas etapas anteriores foi mesclada para online.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar a caixa de correio remota e as propriedades definidas

1. [Abra o Shell de gerenciamento do Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [Conecte-se ao seu servidor Exchange usando o PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. No PowerShell do Exchange, crie uma caixa de correio para a conta (habilite a caixa de correio da conta) executando o seguinte comando:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Para obter informações detalhadas sobre a sintaxe e o parâmetro, consulte [habilitar-caixa de correio](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. No PowerShell do Exchange, defina as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:

   - AutomateProcessing: a aceitação autoaceitar (os organizadores de reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: grátis = aceitar; Busy = recusar.)

   - AddOrganizerToSubject: $false (o organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião recebidas.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião recebidas.)

   - RemovePrivateProperty: $false (garante que o sinalizador particular enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)

   - AddAdditionalResponse: $true (o texto especificado pelo parâmetro AdditionalResponse é adicionado a solicitações de reunião.)

   - AdditionalResponse: "esta é uma sala de reunião do Skype!" (O texto adicional a ser adicionado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio da sala chamada Project-Rigel-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obter informações detalhadas de sintaxe e parâmetro, consulte [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Atribuir uma licença do Microsoft 365 ou do Office 365

1. Conecte-se ao Azure Active Directory. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > Não há suporte para o [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) . 

2. A conta do dispositivo precisa ter uma licença válida do Microsoft 365 ou do Office 365 ou o Exchange e o Microsoft Teams não funcionarão. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis.

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

   Para obter instruções detalhadas, consulte [atribuir licenças a contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Habilitar a conta do dispositivo

O PowerShell do Skype for Business Online é usado para gerenciar serviços para o Microsoft Teams e o Skype for Business online.

1. Crie uma sessão remota do Windows PowerShell a partir de um PC da seguinte maneira:
> [!NOTE]
> O conector do Skype for Business online atualmente faz parte do módulo do PowerShell mais recente do teams.
>
> Se você estiver usando a [versão pública do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)mais recente, não será necessário instalar o conector do Skype for Business online.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Obter o endereço SIP da conta:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. Para habilitar a sua conta de salas do Microsoft Teams, execute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Se não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, você pode obter o valor de um usuário existente usando este comando:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Atribuir uma licença à sua conta de salas do Microsoft Teams

1. Faça logon como administrador de locatários, abra o centro de administração do Microsoft 365 e clique no aplicativo de administração.
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
3. Clique na conta de salas do Microsoft Teams e, em seguida, clique no ícone de caneta para editar as informações da conta.
4. Clique em **Licenças**.
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você precisará usar uma licença do plano 3 se quiser usar o Enterprise Voice em suas salas do Microsoft Teams.
6. Clique em **Salvar**.

Para a validação, você deve ser capaz de usar qualquer cliente para se conectar a esta conta.
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
