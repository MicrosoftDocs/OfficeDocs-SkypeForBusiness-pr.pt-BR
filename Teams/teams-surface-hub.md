---
title: Implantar as equipes da Microsoft para o Hub de superfície
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Defina configurações de administração for Microsoft Teams para o Hub de superfície.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192176"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Implantar as equipes da Microsoft para o Hub de superfície
======================================

Antes de implantar Teams da Microsoft para Microsoft Surface Hub, certifique-se de que você cumpre o hardware, sistema operacional e outros requisitos. Para obter mais informações, consulte o [guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).

## <a name="set-up-user-accounts"></a>Configurar contas de usuário
 
Para configurar contas de usuário que podem ser usadas com equipes para o Hub de superfície, crie a conta de dispositivo como faria para suporte com Skype para negócios. A conta do dispositivo precisa ter a autenticação multifator desabilitada (para permitir o logon automático) para os seguintes serviços dependentes de equipes no Office 365:  
- Exchange 
- SharePoint 
- Aplicativos do Office 

## <a name="add-a-device-account"></a>Adicionar uma conta de dispositivo 

1 \. Inicie uma sessão remota do Windows PowerShell em um PC e se conectar ao Exchange. Certifique-se de que você tem as permissões corretas definidas para executar os cmdlets associados. Veja a seguir alguns exemplos de cmdlets que podem ser usados e modificados em seu ambiente.

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2 \. Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente. Isso permitirá a conta autenticar a equipes.

Se você estiver alterando uma caixa de correio do recurso existente:

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

Se você criar uma nova caixa de correio para o recurso:

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3\. Várias propriedades do Exchange deverão ser definidas na conta de dispositivo para aprimorar a experiência de reunião. Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

4\. Você deverá conectar-se ao Azure Active Directory para aplicar algumas configurações à conta. Para se conectar ao Azure AD, execute o seguinte cmdlet:

```
Connect-MsolService -Credential $cred
```

5\. 	Para a senha não expirar, execute o cmdlet Set-MsolUser com a opção PasswordNeverExpires, como a seguir:   

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

Você também pode definir um número de telefone para a sala da seguinte maneira:

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

6\. A conta do dispositivo precisa ter uma licença válida do Office 365 ou Exchange e Skype para negócios não funcionará. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar o Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365, da seguinte maneira:
 
```
Get-MsolAccountSku
```

Em seguida, você pode adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

7\. Em seguida, você precisará habilitar a conta de dispositivo com equipes para o Hub de superfície. Certifique-se de que seu ambiente atende aos requisitos definidos no [guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).

Iniciar uma sessão do Windows PowerShell remota da seguinte maneira (certifique-se de instalar o Skype para componentes de negócios Online PowerShell):

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

Em seguida, habilite suas equipes de conta do Hub de superfície executando o seguinte cmdlet:

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

Obtenha as informações de RegistrarPool da nova conta de usuário sendo instalação, como mostrado neste exemplo:

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> Novas contas de usuário não podem ser criadas no mesmo pool do registrador contas de usuário existentes no inquilino. O comando acima evitará erros na configuração de conta devido a essa situação. 

Depois de concluir as etapas anteriores para permitir que as equipes de conta do Hub de superfície, você precisa atribuir uma licença para o dispositivo do Hub de superfície v2. Usando o portal administrativo do Office 365, atribua a equipes de licença do Hub de superfície para o dispositivo.

### <a name="assign-a-license-to-the-account"></a>Atribuir uma licença para a conta

1. Faça logon como um administrador de locatários, abra o Centro de administração do Office 365 e clique no aplicativo Administração.
2. Clique em **usuários e grupos**e clique em **Adicionar usuários, redefinir senhas e muito mais**.
3. Selecione as equipes de conta do Hub de superfície e, em seguida, clique ou toque no ícone de caneta, o que significa editar.
4. Clique na opção de **licenças** .
5. Na seção **Atribuir licenças** , você precisa selecionar o plano, dependendo do seu licenciamento.
6. Clique em **Salvar** para concluir a tarefa.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Instalar equipes para o Hub de superfície do repositório de Microsoft 

Essas instruções incluem as soluções alternativas de atuais para a instalação de equipes para o Hub de superfície do Microsoft Store. 
 
1. Inicie o repositório do Windows:<br>
   a. Toque em **Iniciar** > **todos os aplicativos** > **configurações**.<br> b. Toque em **conta de dispositivo do Hub de superfície, gerenciamento**.<br>
   c. À esquerda, toque em da guia **aplicativos e recursos** .<br> d. À direita, toque no botão **Abrir armazenamento** . 
