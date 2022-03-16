---
title: Criar contas de recursos para salas e dispositivos Teams compartilhados
ms.author: czawideh
author: cazawideh
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este artigo para obter informações sobre como criar contas de recursos para salas e dispositivos compartilhados, incluindo Salas do Microsoft Teams, Salas do Teams no Surface Hub e hot-desking em Teams exibições.
ms.openlocfilehash: e7525a9e9ec6737bab18de4351675d567b61611b
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514542"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Criar e configurar contas de recursos para salas e dispositivos Teams compartilhados

Este artigo fornece etapas para criar contas de recursos para espaços compartilhados e dispositivos, e inclui etapas para configurar contas de recursos para Salas do Microsoft Teams no Windows, Salas do Teams no Android, Salas do Teams no Surface Hub e hot-desking on Teams é exibido.

Microsoft 365 contas de recursos são caixas de correio e Teams que são dedicadas a recursos específicos, como uma sala ou projetor. Essas contas de recursos podem responder automaticamente a convites de reunião usando regras definidas quando elas são criadas. Por exemplo, se você tiver um recurso comum, como uma sala de conferência, poderá configurar uma conta de recurso para essa sala de conferência que aceitará ou recusará automaticamente convites de reunião, dependendo da disponibilidade do calendário.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype for Business** <br><br>
> Se você precisar habilitar sua conta de recurso para trabalhar com Skype for Business, consulte [Deploy Salas do Microsoft Teams with Skype for Business Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Antes de você começar

### <a name="requirements"></a>Requisitos

Dependendo do ambiente, você precisa de uma ou mais funções para criar contas de recursos.

|**Ambiente**|**Funções necessárias**|
|-----|-----|
|Azure Active Directory  <br/> |Administrador Global ou Administrador de Usuário  <br/> |
|Active Directory  <br/> |O Active Directory Enterprise administradores, administradores de domínio ou têm direitos delegados para criar usuários. Azure Active Directory Conexão direitos de sincronização.  <br/> |
|Exchange Online  <br/> |Administrador Global ou Exchange Administrador   <br/> |
|Exchange Server  <br/> |Exchange gerenciamento de organização ou gerenciamento de destinatários   <br/> |

Se você estiver criando contas de recurso para Salas do Teams, o UPN deverá corresponder ao endereço SMTP da conta de recurso. Consulte [Salas do Microsoft Teams requisitos antes](requirements.md) de implantar Salas do Teams.

### <a name="what-license-do-you-need"></a>De que licença você precisa?

Antes de criar uma Microsoft 365 de recursos, verifique para ver de que tipo de licença ela precisa:

- **reuniões** Teams Se você deseja associar a conta de recurso a um dispositivo compartilhado, como uma sala do Microsoft Teams ou uma exibição do Teams com hot-desking, e usá-la para ingressar em uma reunião do Teams para que os participantes possam usá-la para apresentar vídeo e áudio por meio dele, você precisa de uma licença de Sala de Reunião. Para obter mais informações sobre licenciamento para salas de reunião, [consulte Teams Sala de Reunião Licensing](rooms-licensing.md).

- **Chamadas PSTN** Se você quiser que o recurso faça ou receba chamadas para ou de um número de telefone externo (chamado de rede telefônica pública comutado ou chamada PSTN), você precisa de uma licença Microsoft 365 Sistema de Telefonia ou Microsoft 365 Business Voice. Você só precisa concluir a Etapa 1 na visão geral a seguir. Em seguida, [consulte Microsoft Teams licenças de complemento para](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) obter mais informações.

- Se você estiver usando apenas uma conta de recurso para reservar um recurso que seja,&mdash; convide o recurso para sua reunião e aceite ou decline automaticamente o convite que você não precisa atribuir uma licença à conta de recurso e você só precisa concluir a&mdash; Etapa 1 na visão geral a seguir.  

## <a name="overview"></a>Visão Geral

**Etapa 1 -** [Criar uma nova conta de recurso](#create-a-resource-account). Ou, se uma caixa de correio de sala já existir e você quiser convertê-la em uma conta de recurso, você poderá modificar uma caixa de correio Exchange [sala existente](?tabs=existing-account#create-a-resource-account).

**Etapa 2 -**  Em seguida, [configure sua conta para](#configure-mailbox-properties) Teams Reuniões.

**Etapa 3 -**  Se a conta de recurso for associada a um dispositivo compartilhado, como Teams exibe com hot-desking, desativará a expiração [de senha](#turn-off-password-expiration).

**Etapa 4 -**  Por fim, [atribua uma licença de sala de](#assign-a-meeting-room-license) reunião para que a conta possa acessar Microsoft Teams.

Depois de criar e configurar suas contas de recursos, [](#next-steps) consulte Próximas etapas para revisar tarefas de instalação adicionais, incluindo grupos de distribuição, funcionalidade de rede e chamada.

## <a name="create-a-resource-account"></a>Criar uma conta de recurso

> [!TIP]
> Ao nomear suas contas de recursos, recomendamos usar uma convenção de nomenisco padrão para o início do endereço de email. Isso ajudará na criação de grupos dinâmicos para facilitar o gerenciamento Azure Active Directory. Por exemplo, você pode usar "mtr-" para todas as contas de recursos que serão associadas a Salas do Microsoft Teams.

> [!TIP]
> Recomendamos que você crie todas as contas de recursos usando Exchange Online e Azure Active Directory.

Crie uma conta de recurso usando um método a partir de uma das seguintes guias:

#### <a name="in-microsoft-365-admin-center"></a>[**Em Centro de administração do Microsoft 365**](#tab/m365-admin-center)

1. Acesse o Centro de administração do Microsoft 365.

2. Forneça as credenciais de administrador para seu Microsoft 365 locatário.

3. Vá para **Recursos** no painel esquerdo e selecione **Salas & equipamento**. Se essas opções não estão disponíveis no painel esquerdo, talvez seja necessário selecionar **Mostrar tudo** primeiro.

4. Selecione **Adicionar uma caixa de correio de recurso** para criar uma nova conta de sala. Insira um nome de exibição e um endereço de email para a conta, selecione **Adicionar** e selecione **Fechar**.

5. Por padrão, as contas de recurso são configuradas com as seguintes configurações:

    - Permitir reuniões repetidas
    - Recusar reuniões automaticamente fora dos limites a seguir
      - Janela de reserva (dias): 180
      - Duração máxima (horas): 24
    - Solicitações de reunião de aceitação automática

    Se quiser alterá-las, selecione **Definir opções de agendamento** antes de selecionar **Fechar**. Se você quiser alterá-los mais tarde, vá para **ResourcesRooms** >  **& equipamento**, selecione a conta de recurso. Em Opções **de Reserva**, selecione **Editar**.

6. Vá para **UsuáriosAtivos** >  usuários e selecione a sala que você criou para abrir o painel de propriedades.

7. Em seguida, atribua uma senha à conta de recurso. No painel, selecione **Redefinir senha**.
 
8. Exigir que os usuários alterem a senha em um dispositivo compartilhado causará problemas de entrada. **Desmarcar Exigir que esse usuário altere a senha quando entrar** pela primeira vez e selecione **Redefinir**.

9. Na seção **Licenças e Aplicativos** , de definir **Selecionar local** para o país ou região onde o dispositivo será instalado. Em seguida, selecione a licença que você deseja atribuir, como Sala de Reunião, e selecione **Salvar alterações**. A licença pode variar dependendo da sua organização.

Para alterar as configurações da caixa de correio de recurso, consulte [Configure mailbox properties](#configure-mailbox-properties) or use the Exchange admin center.

Você também pode precisar aplicar políticas de largura de banda ou políticas de reunião a essa conta. Consulte [Próximas etapas](#next-steps) para obter mais informações.

#### <a name="with-exchange-online"></a>[**Com Exchange Online**](#tab/exchange-online)

1. Conexão para [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. Por padrão, as caixas de correio de sala não têm contas associadas. Adicione uma conta ao criar uma caixa de correio de sala para que ela possa ser autenticada com Microsoft Teams.

    Se você estiver criando uma nova caixa de correio de recurso:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

        - Account: ConferenceRoom01@contoso.com
          
        - Name: ConferenceRoom01
        
        - Alias: ConferenceRoom01
        
        - Account password: P@$$W0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Se você não estiver em uma configuração Exchange híbrida, poderá continuar até a próxima etapa, [Configurar propriedades de caixa de correio](#configure-mailbox-properties).

Se você estiver em uma configuração Exchange híbrida, você precisará adicionar um endereço de email para sua conta de domínio local. Consulte [Sync on-premises and Office 365 user accounts directories](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) para obter mais informações.

#### <a name="with-exchange-server"></a>[**Com Exchange Server**](#tab/exchange-server)

  1. Conexão para Exchange Shell de Gerenciamento. [Abra o Shell de Gerenciamento Exchange ou](/powershell/exchange/exchange-server/open-the-exchange-management-shell) [conecte-se ao seu servidor Exchange usando o PowerShell remoto](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

   2. Para criar uma nova caixa de correio de sala:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

   - Conta: ConferenceRoom01@contoso.com
  
   - Nome: ConferenceRoom01

   - Alias: ConferenceRoom01

   - Senha da conta: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Modificar uma caixa de correio Exchange sala existente**](#tab/existing-account)

Para modificar uma caixa de correio de sala existente para se tornar uma conta de recurso, use a seguinte sintaxe:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor alias ConferenceRoom02 e define a senha como 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Se você estiver em uma configuração Exchange híbrida, também precisará adicionar um endereço de email para sua conta de domínio local. Consulte [Sync on-premises and Office 365 user accounts directories](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) para obter mais informações.

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Se você estiver criando essa conta para Teams Room no Surface Hub, você também deve habilitar o ActiveSync nessa conta. Isso permitirá que você envie emails diretamente do Surface Hub, que você pode usar para recursos como o Quadro de Trabalho. Consulte [Applying ActiveSync policies to device accounts (Surface Hub)](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) to learn more.

---

> [!IMPORTANT]
> Se você estiver apenas usando essa conta de recurso para reservar espaço e aceitar automaticamente ou recusar convites, você concluiu a configuração. Se você estiver usando essa conta de recurso para chamada PSTN, consulte [Microsoft Teams licenças](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) de complemento para determinar de que licença ela precisa.
>
> Continue até a próxima seção somente se a conta de recurso for para um Salas do Teams no Windows, Salas do Teams no Android, Salas do Teams no Surface Hub ou uma exibição Teams com hot-desking.

## <a name="configure-mailbox-properties"></a>Configurar propriedades de caixa de correio

No Exchange PowerShell, online ou local, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência de reunião:

- **AutomateProcessing: `AutoAccept`** Os organizadores da reunião recebem a decisão de reserva de sala diretamente sem intervenção humana.

- **AddOrganizerToSubject: `$false`** O organizador da reunião não é adicionado ao assunto da solicitação de reunião.

- **DeleteComments: `$false`** Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada. Isso é necessário para processar reuniões externas Teams e de terceiros para fornecer uma experiência de União por Toque.

- **DeleteSubject: `$false`** Mantenha o assunto das solicitações de reunião de entrada.

- **ProcessExternalMeetingMessages: `$true`** Especifica se deve processar solicitações de reunião que se originam fora da Exchange organização. Obrigatório para reuniões de Teams externas [e reuniões de terceiros](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Garante que o sinalizador privado enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.

- **AddAdditionalResponse: `$true`** O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.

- **AdditionalResponse: "Esta é uma sala de Microsoft Teams de reunião!"** O texto adicional a ser acrescentado à resposta de aceitação da reunião.

Este exemplo configura essas configurações em uma caixa de correio de sala chamada ConferenceRoom01:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Desativar a expiração de senha

Se a senha da conta de recurso expirar, o dispositivo não entrará após a data de expiração. Em seguida, a senha precisará ser alterada para a conta de recurso e atualizada em cada dispositivo. Para evitar isso, você pode desativar a expiração de senha.
  
> [!NOTE]
> Definir **Senha nunca expira é** um requisito para dispositivos Microsoft Teams compartilhados. Se suas regras de domínio proibirem senhas que não expiram, você precisará criar uma exceção para cada Teams de recurso de dispositivo.

Siga as etapas em uma das seguintes guias para desativar a expiração de senha:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Primeiro, Conexão ao PowerShell do Active Directory:

```PowerShell
   Connect-AzureAD
```

Em seguida, consulte [Definir uma senha para nunca expirar](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire).

Este exemplo define a senha da conta ConferenceRoom01@contoso.com nunca expirar.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Conexão para o MSOnline PowerShell:

       ```PowerShell
       Connect-MsolService
       ```

       Para obter detalhes sobre o Active Directory, [consulte Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. De definir a senha para nunca expirar usando a seguinte sintaxe:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Este exemplo define a senha da conta ConferenceRoom01@contoso.com nunca expirar.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (Local)**](#tab/active-directory1-password/)

1. Conexão o PowerShell do Active Directory:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Para obter detalhes sobre o PowerShell do Active Directory, consulte [ActiveDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps).

2. De definir a senha para nunca expirar usando a seguinte sintaxe:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Este exemplo define a senha da conta ConferenceRoom01@contoso.com nunca expirar.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Atribuir uma licença de sala de reunião

A conta de recurso precisa de uma Microsoft 365 ou Office 365 para entrar Microsoft Teams.

> [!NOTE]
> Salas do Microsoft Teams Padrão e Salas do Microsoft Teams Premium são as duas SKUs disponíveis para dispositivos de sala de reunião compartilhados, incluindo Salas do Teams. Uma licença de sala de reunião é necessária para Teams exibições com hot-desking. Para obter mais informações, [consulte Teams licenciamento da sala de reunião](rooms-licensing.md).

Para atribuir licenças usando o Centro de administração do Microsoft 365, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users). Para atribuir licenças usando o Azure AD, consulte uma das seguintes guias:

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Conexão para o Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Para obter detalhes sobre o Active Directory, [consulte Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Atribua um local de uso à sua conta de recurso usando o `Set-AzureADUser` cmdlet. Isso determina quais SKUs de licença estão disponíveis.

    Neste exemplo, o usuário está localizado nos Estados Unidos (EUA):

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. Em seguida, use `Get-AzureADSubscribedSku` para recuperar uma lista de SKUs disponíveis para sua Microsoft 365 ou Office 365 organização.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Para atribuir a licença, use `Set-AzureADUser` o cmdlet e converta a ID SKU da licença (consulte a etapa 2) em um objeto do tipo de licença do PowerShell. Em seguida, atribua esse objeto à conta de recurso. No exemplo a seguir, a ID SKU de licença é 6070a4c8-34c6-4937-8dfb-39bbc6397a60 e é atribuída à conta conferenceroom01@contoso.com:

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. Conexão para o MSOnline PowerShell.

   ```PowerShell
   Connect-MsolService
   ```

    Para obter detalhes sobre o Active Directory, [consulte Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Atribua um local de uso à sua conta de recurso usando o `Set-MsolUser` cmdlet. Isso determina quais SKUs de licença estão disponíveis.

    Neste exemplo, o usuário está localizado nos Estados Unidos (EUA).
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    Em seguida, você pode `Get-MsolAccountSku` usar para recuperar uma lista de SKUs disponíveis para sua Microsoft 365 ou Office 365 organização.

4. Para atribuir a licença, use o `Set-MsolUser` cmdlet. Neste exemplo, a licença "contoso:MEETING_ROOM" é atribuída à conta conferenceroom01@contoso.com:

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Para validar a criação de conta e a atribuição de licença, entre em qualquer Teams Client usando a conta criada.

## <a name="next-steps"></a>Próximas etapas

### <a name="network-and-bandwidth"></a>Rede e largura de banda

Talvez seja necessário aplicar políticas personalizadas de rede, largura de banda ou reunião a essa conta. Para obter mais informações sobre políticas de rede e largura de banda, consulte [Configurações de política de reunião para áudio & vídeo](/microsoftteams/meeting-policies-audio-and-video). Para Salas do Teams, recomendamos definir a largura de banda da política de reunião como 10 Mbps.

Para fins de colaboração, a PowerPoint Live, Whiteboard e anotações compartilhadas. Talvez você queira criar uma política de reunião para ajustar os participantes e as configurações de convidados para Salas do Teams. Por exemplo, revise as configurações de lobby, como quais participantes admitirão automaticamente as reuniões. Para obter mais informações sobre Teams de reunião, consulte [Manage meeting policies in Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Chamadas

Não há requisitos exclusivos para habilitar a chamada com contas de recursos. Você habilita a conta de recurso para chamada da mesma forma que habilita um usuário normal.

> [!NOTE]
> Recomendamos desligar a caixa postal para dispositivos compartilhados atribuindo uma política de chamada às contas de recurso do dispositivo. Consulte [Chamada e encaminhamento de chamada no Teams](../teams-calling-policy.md) para obter mais informações.

### <a name="configure-distribution-groups"></a>Configurar grupos de distribuição

Para organizar seus locais de sala de reunião, você pode adicionar suas contas de recursos de dispositivo a Exchange grupos de distribuição. Por exemplo, se você tiver escritórios em três locais geográficos diferentes, poderá criar três grupos de distribuição e adicionar as contas de recurso apropriadas a cada local. Para obter mais informações, consulte [Criar uma lista de salas](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

## <a name="related-articles"></a>Artigos relacionados

[Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)

[Implantar Salas do Microsoft Teams](rooms-deploy.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Salas do Microsoft Teams licenciamento](rooms-licensing.md)
