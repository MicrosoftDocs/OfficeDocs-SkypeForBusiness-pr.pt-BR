---
title: Implantar as equipes da Microsoft para o Hub de superfície
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
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
ms.openlocfilehash: 96eb92c45af065b5f09ab9312f79198377067c4a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246154"
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

Essas instruções são para a instalação de equipes para o Hub de superfície do Microsoft Store. 
 
1. Inicie o repositório da Microsoft:<br>
   a. Toque em **Iniciar** > **todos os aplicativos** > **configurações**.<br> b. Toque em **conta de dispositivo do Hub de superfície, gerenciamento**.<br>
   c. À esquerda, toque em da guia **aplicativos e recursos** .<br> d. À direita, toque no botão **Abrir armazenamento** . 
2. Do Microsoft Store, procure *As equipes da Microsoft*. As **Equipes da Microsoft para o Hub de superfície** será exibida. Toque no botão **obter o aplicativo** para instalar.  
3. Quando a instalação estiver concluída, reinicie o Hub de superfície. 

> [!NOTE]
> Não toque no **início** do repositório de página de listagem.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Tornar as equipes a chamada padrão e a aplicação de reuniões
 
Há duas opções para configurar a política padrão de aplicativo de chamada e reuniões: 

- **Opção 1**: configurar via chave USB. 
- **Opção 2**: configurar via MDM como InTune.
 
### <a name="option-1-configure-via-usb-key"></a>Opção 1: Configurar via chave USB 
 
Os pacotes podem ser encontrados na [página de download](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Selecione a adequada para o pacote que você estiver planejando instalar e copiá-lo para uma chave USB. O arquivo .ppkg correto a ser usado depende a diretiva de aplicação de padrão que você gostaria de aplicar da seguinte maneira: 

|Número  |Descrição  |
|---------|---------|
|0     | App preferencial do Skype na tela Iniciar, equipes de reuniões disponíveis        |
|1     | As equipes de app preferencial na tela Iniciar, Skype reuniões disponíveis        |
|2     | Equipes de aplicativo exclusivo na tela Iniciar (Skype app não disponível)        |
 
1. Anexe a chave USB com o dispositivo do Hub de superfície. 
2. Abra o aplicativo de **configurações** em um dispositivo do Hub de superfície. 
3. Abra o **gerenciamento de contas de dispositivo do Hub de superfície**.
4. Abra o **gerenciamento de dispositivo**. 
5. Clique em **Adicionar ou remover um pacote de provisionamento**. 
6. Clique em **Adicionar pacote**.
7. Selecione a opção de **Mídia removível** no menu suspenso. 
8. Adicione o pacote adequado **TeamsRTMMode*.ppkg** que anteriormente foi copiado para a chave USB. 
9. Reinicie o dispositivo do Hub de superfície. 
10. Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo de equipes na tela de início e ingressar em uma reunião do calendário. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opção 2: Configurar via MDM como InTune 

Use o seguinte para configurar a chamada e reuniões aplicativo política padrão via InTune.

|Configuração   |Valor    |Descrição    |
|----------|---------|---------|
|Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo de dados | inteiro (0-2)   |0 - app preferencial do Skype na tela Iniciar, equipes de reuniões disponíveis<br>1 - equipes preferencial app na tela Iniciar, Skype reuniões disponíveis<br>2 - equipes de aplicativo exclusivo na tela Iniciar (Skype app não disponível) |
|Operações| Obter, definir        |

|Configuração   |Valor    |
|----------|---------|
|Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo de dados | cadeia de caracteres - conjunto de cadeia de caracteres para a ID do pacote de aplicativo de equipes como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! As equipes** |
|Operações| Obter, definir        |

Reinicie o dispositivo do Hub de superfície. Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo de equipes na tela de início e ingressar em uma reunião do calendário.