2. Do Microsoft Store, procure *As equipes da Microsoft*. As **Equipes da Microsoft para o Hub de superfície (Preview)** será exibida. Toque no botão **obter o aplicativo** para instalar.  
3. Quando a instalação estiver concluída, reinicie o Hub de superfície. 
4. Depois que o Hub de superfície for reiniciado, você poderá iniciar o aplicativo de equipes do menu **Iniciar** e ingressar em uma reunião do calendário. 

## <a name="make-teams-the-default-vtc-application"></a>Tornar as equipes aplicativo VTC padrão

As equipes podem ser definidas até ser o aplicativo de VTC padrão, em vez de Skype para negócios. Uma política de gerenciamento de dispositivo móvel (MDM) deve ser aplicada ao dispositivo Hub de superfície. 
 
Há duas opções para configurar políticas MDM: 

- Se você tiver uma diretiva configurada, você deve adicioná-lo por meio do aplicativo de gerenciamento do dispositivo. 
- Se você não tiver uma diretiva remoto configurada, temos um arquivo de pacote provisionados que pode ser carregado em uma chave USB.

### <a name="device-management-configuration"></a>Configuração de gerenciamento de dispositivo

O exemplo a seguir é um exemplo da adição de uma política MDM configurada em uma autoridade de MDM central. Se você estiver na rede corporativa, você pode usar as seguintes instruções textual, incluindo a conta de usuário. 
 
1. Na seção **Gerenciamento de dispositivo** , toque em **+**.<br>
   A caixa de diálogo **conectar ao trabalhar ou escola** será aberto. 
2. Insira o endereço de email de diretiva e a senha, quando solicitado.<br>
   **Observação:**  Não há um bug do sistema operacional que não atualizar automaticamente a interface do usuário depois que você inseriu sua conta de gerenciamento de dispositivo. Você precisará feche e abra novamente as configurações para ver a conta listada. 
3. Ele vai levar alguns minutos para as configurações de diretiva MDM sincronizar. Se desejar forçar uma sincronização, toque no botão de **conta MDM** e, em seguida, toque no botão **Info** . Isso exibirá a janela de informações onde você pode toque em **sincronização**. 
4. Para verificar se você tem o que você precisa, é possível verificar o registro. Você deverá ver duas chaves em **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**. <br><br>
   O valor DWORD **VtcAppMeetingHandlingMode** indica que as equipes é o aplicativo padrão. Os valores a seguir são reconhecidos. <br><br>
    |Número | Valor   |
    |-------|---------|
    |0      | SkypePreferred            |
    |1      | VtcPreferred (equipes)      |
    |2      | VtcExclusive (somente para equipes) |

    O **VtcCallAppPackageId** é o nome do pacote equipes instalado. Se isso não for exibido, certifique-se de que ter instalado o pacote de equipes e resincronização. 
 
### <a name="configure-mdm-via-usb-key"></a>Configurar MDM via chave USB 
 
Os pacotes podem ser encontrados na [página de download](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Selecione a adequada para o pacote que você estiver planejando instalar e copiá-lo para uma chave USB. O arquivo .ppkg correto a ser usado depende do pacote de equipes que tenha sido instalado do repositório e a política que você gostaria de aplicar (Skype exclusivo, Skype preferencial, equipes preferenciais, exclusive equipes). 
 
1. Anexe a chave USB com o dispositivo do Hub de superfície. 
2. Abra o aplicativo de **configurações** em um dispositivo do Hub de superfície. 
3. Abra o **gerenciamento de contas de dispositivo do Hub de superfície**.
4. Abra o **gerenciamento de dispositivo**. 
5. Clique em **Adicionar ou remover um pacote de provisionamento**. 
6. Clique em **Adicionar pacote**.
7. Selecione a opção de **Mídia removível** no menu suspenso. 
8. Adicione o **Allowbuildspreview.ppkg**e, em seguida, selecione o pacote de superfície Hub que você deseja adicionar. 
9. Reinicie o dispositivo do Hub de superfície. 

> [!NOTE]
> Se seu dispositivo ou dispositivos de sua organização não atualmente fazem parte do programa Insider Windows e você estiver nos países cobertos pela regulamentação de proteção de dados gerais (GDPR) (ou você tiver alterado manualmente suas configurações de telemetria para básico), em seguida, você deve verificar novamente que você tenha permitido telemetria completa antes de participar do programa Insider. GDPR alterado o comportamento padrão de dispositivos de superfície Hub na UE para definir telemetria como básica.