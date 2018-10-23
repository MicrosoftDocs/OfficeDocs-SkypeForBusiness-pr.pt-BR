---
title: Implantar o Skype Room Systems versão 2 com o Exchange no local
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
description: Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 em um ambiente híbrido com o Exchange no local.
ms.openlocfilehash: 49e0b85cc38de91ed269ca103ef995507a6d1e37
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699357"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Implantar o Skype Room Systems versão 2 com o Exchange no local
 
Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 em um ambiente híbrido com o Exchange no local e Skype para Business Online.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda as implantações híbridas para sistemas de sala Skype v2 com o Exchange hospedado no local. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não é ideal para sua instalação, é recomendável usar o Windows PowerShell para obter o mesmo resultado final conforme documentadas aqui e para obter outras opções de implantação. 

A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de v2 Skype sala sistemas compatíveis. Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo v2 de sistemas de sala Skype usará.
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Implantar o Skype Room Systems versão 2 com o Exchange no local

Antes de implantar sistemas de sala Skype v2 com o Exchange no local, certifique-se de que você cumpre os requisitos. Para obter mais informações, veja [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Se você estiver implantando v2 Skype sistemas de sala com o Exchange no local, você usará ferramentas administrativas do Active Directory para adicionar um endereço de email para sua conta de domínio local. Essa conta será sincronizada com o Office 365. Você deverá:
  
- Criar uma conta e sincronizá-la com o Active Directory.
    
- Habilitar a caixa de correio remota e as propriedades definidas.
    
- Atribua uma licença do Office 365.
    
- Habilite a conta de dispositivo com Skype para Business Server. Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:
    
  - Você precisará ter Skype para negócios Online (plano 2) ou superior no seu plano do Office 365. O plano precisa dar suporte à funcionalidade de conferência.
    
  - Se precisar de Enterprise Voice (telefonia PSTN) usando os provedores de serviços de telefonia para sistemas de sala Skype v2 será necessário Skype para Business Online (plano 3).
    
  - Os usuários de Inquilino devem ter caixas de correio do Exchange.
    
  - Sua conta de v2 de sistemas de sala Skype exigir um Skype para negócios Online (plano 2) ou Skype licença Business Online (plano 3), mas ele não requer uma licença do Exchange Online.
    
- Atribua um Skype licença Business Server à sua conta de v2 Skype sistemas de sala.
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a>Criar uma conta e sincronizá-la com o Active Directory

1. Na ferramenta de **usuários do Active Directory e computadores AD** , clique com botão direito na pasta ou unidade organizacional que seus sistemas de sala Skype v2 contas serão criadas, clique em **novo**e, em seguida, clique em **usuário**.
    
2. Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.
    
3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.
    
    > [!NOTE]
    > Selecionando a **senha nunca expira** é um requisito para Skype para Business Server em sistemas de sala Skype v2. As regras do domínio podem proibir senhas que não expiram. Nesse caso, você precisará criar uma exceção para cada conta de dispositivo v2 Skype sistemas de sala.
  
4. Depois de criar a conta, execute a sincronização do diretório. Quando ele estiver concluído, vá para a página de usuários no seu centro de administração do Office 365 e verifique se a conta criada nas etapas anteriores mesclada para online.
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar a caixa de correio remota e as propriedades definidas

1. Habilitar a caixa de correio remota abrindo o shell de gerenciamento do Exchange no local com permissões de administrador e execute o seguinte comando:
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. Iniciar uma sessão remota do Windows PowerShell e se conectar ao Microsoft Exchange. A partir de seu locatário do Office 365, execute os seguintes comandos:
    
   ```
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess = New-PSSession -ConfigurationName Microsoft.Exchange -Credential $cred -AllowRedirection -Authentication Basic -ConnectionUri "https://<ExchangeServerFQDN>/PowerShell"
   Import-PSSession $sess
   ```

3. Para melhorar a experiência de reunião, você precisará definir as propriedades do Exchange na conta do dispositivo da seguinte maneira:
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    Para obter mais informações sobre quais propriedades, você precisa definir, consulte as propriedades do Exchange.
    
4. Você deverá conectar-se ao Azure AD para aplicar algumas configurações à conta. Você pode executar este comando para se conectar:
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a>Atribuir uma licença do Office 365

1. A conta do dispositivo precisa ter uma licença válida do Office 365 para garantir que Exchange e Skype para Business Server funcionará. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).
    
2. Em seguida, use o Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365.
    
3. Depois de listar as SKUs, você poderá adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a>Habilitar a conta de dispositivo com o Skype for Business

1. Crie uma sessão remota do Windows PowerShell de um PC, da seguinte maneira:
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar sua conta do Skype sala sistemas v2 para Skype para Business Server, execute este comando:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Se você não tiver certeza sobre qual valor usar para o parâmetro RegistrarPool no seu ambiente, você pode obter o valor de um existente Skype para usuário Business Server usando este comando
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a>Atribuir uma licença do Skype for Business a sua conta do Skype Room Systems versão 2

1. Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.
    
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
    
3. Clique na conta de sistemas de sala Skype v2 e, em seguida, clique no ícone de caneta para editar as informações de conta.
    
4. Clique em **Licenças**.
    
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você terá que usar uma licença de plano 3 se você quiser usar o Enterprise Voice em sua v2 Skype sistemas de sala.
    
6. Clique em **Salvar**.
    
Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para fazer logon conta.
  
## <a name="see-also"></a>Consulte também

[Configurar contas para sistemas de sala Skype v2](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implantar o Skype Room Systems versão 2](room-systems-v2.md)
  
[Configurar o console do Skype Room Systems versão 2](console.md)
  
[Gerenciar o Skype Room Systems versão 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

