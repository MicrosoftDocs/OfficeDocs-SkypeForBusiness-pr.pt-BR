---
title: Implantar salas de equipes da Microsoft com o Exchange no local
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: Leia este tópico para obter informações sobre como implantar as salas de equipes da Microsoft em um ambiente híbrido com o Exchange no local.
ms.openlocfilehash: b6c10635180d5707982efbc259eca577c45b1638
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012514"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Implantar salas de equipes da Microsoft com o Exchange no local

Leia este tópico para obter informações sobre como implantar o Microsoft equipes salas em um ambiente híbrido com o Exchange no local e Skype para Business Online.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda as implantações híbridas para salas de equipes da Microsoft com o Exchange hospedado no local. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não é ideal para sua instalação, é recomendável usar o Windows PowerShell para obter o mesmo resultado final conforme documentadas aqui e para obter outras opções de implantação.

A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de salas de equipes da Microsoft compatíveis. Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo de salas de equipes da Microsoft usará.
  
## <a name="requirements"></a>Requisitos

Antes de implantar salas de equipes da Microsoft com o Exchange no local, certifique-se de que você cumpre os requisitos. Para obter mais informações, consulte [requisitos de salas de equipes da Microsoft](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Se você estiver implantando salas de equipes da Microsoft com o Exchange no local, você usará ferramentas administrativas do Active Directory para adicionar um endereço de email para sua conta de domínio local. Essa conta será sincronizada com o Office 365. Você deverá:
  
- Criar uma conta e sincronizá-la com o Active Directory.

- Habilitar a caixa de correio remota e as propriedades definidas.

- Atribua uma licença do Office 365.

- Habilite a conta de dispositivo com Skype para Business Server. Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:

  - Você precisará ter Skype para negócios Online (plano 2) ou superior no seu plano do Office 365. O plano precisa dar suporte à funcionalidade de conferência.
  
  - - Se precisar de Enterprise Voice (telefonia PSTN) usando os provedores de serviços de telefonia para salas de equipes da Microsoft você precisa Skype para Business Online (plano 3).
  
  - - Os usuários de Inquilino devem ter caixas de correio do Exchange.
  
  - - Sua conta da Microsoft equipes salas requerem um Skype para negócios Online (plano 2) ou Skype licença Business Online (plano 3), mas ele não requer uma licença do Exchange Online.

- Atribua um Skype licença Business Server à sua conta de salas de equipes da Microsoft.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Criar uma conta e sincronizá-la com o Active Directory

1. Na ferramenta de **usuários do Active Directory e computadores AD** , clique com botão direito na pasta ou unidade organizacional que suas salas de equipes da Microsoft contas serão criadas, clique em **novo**e, em seguida, clique em **usuário**.

2. Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.

3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionando a **senha nunca expira** é um requisito para Skype para Business Server em salas de equipes da Microsoft. As regras do domínio podem proibir senhas que não expiram. Nesse caso, você precisará criar uma exceção para cada conta de dispositivo de salas de equipes da Microsoft.
  
4. Depois de criar a conta, execute a sincronização do diretório. Quando ele estiver concluído, vá para a página de usuários no seu centro de administração do Office 365 e verifique se a conta criada nas etapas anteriores mesclada para online.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar a caixa de correio remota e as propriedades definidas

1. [Abra o Shell de gerenciamento do Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [Conecte-se ao servidor do Exchange usando o PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. No PowerShell do Exchange, criar uma caixa de correio para a conta (caixa de correio-habilitar a conta) executando o seguinte comando:

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Para detalhadas sobre sintaxe e informações de parâmetro, consulte [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. No PowerShell do Exchange, defina as seguintes configurações na caixa de correio de sala para melhorar a experiência de reunião:

   - AutomateProcessing: AutoAccept (organizadores de reunião recebem a decisão de reserva de sala diretamente, sem intervenção humana: livre = aceitar; ocupado = recusar.)

   - AddOrganizerToSubject: $false (o organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (mantenha qualquer texto no corpo da mensagem de entrada solicitações de reunião).

   - DeleteSubject: $false (manter o assunto de solicitações de reunião recebidas).

   - RemovePrivateProperty: $false (assegura o sinalizador particular que foi enviado pelo organizador da reunião na reunião original permanece conforme especificado de solicitação).

   - AddAdditionalResponse: $true (o texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião).

   - AdditionalResponse: "Esta é uma sala de reunião Skype!" (O texto adicional para adicionar à solicitação de reunião).

   Este exemplo configura essas configurações na caixa de correio de sala chamada Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para detalhadas sobre sintaxe e informações de parâmetro, consulte [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-an-office-365-license"></a>Atribuir uma licença do Office 365

1. Conecte-se ao PowerShell do Azure Active Directory. Para obter instruções, consulte [conectar-se com o Azure Active Directory PowerShell para o módulo de gráfico](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

2. A conta do dispositivo precisa ter uma licença válida do Office 365 ou Exchange e Skype para negócios não funcionará. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Em seguida, você pode adicionar uma licença usando o`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).

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

   Para obter instruções detalhadas, consulte [Atribuir licenças às contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account-with-skype-for-business"></a>Habilitar a conta de dispositivo com o Skype for Business

1. Crie uma sessão remota do Windows PowerShell de um PC, da seguinte maneira:

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar sua conta de salas de equipes da Microsoft para Skype para Business Server, execute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Se você não tiver certeza sobre qual valor usar para o parâmetro RegistrarPool no seu ambiente, você pode obter o valor de um existente Skype para usuário Business Server usando este comando

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-microsoft-teams-rooms-account"></a>Atribuir um Skype licença de negócios à sua conta de salas de equipes da Microsoft

1. Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
3. Clique na conta de salas de equipes da Microsoft e clique no ícone de caneta para editar as informações de conta.
4. Clique em **Licenças**.
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você terá que usar uma licença de plano 3 se você quiser usar o Enterprise Voice em suas salas de equipes da Microsoft.
6. Clique em **Salvar**.

Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para fazer logon conta.
  
## <a name="see-also"></a>Consulte Também

[Configurar contas para salas de equipes da Microsoft](room-systems-v2-configure-accounts.md)

[Planejar para salas de equipes da Microsoft](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implantar salas de equipes da Microsoft](room-systems-v2.md)
  
[Configurar um console de salas de equipes da Microsoft](console.md)
  
[Gerenciar salas de equipes da Microsoft](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
